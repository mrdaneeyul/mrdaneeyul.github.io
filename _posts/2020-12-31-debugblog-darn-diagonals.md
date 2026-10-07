---
title: "Debugblog: Darn Diagonals"
date: 2020-12-31 15:55:04 +0000
tags: ["gamedev", "devlog", "devblog", "debugging", "debugblog"]
image: "/Images/devlog/2020-12-31-debugblog-darn-diagonals.gif"
alt: "Debugblog: Darn Diagonals"
tumblr_url: "https://www.thewakingcloak.com/post/639033781874049024/debugblog-darn-diagonals"
tumblr_id: "639033781874049024"
---

I love and hate debugging. It’s frustrating to have a problem and have to work it out before you can continue being creative. On the other hand, it’s a puzzle, and I like puzzles. Working them out feels really good. Like beating that boss. <br>

Anyway I don’t know if this is helpful to y’all, but I decided to write up a blog on my debugging process. (Maybe I’ll do more in the future under the “Debugblog” series??)<br>

So here’s the issue. <br>

In this gif, I’m ONLY pressing one key at a time: left, right, up, or down. But the player is moving at an angle somehow.

The weirdest part: this doesn’t happen all the time, and it only happens in **daytime**. This is baffling.

So the first step in debugging is we need to **replicate the issue**. When I initially found this bug, it was only happening on a random screen and just slightly so. I ignored it for a while. When I saw it happen again, I started making mental notes of the conditions in which it occurred.

Eventually I found a place where I could reproduce the issue consistently (in the gif above). This will be invaluable when testing! If the issue is hard to replicate, it’s harder to test and harder to check when it’s working.

The next step is usually the biggest one: finding the cause of the bug. Usually you want to **isolate the issue**, which you’ll see come up a lot as I move forward…

So anyway, the bug is with movement. I have two “movement” scripts. One that takes into account various environmental variables and modifies velocity–*move_actor()*–and one that actually moves the object and factors in collision–*movement_and_collision()*.

I figured the first place I should go is my *move_actor()* script. I want to know if the extra variable in movement is being added to the velocity before *movement_and_collision()* is called.

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-2.png)

One of the most common ways to debug is using a breakpoint. I could use a breakpoint here, but the issue is that this line runs every single frame I’m moving, so that makes movement difficult. Instead, I’m going to use *show_debug_message()* (I created *console_log()* as shorthand which also shows time and frame information). <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-3.png)

(Full disclosure, I actually was looking at the code in the “else” block first, and the velocity was always being logged as 0,0 lol… because that only runs when the player isn’t moving. It’s okay to make mistakes!) <br>

So I played the game and duplicated the issue. My guess was that there would be an extra y value added here, but lo and behold, there wasn’t. Check out some of the debug output:

> [14:51:34.16493] x: -1.20, y: 0
>
> [14:51:34.16511] x: -1.20, y: 0
>
> [14:51:34.16527] x: -1.20, y: 0
>
> [14:51:34.16543] x: -1.20, y: 0
>
> [14:51:34.16560] x: -1.20, y: 0

This is what we’d expect: the player is moving left at 1.2 pixels per frame and y movement is 0. However, I am still seeing extra y movement in game. Unfortunately this means we did not find our issue yet, but it also means we can discount everything in *move_actor()* and before! Basically this extra movement is almost certainly in *movement_and_collision()*. <br>

Okay, so let’s clean up *move_actor()* and move into *movement_and_collision()*. This is an asset I bought from Pixelated Pope, so I won’t show you the whole thing (not that I was showing you all of *move_actor()* either), but I’ll show you the important stuff. This is near the end: <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-4.png)

Yeah, so this never gets hit, lol. Let’s try earlier in the script. <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-5.png)

Uhh… sorry this is hard to read (tumblr is not great for posting code). I’m logging lengthdir_x and lengthdir_y in the initial *tile_and_place_meeting_3d()* check.

Alright, so here are some logs. Yep. Here’s our unwanted diagonal movement.

> [15:05:12.10597] x: 1.17, y: -0.24
>
> [15:05:13.10613] x: 1.17, y: -0.24
>
> [15:05:13.10630] x: 1.17, y: -0.24

Okay, so this script actually does have some recursiveness built in (it calls itself under certain conditions). That’ll make debugging this a little bit trickier. Let’s figure out which “recursion” this is being called on. In other words, I want to know if this is happening on the first run of the script every frame, or when the script calls itself. Luckily, this recursion functions via a “count” variable (which stops the script from infinitely calling itself lol). I’ll add that into my *console_log()*.

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-6.png)

I forgot to add a space, but that’s okay, we can still read it. it looks like it’s occurring when it calls itself (count is “2”).

> [15:13:40.11644] count: 2x: -1.17, y: 0.24
>
> [15:13:40.11661] count: 2x: -1.17, y: 0.24
>
> [15:13:40.11677] count: 2x: -1.17, y: 0.24

I’m actually going to move this outside of the if block and see if it occurs during all calls or just on the second. Here are the logs. <br>

> [15:17:38.12612] count: 1, x: -1.20, y: 0
>
> [15:17:38.12612] count: 2, x: -1.17, y: -0.24
>
> [15:17:38.12628] count: 1, x: -1.20, y: 0
>
> [15:17:38.12628] count: 2, x: -1.17, y: 0.24

Okay, we’ve confirmed it’s occurring only when the script calls itself. However, I think this is actually “correct” behavior. The *movement_and_collision()* script is doing something called “angle sweeps” for its collision checking. If it can’t find an opening (i.e. runs into a wall), it tries again at a slightly different angle. This allows the player to move along diagonal collision walls. <br>

That means the issue seems to actually be in the collision check. It’s finding a collision where there should not be any, meaning the angle sweep gets triggered! <br>

Okay, so the issue seems to be in *tile_and_place_meeting_3d*. This is my tile_and_place_meeting_3d() script:

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-7.png)

There’s a lot of ground to cover, so I’m going to actually break this up so I can figure it out easier. Basically we want to narrow down to exactly where the issue is occurring. Isolating the issue.<br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-8.png)

The output of this is weird as heck, but yeah, it’s occurring in tile_meeting_precise(). I’m not colliding with any tiles–or shouldn’t be. <br>

> [15:36:49.45138] tile: 0, instance: 0
>
> [15:36:49.45139] tile: 1, instance: 0
>
> [15:36:49.45154] tile: 1, instance: 0
>
> [15:36:49.45155] tile: 0, instance: 0
>
> [15:36:49.45155] tile: 1, instance: 0
>
> [15:36:49.45171] tile: 1, instance: 0
>
> [15:36:49.45171] tile: 0, instance: 0
>
> [15:36:49.45172] tile: 1, instance: 0
>
> [15:36:49.45188] tile: 1, instance: 0

Okay, I could debug further, but we know which script the issue is in. I happen to know I’ve made a few recent changes to this script, so first I want to share the magic of version control! <br>

I use git and store my code on a private github repository. This means I can go back and see a history of all changes made to this file.<br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-9.png)

Okay yeah, so what I’m gonna try first is to just take the old version and put it in  GameMaker and see if that fixes the issue. I do need the changes from the new version, but if I can pinpoint the issue as having been part of this specific change, I can rework it (probably). <br>

You can usually do this via a revert but I was dumb and copy+pasted the old version and deleted the new version. Way jankier, BUT the old version fixed the issue! That means some change I introduced in the new version is causing the issue. <br>

The next step is to redo the new changes one by one until we figure out which one is the culprit. <br>

I recreated all my changes and the issue only occurs when I enable “SD tile collision checking”. How exactly SD collision works isn’t important to this debug process, but it’s essentially the opposite of “HD tile collision checking”, which is for the player so they can slide smoothly along walls. HD tile collision can be smooth because it uses enlarged colliders (the reason for this is a long story).<br>

However, logging shows that the player object never hits SD collision checking. Interesting, right? Why would the **player** have a collision **only** when SD collision checking is added *but the player never hits it?* Well, I think the answer goes back to some of our initial discoveries when replicating the bug: it only happens in the day. Now, nothing changes for the player physics/movement between day and night, but other objects do call this script that are affected by day and night. <br>

I quickly added a log to print out object names to see what other objects use this. It’s easier than doing a search all files for the script name because that could end up with all sorts of results, some of them not directly being called by the objects. [Note: I later found this actually is what is happening; an object is calling this script indirectly via another script] Anyway, here’s the log:<br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-10.png)

*show_debug_message(object_get_name(object_index));* is a super handy way to print out the names of objects calling a script.

The logs showed a handful of items are checking collision: keys, heart containers, teleporters, etc. I want to start with the teleporters, though, since so far those always seem to be present where the weirdness is happening. Just a hunch.<br>

Oh and guess what? Teleporter_obj is calling *tlie_meeting_ground()* *in the daytime only*. We know the issue only occurs in daytime. And *tile_meeting_ground()* seems like it could easily be related to *tile_meeting_precise()* right?<br>

So the quick and easy check here is to comment out lines 8 and 9. And guess what? No more weird player collision! So now we have the culprit. But we do actually need this code. So… why is this interfering with the player? <br>

First, I confirmed that it was indeed the *tile_meeting_ground()* script by removing it. Then I put it back and did some more digging. Interestingly, this script never calls *tile_and_place_meeting_3d()* (remember, that’s the script I modified and is causing the issue). So that’s a bit baffling. This is all it does. <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-11.png)

I need to narrow this down more. I started by returning early if the object was a teleporter. I first did this on line 59 before calling tile_get_at_point(), then on line 60, etc. <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-12.png)

Eventually I broke out each individual check and tested returning after each one so I could pinpoint which part of this script was causing the issue. Turns out it’s *ground_z_get()*.<br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-13.png)

*ground_z_get()* determines… well, where the ground is. And guess what? It does call *tile_meeting_precise(*). AHA! Another mistake on my part. But we’ve established that’s okay. :)<br>

The *ground_z_get()* code is not pleasant to post here, so suffice it to say, I changed the part where it calls *tile_meeting_precise()* to skip when it’s the teleporter calling.

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-14.png)

This is definitely the problem.

Now we know where *obj_teleporter* is calling *tile_meeting_precise()* and this is starting to make more sense. When I was confused about the *tile_meeting_ground()* code not being related to the *tile_meeting_precise()* code, I was wrong, because *tile_meeting_ground()* indirectly calls it. And we already knew that *obj_teleporter* called *tile_meeting_precise()* somehow (otherwise it wouldn’t have shown up in the output log). This is it.

Okay but that’s a patch, not a true fix. I’m going to undo it, roll up my sleeves, and dive back into *tile_meeting_precise()*, the source of all our woes. <br>

Looking at this script further, I think I may know vaguely what’s going on here. It creates a checker object that matches tile collision. Now, this is a local variable, and when *place_meeting()* is called, it’s against the instance id, not against all *obj_precise_tile_checker.* But just for kicks, I’m going to destroy the instance before the script returns to see if this is the issue.

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-15.png)

**This worked!!!** <br>

As to why, I was a bit confused at first. This is all local variables, right? One object calling this script will have local variables that should not ever affect another object calling this script with its own local variables.

But the secret is up here: <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-16.png)

A bit of optimization so that we’re not constantly creating a bunch of collision checkers every single frame. What is happening is the first time this script is run (say an SD one), it creates a tile checker and sets the size (later in the script). Then when another object comes in (say the player with HD/smooth checking), it sees that a checker object is already created and does not create an appropriately scaled one. <br>

I’ve got a better idea than using *instance_destroy()*… I’ll create an SD and an HD tile checker object. That way we can create both and they can exist at the same time without interfering with each other. <br>

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-17.png)

Here we’re just creating an HD checker if we wanna use HD collision checking (just the player right now lol) and SD checker if we wanna use SD checking. Boom. I removed the *instance_destroy()* from this script and here we go… <br>

**That fixed it!** <br>

And the final step: **test everything!** Of course you should be testing after each incremental change so you know exactly what fixes or causes the issue (which we did). And I already tested walking. But let’s make sure our teleporters still work. :)

I tested a bunch of ‘em, but here’s everything working as expected!

![](/Images/devlog/2020-12-31-debugblog-darn-diagonals-18.gif)

Yay!

I hope this was helpful to you!

Peace
