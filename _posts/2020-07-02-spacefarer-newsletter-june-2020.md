---
title: "Spacefarer Newsletter: June 2020"
date: 2020-07-02 02:49:36 +0000
tags: ["gamedev", "indiedev", "devlog", "devblog", "ProtoDungeon", "the waking cloak", "studio spacefarer", "game boy color", "zelda"]
image: "/Images/devlog/2020-07-02-spacefarer-newsletter-june-2020.gif"
alt: ""
tumblr_url: "https://www.thewakingcloak.com/post/622495716083892224/spacefarer-newsletter-june-2020"
tumblr_id: "622495716083892224"
---

Well, month two of this newsletter! We’re still doing this thing!<br>

This gif isn’t really related to anything in this newsletter, but I wanted to share this because 1) there will be a few paragraphs without images and I want to provide you with some interesting content, 2) I’m sort of possibly doing more camera rework which you may hear about next month… who knows, and 3) it’s hilarious.

So anyway, yeah, I got a lot done this month. I installed the GameMaker Studio 2.3 beta, created the ProtoDungeon 3 project, and put together the git repository. Of course, I ran into a fair few bugs when transitioning to the 2.3 beta. Namely, the player would always just slide to the right…

After quite a lot of debugging (is my input library working? is there an object on the player pushing the player? are there two players pushing each other?), I discovered that the player was pushing herself. Some stuff had changed behind the scenes that messed with one of my collision checks. Easy to fix though!

Then I fixed up some ancient camera issues that have been around since the dawn of time. The camera was originally created to follow the player with lerp (short for “linear interpolation;” this is what makes the camera move smoothly). This lerp caused all kinds of little visual quirks if I wanted to instantly move the camera anywhere because it was trying to “smooth out” that movement. And it was inflexible too. Well, now I have more control over it; stuff most people probably won’t notice, but it makes things much easier on my end and does actually get rid of those quirks.

As sort of another giant rabbit trail (bear trail?) from starting actual work on Episode 3, I implemented the new floating HUD. I thought I had a ton of code that would be impossible to untangle due to the way the camera compensated for the HUD being at the bottom… but this was surprisingly easy. Now, there’s some rooms that aren’t big enough causing problems, and I’ll have to go through and resize all of them (most of Episode I will be this way). Anyway, super pleased with the new direction on the HUD here.

Before:

![](/Images/devlog/2020-07-02-spacefarer-newsletter-june-2020-2.gif)

After:

![](/Images/devlog/2020-07-02-spacefarer-newsletter-june-2020-3.gif)

And then the main feature: I worked on the new boots! The boots have a lot of different functions, but I’m trying to get the main one: jumping! This also went much faster than expected. I do have a lot of polish to apply still, but it does work.

![](/Images/devlog/2020-07-02-spacefarer-newsletter-june-2020-4.gif)

Fun fact: it’s the same sprite as the ring spell object, and it ends up kinda looking like the Mario jump. I dunno if it’s gonna stay that way… but it’s not bad?

Also, **[please watch these gifs](https://imgur.com/a/toyDf2d)**. I had a lot of funny moments working on jumping.

Lastly, I ran into [a tile collision tutorial](https://pixelatedpope.itch.io/tdmc/devlog/156556/converting-tdmc-to-use-tiles), so I (perhaps unwisely) chose to convert my collision system to that. It’s much more performant and way easier to change in the workflow, but it will require me to fix a few collision issues I’ve sort of been masking until now. Will this pan out? Who knows.<br>

![](/Images/devlog/2020-07-02-spacefarer-newsletter-june-2020-5.png)

I’m pretty excited at my current pace of development. Of course, I’m not over-optimistic enough to say this episode will be done soon, though. :)
