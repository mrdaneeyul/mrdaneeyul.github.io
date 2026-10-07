---
title: "A quick and easy way to do a sword-slash effect in GameMaker!"
date: 2017-08-05 21:37:42 +0000
tags: ["devlog", "devblog", "gamedev", "indiedev", "screenshotsaturday", "effect", "game development", "game design", "games", "video games", "GameMaker", "GameMaker Studio 2", "game", "maker", "studio", "2"]
image: "/Images/devlog/2017-08-05-a-quick-and-easy-way-to-do-a-sword-slash-effect-in.png"
alt: "A quick and easy way to do a sword-slash effect in GameMaker!  When my enemy parent object gets hit (all enemies are children of this object, so any enemy that gets hit basically), first check to see if a hit alarm has already been set. If not, go ahead and set it for 1/10th of a second, play a sound, and call instance_create_depth to create the slashEffect_obj. Note the x and y positions–we’re adding a random number from -4 to 4 to x and to y. This is so the slash object is not always created in the exact center of the enemy object.  The slashEffect_obj’s Create Event then picks an angle using “image_angle = choose(90, 180, 270, 360)”. We could include more or less angles in the choose function here, but this works pretty well. This, combined with a bit of randomness to the x & y coordinates of the object, helps the slash effect look a little different each time.  The image_speed of the animation is also set (I’m setting image_index = 0 here for some reason, but it’s totally not necessary). The only other event is Animation End, which calls instance_destroy() to kill the effect object.  (Oh, and back on the enemy object, when the alarm hits 0, it will set “isHit” back to false and the enemy can be hit again.)  **EDIT:** I have this working in game, but it’s not yet ready to show what this looks like. Keep an eye out–should be ready next week, I think! In the future, I’ll try to show code of stuff that I’ve already shown you guys. :)  Let me know if you have any questions!  I don’t always have something visually interesting to show for #screenshotsaturday, so I set up a poll to see if people were interested in seeing screenshots of code (people have requested this before, but I couldn’t tell if they were serious or joking!).  Turns out 80% so far are actually interested, so here ya go, lol. This is kind of nice for me because working on a game isn’t always working on the glamorous visuals. I spend most of my time here in the code!"
tumblr_url: "https://www.thewakingcloak.com/post/163842071344/a-quick-and-easy-way-to-do-a-sword-slash-effect-in"
tumblr_id: "163842071344"
---

A quick and easy way to do a sword-slash effect in GameMaker!

When my enemy parent object gets hit (all enemies are children of this object, so any enemy that gets hit basically), first check to see if a hit alarm has already been set. If not, go ahead and set it for 1/10th of a second, play a sound, and call instance_create_depth to create the slashEffect_obj. Note the x and y positions–we’re adding a random number from -4 to 4 to x and to y. This is so the slash object is not always created in the exact center of the enemy object.

The slashEffect_obj’s Create Event then picks an angle using “image_angle = choose(90, 180, 270, 360)”. We could include more or less angles in the choose function here, but this works pretty well. This, combined with a bit of randomness to the x & y coordinates of the object, helps the slash effect look a little different each time.

The image_speed of the animation is also set (I’m setting image_index = 0 here for some reason, but it’s totally not necessary). The only other event is Animation End, which calls instance_destroy() to kill the effect object.

(Oh, and back on the enemy object, when the alarm hits 0, it will set “isHit” back to false and the enemy can be hit again.)

**EDIT:** I have this working in game, but it’s not yet ready to show what this looks like. Keep an eye out–should be ready next week, I think! In the future, I’ll try to show code of stuff that I’ve already shown you guys. :)

Let me know if you have any questions!

I don’t always have something visually interesting to show for #screenshotsaturday, so I set up a poll to see if people were interested in seeing screenshots of code (people have requested this before, but I couldn’t tell if they were serious or joking!).

Turns out 80% so far are actually interested, so here ya go, lol. This is kind of nice for me because working on a game isn’t always working on the glamorous visuals. I spend most of my time here in the code!
