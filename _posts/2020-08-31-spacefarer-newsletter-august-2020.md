---
title: "Spacefarer Newsletter: August 2020"
date: 2020-08-31 17:11:26 +0000
tags: ["gamedev", "devlog", "devblog", "indiedev", "ProtoDungeon", "TheWakingCloak", "pixelart", "zelda", "newsletter"]
image: "/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020.png"
alt: "image"
tumblr_url: "https://www.thewakingcloak.com/post/627985756474966016/spacefarer-newsletter-august-2020"
tumblr_id: "627985756474966016"
---

I spent the first week of August cleaning up cliff and z-object stuff. Not very glamorous! I was definitely ready to move on, but it had to be done. Everything I mentioned at the end of the [July newsletter](https://www.thewakingcloak.com/post/625255857522917376/spacefarer-newsletter-july-2020)? I tackled it.

1.  Falling off ledges now works properly. *This was surprisingly difficult.*
2.  Tile animations on z objects is now handled…
3.  Building cliffs is much less painstaking now. The objects automatically resize themselves for proper collision, and the sprites are all color- and number-coded.

And more: lots and lots of weird cases and stuff fixed. Cliffs at a “negative z” (below sea-level, essentially) were a whole ‘nother animal. They’re still a little janky, and I’ll have to do more manual intervention for these.

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-2.gif)

Also, area transitions were only based on x and y, so throwing z into the mix messed those up hardcore.

Once I got past all that, I decided to tackle **swimming**!

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-3.gif)

Talk about a switch. Cliffs took me a few months. Swimming took me, like, a couple days. Even the stuff I thought would be hard (falling off waterfalls, slippery momentum, etc.) ended up being more or less built in to the systems I have, lol, so I basically just wrote a line or two of new code for those. Diving took an extra few days on top of that, mostly just because I went back and forth on how to modify the z. <br>

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-4.gif)

Next came **rolling**. (You might say we’re on a roll.) This was the first bit I’d copied over from The Waking Cloak project in ages. The Waking Cloak will eventually be built afresh on the ProtoDungeon foundation, but I guess the old code does still have some useful stuff in there!<br>

I did spend an evening converting my mess of move speed/direction/vectors to create a Vector2 struct in 2.3. Structs are a nice breath of Object-Oriented Programming in GameMaker. :) Then I leveraged this so I could easily modify the direction of rolling, jumping, etc. I could have done all this without, but it makes it easier.

“Rolling” in the water will be a dash. Unfortunately, in doing all this, I broke the “slippery” friction on water, which *for some reason* took me a few days to fix.

Roll cleanup from there involved allowing jumping into a roll and rolling into a jump. For gameplay purposes, these don’t let you jump further or anything, but it adds some usability. Without this, if you press the “roll key” right before landing, nothing happens, and it feels clunky. With this, if you press the roll key while jumping, the character will roll immediately when they hit the ground. It feels really good!<br>

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-5.gif)

I updated the controls to match the new rolling. Space and shift now both trigger rolls for keyboard, and the left face button does so on the gamepad. This also meant I had to update the control remapping settings (which needs a UX overhaul, I’m breaking a couple guidelines here, but no time for that now lol).

Next came the dash. This only took a few days, since it’s basically the same as a roll, just faster (not shown in the video, I sped it up after recording) and with a cool afterimage effect! [I had to take a video instead of a gif to capture the full effect (gif framerate is too low, so it’s much more “blinky”). Anyway yeah, click this giant link to watch, lol.](https://i.imgur.com/Ih7KzVs.mp4)

And then I rounded out the month by updating various tiles and sprites. It was pretty tough to get back into the swing of things, art-wise. Thanks to the [Studio Spacefarer Discord server](https://discord.gg/studiospacefarer), though, I’m pretty happy with the direction things went.<br>

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-6.gif)

[Check out the “before” in last month’s newsletter.](https://www.thewakingcloak.com/post/625255857522917376/spacefarer-newsletter-july-2020)

Oh, also, on the penultimate day of the month, I felt like taking a quick break from all of everything to install [rt-shell](https://github.com/daikon-games/rt-shell/tree/master/rt-shell), a plugin that lets you do debug commands. My previous debug method was a list of hotkeys. It was pretty limited! The new one is extensible (I can write my own scripts), so it’s gonna be really helpful.

![image](/Images/devlog/2020-08-31-spacefarer-newsletter-august-2020-7.gif)
