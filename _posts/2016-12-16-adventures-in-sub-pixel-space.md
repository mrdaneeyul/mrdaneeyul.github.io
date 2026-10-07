---
title: "Adventures in Sub-Pixel Space"
date: 2016-12-16 01:30:48 +0000
tags: ["The Waking Cloak", "GameMaker", "GameMaker Studio 2", "gms", "supersampling", "gamedev", "indiedev", "devlog", "devblog"]
tumblr_url: "https://www.thewakingcloak.com/post/154528744369/adventures-in-sub-pixel-space"
tumblr_id: "154528744369"
---

So over the past few days, I’ve been porting the game over to the new version of the engine I’ve been using: GameMaker Studio 2. There are tons of improvements for a project like mine, particularly with tools like tile animations and so on. Plus, there’s a fairly significant fps boost which makes me happy. I’m definitely going to continue using GMS2.

I took the opportunity to work on an issue with diagonal movement.

~Warning: technical details ahead. Save yourself.~

Some backstory: The Waking Cloak is extremely low resolution at 320x180. At 60 frames per second, the player moves at the slow speed of 1px per frame, or 60px per second. However, diagonal movement is a little different, and here’s why: you can think of movement each frame as moving along a square (i.e., a pixel). You can move 1px up or 1px left without much issue. But if you move 1px up *and* 1px left, you’re moving along the diagonal–and diagonal along a square is a longer distance than a side of a square. This means movement is noticeably faster when going diagonally, and we don’t want that!

The solution is to lower the speed when moving diagonally. This comes to about 0.707px per frame, but I rounded up to 0.75 just for the sake of easier math.

Solved, right?

Wrong. Because you *can’t move in between pixels*. Pixels are all smashed together, and there’s nothing in between, so the engine is forced to render the player sprite at whole numbers. This results in a sort of jittery “stair-step” effect. This is incredibly frustrating, and was the original reason I scaled up all my assets x5 way back when I first started development (a mistake, if you’ve read the earlier blogs). Eventually I had settled on a [supersampling](https://en.wikipedia.org/wiki/Supersampling)solution (scale the game up, then scale it back down so you “create” more pixels to work with).

There’s an easier way to supersample with GMS2, as you can use their viewport/camera system. For those of you with GMS2, this means setting your viewport to a multiple of your resolution size (x4 for my game is 1280x720), and then setting the camera to the resolution size (so 320x180). This ends up looking incredibly smooth and solves the stair-step effect, since a speed of 0.75 ends up moving 3 pixels, and 1 ends up moving 4.

Except there’s still a problem. A pixel game with a tiny resolution should be able to run even on old computers, or underpowered computers like my laptop. And supersampling tends to be pretty graphically intensive. So while the average fps stayed at 60, it would occasionally dip and hitch, providing a frustrating experience. Sure, it’d run fine on a gaming computer, but I want others to actually be able to run this.

Doing x2 supersampling provides a ton of relief on the framerate, but we’re back to a moderate stair-step effect. Not my favorite, so I took it off and sought other routes.

Thanks to a discussion all day on the GM forums, learned a way to solve this (one I’d tried earlier, but didn’t implement quite right). If you want to follow the discussion, it’s [here](https://forum.yoyogames.com/index.php?threads/help-with-diagonal-sub-pixel-movement-in-a-very-low-res-game.14873/), but the short version is that you don’t move the player every frame.

The longer explanation is this: the speed is still 0.75 when moving diagonally. But this means:

-   Frame 0, the player won’t move.
-   Frame 1, we add another 0.75, making our speed 1.50, so we move 1px and store the 0.5.
-   Frame 2, we add 0.75 to that 0.5, winding up with 1.25, so we move another 1px and store the 0.25.
-   Frame 4, we add 0.75, winding up with 1, so we move another 1px
-   Frame 5, and we start all over again at 0.

**tl;dr - This has the effect of moving 1px every three out of four frames.**

This isn’t a perfect solution, and there’s still some jitter (I learned that even the games that inspired mine, like Oracle of Ages, has this hint of a jitter when moving diagonally–there’s no way to avoid it!). So, to smooth things out even more, I bump the supersampling back up to x2. It’s nearly perfect, runs at a rock-solid 60fps on my laptop, and I couldn’t be happier to finally put this issue to rest.

Without scaling any assets manually this time!

Later on, I’ll attempt to add an option for those with more powerful computers to allow x4 supersampling for them. You know, for that extra super buttery-smooth diagonal movement.

**STUPID PERSON UPDATE:**

I am a stupid person, and I’m going to blame it on lack of sleep so I don’t feel too bad about it. :)

My code that moves 1px every three out of four frames wasn’t set up correctly (it was late, okay?), and so it was doing nothing. So now that I fixed the code (thanks to the GM forums for pointing it out), I’m observing a couple things:

1.  My movement code before the fix just now did nothing new, and was still just as jittery as before. Placebo effect I guess?
2.  The supersampling was doing all the real smoothing work.
3.  The supersampling isn’t causing massive frame drops anymore at x2. Or at x4. It’s not causing an fps drop *at all*. (which is… incredibly confusing… since it caused one before.)
4.  The fixed code, while it does smooth things out at 320x180, actually doesn’t work together well with supersampling. It has the same effect at any multiplication, more or less. Which makes sense, because we’re avoiding subpixels altogether.

Apparently I learned nothing at all, and supersampling just started working? But seriously, I now have some good options where it’s pretty easy to, down the line, switch to one or the other depending on how much of an old-school purist I want to be (the old games actually do use something similar to my fixed code and have a bit of a jitter).
