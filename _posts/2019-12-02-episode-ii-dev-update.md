---
title: "Episode II dev update!"
date: 2019-12-02 18:40:45 +0000
tags: ["devlog", "devblog", "gamedev", "indiedev", "ProtoDungeon"]
tumblr_url: "https://www.thewakingcloak.com/post/189435803834/episode-ii-dev-update"
tumblr_id: "189435803834"
---

So I’m Working on another optimization patch. I’ve run the profiler, and it looks like the object(s) taking the most time is… (drumroll please)

You guessed it: the tall grass!

Okay, so what’s happening here is each “tall grass” square is an object. Every frame, they’re checking for collisions with actors and other objects, and if so, they create a rustling effect. Unfortunately, since this is doing collision checking *and* ds_list creation/deletion every frame for every single patch of grass, it takes up about 12% of each frame.

I could do a quick fix on this, but I’m gonna go the slightly longer route and put together something I’ve needed for a while: a deactivation manager. This will deactivate all unnecessary instances (enemies, grass, NPCs anything that doesn’t need to watch for updates) and place them in a data structure that keeps track of them per in-game “region”. That way when the player is entering a region, the manager can go through and reactivate everything in there. When they leave, it can deactivate everything.

It’ll be a little complex since it has to work properly with save/load (deactivated objects won’t save, and instance IDs aren’t guaranteed to be the same for each run; I’ll need to reactivate everything on a save and then deactivate), but overall I think we can have it done soon. Hopefully this means a nice framerate jump for everyone.

I think I have determined also that the day/night shader is *not* the cause of the framerate issues some of y'all are seeing, but I have some ideas for improvements as well just in case.
