---
title: "Resolution is Hard (devblog 2 / update 2)"
date: 2016-09-20 14:01:18 +0000
tags: ["gamedev", "game design", "The Waking Cloak", "gbc", "game boy color", "retrogaming", "zelda", "resolution", "aspect ratio", "update", "pixel", "pixel art", "devlog", "devblog"]
image: "/Images/devlog/2016-09-20-resolution-is-hard-devblog-2-update-2.png"
alt: "image"
tumblr_url: "https://www.thewakingcloak.com/post/150681373992/resolution-is-hard-devblog-2-update-2"
tumblr_id: "150681373992"
---

I’m a developer because I like to solve puzzles.

While I’m in the thick of it, I hate the problem. It’s overwhelming, impassable, irritating. Then, when I have a breakthrough, when all the pieces of that puzzle fall into place, I feel unstoppable.

I was never any good at sports. I’m clumsy, terrible at small talk, not very observant and tend to be a little gullible and slow to pick up on humor. I will likely never feel the rush of making a touchdown or get excited to go to a meet-and-greet (that’s a thing… right?). But dang it if I don’t feel the life pulsing through my veins when I finally find the solution to a problem.

Nerd time:<br>

So I’m mimicking the Game Boy Color, which has a resolution of 160x144. The Zelda titles on GameBoy have 16x16 pixel tiles and sprites–in other words, the screen is 10 tiles wide and 9 (minus one for the HUD, leaving 8) tiles high.

But this is *tiny*, especially on our computer screens (and even on a smartphone). Obviously, we don’t want to play in such a small window, so we scale up.

**Here’s the issue:** it’s really hard to scale up pixel graphics. I can multiply everything by 5, thus getting a 720px-high window, and everything looks cool. But if we want to scale up to a 1080px-high screen (currently the most common), we have to multiply that original resolution by 7.5… meaning some pixels will be bigger than others.

This happens whenever you try to multiply by a non-whole number with pixels. Here’s what it looks like at x1 (normal) and x1.5 (freaky):

To avoid this, I needed a whole number that all the common monitor sizes (720, 1080, 1440) were divisible by. 360 divides into all of these! Hooray! So I immediately began taking my x5 scale assets and dividing them in half so I could have a beautiful 360px-high window that could be scaled up.

And that’s when I encountered the second issue: **I’m an idiot.**

16x16 tiles and sprites multiplied by 5 (what I had originally) and then divided by 2 leaves us with 40x40 tiles. I am, essentially, multiplying 16 by 2.5. In other words, It’s the same issue as trying to scale 144 up to 1080: some “pixels” are bigger than others.

Annoyed, I worked on other functionality, and I was generally pretty productive. It kept gnawing at the back of my mind though: how will I display the game without making it blurry or distorted? And how would I display the game without *giant black bars* on either side of the screen?

The answer came a week or so later, and it was one that I didn’t quite want at first because it wasn’t “authentic” or some such hipster thing. Also it would be a fair bit of work.

*I would change the game.*

Well. I would change the game’s resolution anyway.

This was a pretty big decision, but it had to be made early lest I be forced to do even more work later. So after some math (math is hard, you guys) I determined essentially that the game screen would be twice as wide (20 tiles) and a little taller (10 tiles, plus a 20px-high GUI). 320x180. A 16:9 aspect ratio, which is the most common monitor size.

I was a little nervous about abandoning the screen ratio of the Game Boy, but you know what? It looks kinda cool. And the other retro kids are doing it–just look at Shovel Knight.<br>

And in a stroke of beautiful luck, 320x180 scales perfectly to 720p, 1080p, 1440p, and 4k in 16:9. Puzzle pieces falling together.

**The State of the UnionThe Waking Cloak:**

-   Added “state machines” which help with code design, organization, etc. The player has a “Walk” state, a “Stand” state, a “Using Item” state, and so on.
-   Started combo system for attacks and item usage.<br>
-   Updated the resolution to 1) avoid black bars and 2) scale the game to any monitor size without pixel distortion (read the blog!!).<br>
-   Along with that, updated all my assets to their original size of 16x16.
-   Worked on sub-pixel movement logic so that the small assets won’t be all jerky when they move around. Still working on this.
-   Finished fifth mockup: The Roots of the Lotus Tree.
-   Worked on sixth mockup: a coast with some… mysterious things. This was my first mockup in the new resolution, and so I also worked on a new HUD.
-   Worked more on worldbuilding, backstory, and plot. Fun stuff!
