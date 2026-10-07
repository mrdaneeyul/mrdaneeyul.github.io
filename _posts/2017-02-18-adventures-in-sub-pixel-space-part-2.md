---
title: "Adventures in Sub-Pixel Space, Part 2"
date: 2017-02-18 23:01:20 +0000
tags: ["gamedev", "indiedev", "gamemaker", "code", "The Waking Cloak", "GameMaker Studio 2", "devlog", "devblog", "game development", "dev", "tutorial"]
tumblr_url: "https://www.thewakingcloak.com/post/157413931739/adventures-in-sub-pixel-space-part-2"
tumblr_id: "157413931739"
---

This will be part post, part tutorial on moving objects at fractional speeds at low resolutions and how you can avoid jerky rendering of your sprites as they move about at these fractional speeds… the retro way!

This method works for GameMaker Studio and GameMaker Studio 2, but the same principles can apply to any engine. I didn’t come up with this method, so credit where credit is due: I learned a bunch of cool stuff when I created [this post](https://forum.yoyogames.com/index.php?threads/help-with-diagonal-sub-pixel-movement-in-a-very-low-res-game.14873/) over on the GameMaker Forums.<br>

I had grand plans to add fancy gifs all over the place to this to make it exciting and fun to look at, but I’m lazy and I’ve been under the weather lately. I’m considering a more tutorial-y video at some point, but we’ll see.

Okay, so first, some background: My game’s base resolution is low (320x180) and the game runs at 60fps. This means a good speed for the player object is about 1px per frame. However, [as I’ve discussed previously](http://www.thewakingcloak.com/post/154528744369/adventures-in-sub-pixel-space), diagonal distance is longer than horizontal/vertical distance, so if you move 1px/frame diagonally, you end up moving *faster*.

The calculation for diagonal speed is:

(base speed) / √(xSpeed² + ySpeed²)

In other words: speed divided by the length of the hypotenuse. So for 1px/frame horizontal movement, diagonal movement is ~0.707px/frame. You can take this “constant” and multiply it by any speed to get a good diagonal speed, so if your speed is 5px/frame, diagonal speed would be 5 * 0.707 = 3.535.

This solves the speed issue, but there’s a pretty big, ugly hurdle to overcome: you can’t draw an object at a partial pixel (unless you supersample, but we’ll get to that). GameMaker will only draw at whole pixel numbers, even if the actual coordinates of the player are some fraction. The result is a really nasty, jittery “stairstep” effect. This won’t even necessarily happen at diagonal movement–if your normal speed is something like 1.2px/frame, it’ll still jitter.

So it looks terrible. How to deal with it? Here’s the different methods I tried, in order.

1.  **Scaling** - resize all your assets so that each “pixel” on screen is actually made up of multiple pixels which GM can render at. Pros: no hefty calculations, smoother movement. Cons: awkward, unwieldy, and can run into major issues when you’re trying to scale to different monitor sizes.<br>
2.  **Supersampling** - keep assets normal sized, but when you’re drawing to your application surface, scale it up there, then draw the resolution back down. Pros: extremely smooth movement, avoids awkward asset scaling. Cons: somewhat complicated setup, can be fairly resource intensive, and the camera can still be very jerky (at least in GMS2). Stardew Valley, for example, uses this method to great effect.<br>
3.  **Frames** - count frames, and only move 3 out of 4 frames when moving diagonally. Pros: fast. Cons: inflexible, doesn’t account for all fractions, is clunky. Not as smooth as scaling/supersampling. Probably one of the worst ways to do this.<br>
4.  **Remainders** - this is a refined version of Method 3, and my favorite. I’m fairly certain this is what old, low-res games used. Pros: accounts for ALL fractions, fairly smooth, clean, and retro. Cons: Not as smooth as scaling/supersampling, but again, if you really want that retro feel, this is the way to go. <br>

So how to do it? I’ll put some code below, but [here’s a pastebin](http://pastebin.com/BLUaRDD5) with more complete code (since Tumblr code formatting is kind of terrible).

Here’s code in the player_obj Create event:

xSpeed = 0;<br>ySpeed = 0;<br>xSpeedRemainder = 0;<br>ySpeedRemainder = 0;<br>

And this is the player_obj Begin Step event. This prevents the player from skidding around by resetting the speed to 0.

xSpeed = 0;<br>ySpeed = 0;<br>

xSpeed and ySpeed will be determined later in the End Step, and xSpeedRemainder and ySpeedRemainder will be used to keep a running total of the speed remainders. We’ll go into that further in a bit. But first, the Walk state:

playerSpeed = 1;<br>playerSpeedDiagonal = playerSpeed * 0.707;<br>xSpeed = 0;<br>ySpeed = 0;<br>

//There’s other code in here for other directions, but since it’s sorta long (and simple enough), here’s just two examples:

//Northwest<br>if(isUpKeyHeld && isLeftKeyHeld && !isDownKeyHeld && !isRightKeyHeld)<br>{<br>    sprite_index = player_walk_n_sp;<br>    rotation = compass.northwest;<br>    xSpeed = -playerSpeedDiagonal;<br>    ySpeed = -playerSpeedDiagonal;<br>}<br>//East<br>else if(isRightKeyHeld)<br>{<br>    sprite_index = player_walk_e_sp;<br>    rotation = compass.east;    <br>    xSpeed = playerSpeed;<br>}<br>

Finally, here’s the End Step in the player_obj:

/// @description Move, update state & hitboxStateUpdate();<br>//Add the speed to the respective remainders.<br>xSpeedRemainder += xSpeed;<br>ySpeedRemainder += ySpeed;<br><br>//Sync up remainders for diagonals to avoid stair-step effect (abs() prevents sync on knockback).<br>if(xSpeed != 0 && ySpeed != 0 && abs(xSpeed) == abs(ySpeed))<br>{<br>    if (ySpeedRemainder < xSpeedRemainder)<br>        ySpeedRemainder = sign(ySpeedRemainder) * abs(xSpeedRemainder);<br>    if (xSpeedRemainder < ySpeedRemainder)<br>        xSpeedRemainder = sign(xSpeedRemainder) * abs(ySpeedRemainder);<br>}<br><br>//If the remainder is >= 1 or <= -1, set the whole number as the speed.<br>var xSpeedWholeNum = xSpeedRemainder & ~0;<br>var ySpeedWholeNum = ySpeedRemainder & ~0;<br><br>//Move x, process x collision.<br>x += xSpeedWholeNum;<br>ProcessCollision(id, xSpeedWholeNum, 0);<br><br>//Move y, process y collision.<br>y += ySpeedWholeNum;<br>ProcessCollision(id, 0, ySpeedWholeNum);<br><br>//Subtract the whole number from the respective remainder (so just a fraction is left).<br>xSpeedRemainder -= xSpeedWholeNum;<br>ySpeedRemainder -= ySpeedWholeNum;

A few notes:<br>

-   The code in the End Step that syncs up the remainders is to prevent a minor stair-step effect. It’s pretty easy for the remainders to get “out of sync.” For example, if xSpeed is 0.707 and ySpeed is 1.414, y will move and x will not. Then the next time, x will move and y will not. If we sync up the remainders, this makes the movement smoother.<br>
-   Also, I’m using tile collision (hence the ProcessCollision() function calls). The easiest way to process any collisions without crazy glitches or extra-complicated code is to do it for the x and y directions separately.<br>

And there you have it! Let me know if you have any questions, comments, or even improvements on this method.
