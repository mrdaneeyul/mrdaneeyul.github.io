---
title: "Spacefarer Newsletter: September 2020"
date: 2020-10-01 01:17:08 +0000
tags: ["gamedev", "indiedev", "devlog", "devblog", "ProtoDungeon", "GameMaker", "pixelart", "pixel graphics", "zelda"]
image: "/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020.gif"
alt: "Spacefarer Newsletter: September 2020"
tumblr_url: "https://www.thewakingcloak.com/post/630734223020605440/spacefarer-newsletter-september-2020"
tumblr_id: "630734223020605440"
---

Alright, here we go!**<br>**

I picked up where I left off in August: wrapping up the tileset for the episode. Water details, beach details, waterfalls, spikes, cracked floors, etc. Lots of work, especially since I haven’t done a lot of art recently. I’m really proud of the improvement here though.

Next I started on another big task: enemies! I’ve done these before in The Waking Cloak, so there’s a decent framework. Definitely still a big deal, though, given how much I’ve already done on this episode.

I have two enemy types planned, one of which I’m (creatively) calling a hopper (not the official name but probably what it will be called in code forever). In terms of gameplay it’s like a cross between a goomba with butt spikes and a tektite. Will this be annoying to deal with? Maybe! Hopefully not too much. That’s what testing is for.

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-2.gif)

Anyway, to give you an idea of what went into this single enemy:

-   **AI** - fairly simple, just runs every step and has a chance to trigger the jump state
-   **States** - idle, jump, death
-   **Art** - sprites for all states, facing both east and west each
-   **Hitbox logic** - hopper hurts player with spikes, player hurts hopper without spikes
-   **Jumping** - tweaking this to feel right without being too fast or too often definitely took some time, as well as flipping the spikes orientation
-   **Player impact** - tricky to get that little bounce without feeling mushy
-   Confining to a single area - will be useful for all enemies
-   Work out bugs with **pushing the player** on hurt - will also be useful for all enemies
-   **Enemy manager** - keeps track of enemies, deaths, etc.(I ended up putting this on the backburner for another episode; will be mostly useful when I have multiple rooms)

The other enemy? I want to keep it a surprise.

I took a break from enemy design to update the save/load functionality. Ever since I added saving and loading in Episode II, whenever the game had updates, there was a high likelihood that a save file from the old version of the game would break in the updated version.

The reasons for this are numerous and complicated, but the fix is to add save file versioning. With this, I save a version number to the save file, say, 1.2.0. When I make changes to the game, I will also update this number in the game itself.

For example, say a player saves and quits their game in a certain location. Then say I move that entrance to a room in version 1.3.8. If the player updates and they will not be able to load in the proper location and instead might load inside of a tree or a wall and be unable to escape. Thus the fix: the conversion script would check the save file version (1.2.0) against the game version (1.3.8). It would run a line of code to check whether the player is in that position, and if so, move them to the new room entrance.

I wrapped up the hopper, then did a quick bugfix for the cliffs. There was a case where if you jumped at a cliff and hit the ledge just right, you could do sort of a glitchy jump where you weren’t falling or getting up on the cliff. It didn’t hurt anything, but it didn’t look good. I actually got frustrated trying to replicate the bug after fixing it which… uh… I guess means I fixed it.

Then I circled back around to ramps. Westward-facing ramps had incorrect height calculations, meaning they act just like eastward-facing ramps, so I fixed that.

Some more attempts at ramp collision made me question whether I wanted to still do them or not. Of course I’d still have north-facing stairs, but collision is much simpler on those. Since I only had one east/west ramp in the level design, I removed it and decided to only do north-facing ramps.

NEXT… the fun part! The culmination of all my plans for the dungeon, creating the map in Tiled, painstakingly building the new mechanics, and so on: actually creating the dungeon room.<br>

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-3.png)

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-4.png)

Of course, I’ve changed the functionality of the boots since I last planned the dungeon. This has been a pattern starting back in Episode I, and it’s a result of taking theory and putting it into practice. For the boots, here’s what changed from my initial design notes:

1.  **Lv1** - **Jump** height has been reduced from 16px to 12px. I decided partway through level design that not only could you jump over pits, but you could jump up cliffs. But jumping up the standard height of 16px breaks a lot of design; cliffs would have to be very tall to serve as blockers, and various other obstacles break too. 12px jumps let you go up 8px cliffs without jumping over various obstacles. However, the map design did not yet account for 8px cliffs.
2.  **Lv2** - **Diving** has been added. Not sure how I overlooked this, but here we are. Diving below the surface is great for ducking under projectiles and maybe finding some secret stuff.
3.  **Lv3** - The **dash** no longer serves as a “long jump.” This solves a handful of redundancy issues (mainly jumping/swapping), but it did require a map update. Instead, dashing only acts as temporary invincibility and a faster roll. This will still let you dash through attacks and so on, but not over pits, and I plan to use this in Episode III.

So I made quite a lot of changes, all told, from the Tiled draft to the room in GameMaker.

I broke one of the cardinal rules of programming: instead of making small changes and testing often, I got lazy(?) and made a BUNCH of changes and didn’t test for days. I figured adding collision tiles and water tiles and cliffs wouldn’t cause too much trouble.

Well. They mostly worked. But the first foray into the dungeon was pretty janky with loads of bugs. It was honestly pretty discouraging, and I wanted to just stop and give up for a while. But I started breaking down the problems into more manageable chunks. That was enough to keep me going. Here are the bugs I tackled this month:

-   Made tile collision respect z-height.
-   Fixed an issue with the east area border snapping the player back.
-   Prevented jump in midair <br>
-   Fixed camera dip when diving
-   Fixed cliff sprite generation drawing invisible layers (usually leading to garbled, neon-colored cliffs)
-   Prevented teleporters (stairs, cave entrances, etc.) from triggering when submerged.
-   Fixed camera movement issue when loading the game that started the player in the wrong room (sometimes within a wall).
-   Fixed issue with being able to jump into tile walls and get stuck.
-   Fixed cliff collision box calculations (I messed this up earlier this week when messing with tides interacting with cliffs).
-   Made one high cliff at the bottom of one of the areas shorter, thus fixing a bad collision issue.
-   Rigged up a way to allow high tide to smoothly allow you to walk onto floors at both 0 and 16 (the secret is to lower all adjacent cliffs by 16 at high tide).
-   Fixed invisible daytime tiles when loading a daytime save file.

I also rigged up a way for “tides” to work, meaning tiles and collision changes depending based on day or night.

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-5.gif)

Near the end of the month, I took one more swing at (north-facing) ramps. This ended up being a *whole thing*. I couldn’t use my stair object like before because the player actually has to change z-height. I temporarily forgot how triangles worked.

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-6.gif)

It’s hard to see here, but the player needs to make it up to a z-height of 48. However, she’s only getting up to about 37. This completely baffled me for about an hour. I tried changing the calculation, the collider, and so on, with no results.

Well. As it turns out, I was trying to force the hypotenuse of the triangle (the ramp) to be the same size as the sides (the ground and the cliff). This isn’t physically possible, lol. When you’re only factoring in two dimensions, this isn’t an issue, but when you add the z axis (even if it’s faked), you have to obey the laws of geometry.

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-7.gif)

(still some work to do here; ramp movement is very fast and the shadow is all over the place, but it does work).

After that, the bugs were getting me down again, so I decided to switch gears. I added the boots, chapel keys, regular keys, and some rocks! This doesn’t sound like a lot, but it goes a long way towards making it a real, functional game.

And lastly: October is going to be fun! I’m doing [Devtober](https://discord.gg/q2ZPpX)! I effectively do this anyway–a little bit of game development every day–but it’ll be good to join everyone again. My goal is to have everything playable by the end of the month from start to finish (but not necessarily bug free). Wish me luck!

Peace out. Here’s an early enemy bug.

![](/Images/devlog/2020-10-01-spacefarer-newsletter-september-2020-8.gif)
