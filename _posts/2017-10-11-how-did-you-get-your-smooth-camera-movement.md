---
title: "How did you get your smooth camera movement"
date: 2017-10-11 16:26:47 +0000
tags: ["gamedev", "Anonymous", "game design", "game development", "gamemaker", "gamemaker studio 2", "pixelatedpope", "camera", "views", "subpixels", "rendering", "resolution"]
tumblr_url: "https://www.thewakingcloak.com/post/166292609689/how-did-you-get-your-smooth-camera-movement"
tumblr_id: "166292609689"
---

> How did you get your smooth camera movement working? I've tried a bunch of methods, with different lerp functions and such, but it always looks too jerky... :(

You’re partway there–I use a simple lerp in mine! But there’s a few extra bits you’ll need.

I only know how to do this in GMS2 (though I’m certain you can do it in GMS1–it might be similar), so that’s what I’ll be talking about!

Smooth camera movement can be tricky in low-res games, and the reason is because it can’t go “in between” pixels. It will always round to the nearest pixel.

You’ll need two things:

 

**1. Set up your game to use subpixels.**

Subpixels mean each of your in-game pixels will be made up of multiple pixels. You’ll need to enable the ability for at least your camera to move in between pixels.

**2. Manually move the camera/view.**

If your camera is set to follow an object, it won’t take advantage of subpixels (even if the object itself does). You’ll need to set the view manually each step.

This is actually not as hard as it sounds. I could write up a whole thing on how I do this in GMS2, but I’m just using PixelatedPope’s method… so best watch his video instead:

Note: if you’re using GMS1, OR if you want to understand resolution in GameMaker in general, check this playlist out, also from Pixelated Pope:
