---
title: "The Starflower Engine"
date: 2026-03-11 16:34:28 +0000
tags: ["gamedev", "indiedev", "devlog", "steam games", "steam", "indie", "monogame", "gamemaker", "video games", "indie games", "protodungeon", "the waking cloak", "game engine", "starflower", "Youtube"]
image: "/Images/devlog/2026-03-11-the-starflower-engine.mp4"
alt: ""
video: true
tumblr_url: "https://www.thewakingcloak.com/post/810808108281724928/the-starflower-engine"
tumblr_id: "810808108281724928"
---

Normally, switching engines 75% of the way through development is a really bad idea. But, like, I’d gotten *really* stuck on ProtoDungeon: Episode III.

## The Stuckness

A lot of factors were in play. The main one was the depth system. I’ve been talking about that years, so I won’t get too deep (ohoho) into that. Just know that the end result was using 3D tricks in a 2D game: z-tilting shader, overriding GameMaker’s rendering pipeline, and geometry built of fake 3D boxes.

It works! But I also had to hand-place almost 600 instances of those fake 3D boxes, and if I ever wanted to change the level geometry, it was a headache. I made a lot of mistakes, so there were a lot of headaches.

![Fake 3D box geometry headaches in GameMaker](/Images/devlog/2026-03-11-the-starflower-engine-2.png)

ALT

My workflow became something like: place tiles on the correct layer, place the correct 3D boxes on the correct layer, place the additional sprites on the correct layer, try to figure out why the player is drawing under the ground, try to figure out how to get sprites to stop z-fighting, realize I did the wrong 3D box height *again*, close laptop, cry in corner.

If you’re a digital artist, you may have had the experience of attempting to organize your art in neat layers *for real this time* and then after a few hours realizing you’ve drawn everything to one single mega-layer which shall never become untangled. This is like that except it would break the game whenever I did it. Creating something 3D (even partly 3D) is really hard in a 2D editor.

And even goofy 3D boxes and layer issues would’ve been okay by themselves (there’s a lot of crying in corners in gamedev), but other stuff was starting to fray too as a result of being sort-of-fake-but-also-real-3D-in-2D, as well as just pushing GameMaker probably further than it was really meant to be pushed:

-   Ladders just gave up working forever
-   Stairs were a nightmare
-   A* pathfinding broke somewhere along the way
-   Custom rendering pipeline became difficult to work with and really non-performant
-   Actually the game in general was choking on its framerate
-   Collision was getting really bonkers
-   I couldn’t decouple my drawing framerate; I was locked at 60fps despite MANY attempts to use delta time or Juju’s awesome [Iota](https://www.jujuadams.com/iota/#/latest/) library), so this meant the game ran really badly on monitors with higher refresh rates
-   Game compilation now took an aggravating amount of time to complete

I love GameMaker, and all this stuff is doable, but at some point I had to realize I’m effectively creating a 3D game (even if it looks 2D) in a 2D engine.

## Experimentation & The Map Editor

I did a lot of experimentation. Part of this was related, part of this was just because I really wanna try pixel art in full 3D someday. You may remember [this tech demo](https://studiospacefarer.itch.io/protodungeon-i-3d) from a few years back. Then, I more recently had some decent attempts in GameMaker since I hated using Unity SO much. I called the framework “**Diorama**” or “**3Diorama**” (I was trying to be clever). It could swap between 2D and 3D seamlessly, and it’s maybe the closest I got to what I wanted to do:

![The Diorama 2D/3D engine running in GameMaker](/Images/devlog/2026-03-11-the-starflower-engine-3.gif)

ALT

Unfortunately, In the end, it was still pretty clunky to work with and place stuff. So, I drafted a spec for a map editor that would hopefully resolve most of the annoying fake 3D box placement issues. Even if it was just some nice shortcuts to display and swap between layers, and to get some better visibility on “where stuff was” in 2D, that would be a pretty major boon.

I still have the spec. It would save as json, then pipe instances, sprites, and room layout into GameMaker. The additional benefit I was aiming for was, since everything would be json, I’d theoretically be able to make changes and then live-reload rooms to see the changes without recompiling the game (important since it was also starting to take a really long time to compile).

[MonoGame](https://monogame.net/) quickly became the candidate of choice for this. It’s a framework more than an engine. It gives you a few basics (like VERY FEW basics) and sends you off on your way to figure everything out. It really doesn’t do much for you at all. The upside of this is that you can basically do *whatever you want*. Engine doesn’t have a feature? Add it. Really good for a custom map editor.

And I’ve wanted to work in MonoGame for **years**, so this was as good a chance as any!

Then, amidst all this spec-writing, architecture, and planning, I had a very dangerous thought.

## After all, why not? Why shouldn’t I create my own game engine?

There was sort of a “grass is greener” thing going on for sure, as well as going against all the common gamedev advice, but… what if I really did finally make the jump to MonoGame? It actually made a lot of sense. Why export to json and then build some sort of clunky GameMaker import with live-reloading if I could just… *do it all in MonoGame*.

Aside from the technical feasibility (since MonoGame is an open-ended framework, you can kinda just make it act like GameMaker lol), I also just have **wanted to do this for years**. I’m trying to lean more into my instincts about things, rather than what I feel like I’m “supposed to do” according to common advice. I want to work on the things I want to work on. If this were a job instead of my hobby, or if I was on a team, there would be some more give-and-take here, but even then I’d still want to push for what *feels right* instead of a general cookie cutter approach.

So I did it.

I built a 3D pixel art engine that can flatten itself into 2D, and I called it the **Starflower Engine.**

(This is a sort of deep-cut reference to when I almost changed Studio Spacefarer’s name to Starflower because I ran into a UK studio called Spacefarer Games, but they turned out to be nice and the rename turned out not to be necessary. I still like how Starflower sounds though, and “Starflower Engine” is a mix of fantasy and sci-fi that appeals to me)

I’m having a blast and got some deets to share with you, but first, here’s what it looks like so far with me rebuilding ProtoDungeon: Episode III:

## Starflower Engine: What it do

Starflower Engine is basically my dream game engine (albeit a scrappy one lol). It’s a pixelart-based engine that:

-   Supports 2D or 3D top-down pixelart and can easily switch between the two on the fly
-   Runs reminiscent of a C# version of GameMaker - entities instead of objects, C# instead of GML, but you’ve still got Step and Draw
-   Has a **live map editor** - you can run in play mode, walk somewhere, realize you want a wall or enemy there, switch to edit mode, place, and then switch back to play mode
-   Acts a little like Lego or Minecraft in the editor - **tile/voxel placement** with autotile and other conveniences (I actually am having too much fun making stuff)
-   Runs with **uncapped framerate** - logic runs at 60fps but draw runs at max velocity
-   Performs extremely fast - tons of headroom for both Update (Step) and Draw on all sides
-   Has a built-in **lowpoly model editor** using sprite composition - UVs against a texture which can pop out for live editing in Aseprite (and the texture gets wrapped up into a texture atlas for more performanceeeee)
-   Enables record-and-run automated testing that can play through actual levels to verify mechanics and game all still work
-   Contains a built in MP4 recorder for convenience using ffmpeg, because why not
-   Runs with my own custom rendering pipeline, including day/night palette swap shaders, shadows (via the same color swap lookup dictionary used for night), CRT and effects, etc.
-   Is **extremely customizable** because yeah it runs on MonoGame and the engine guts are *all right there*

And more stuff in the works now and whenever I need it. It’s pretty rough around the edges of course, and it’s really only focused on this **exact type** of game(s) I’m making (though, if a few years down the road it becomes polished enough I’d love to share the engine for free).

But as it is now, I’m four months in and enjoying gamedev, *really* enjoying it, for the first time in years. Feels like all the stuff I’ve always wanted to do but stopped myself because it seemed like “I shouldn’t.” I’m learning that’s not how I want to be creative anymore.

So to end all of this, here’s a fun little video I made that summarizes the first four months of Starflower Engine’s development:

Oh yeah and if you’d like to, please consider **[wishlisting ProtoDungeon: Episode III on Steam](https://store.steampowered.com/app/1063700/ProtoDungeon_Episode_III/)!** It’s still planned to be fully 2D, just now in the Starflower Engine (and being built MUCH faster than before!). Episode IV, though, will be another story…
