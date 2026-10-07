---
title: "Building a ProtoDungeon"
date: 2019-03-28 14:35:31 +0000
tags: ["devlog", "devblog", "The Waking Cloak", "ProtoDungeon", "game development", "gamedev", "indiedev", "demo", "changelog?"]
tumblr_url: "https://www.thewakingcloak.com/post/183770984844/building-a-protodungeon"
tumblr_id: "183770984844"
---

With the impending release of The Waking Cloak’s first demo, *ProtoDungeon: Episode I*, I thought it might be fun to write up a list of things I actually did to get this demo off the ground.

Since the demo is pretty small, and limited to a single main mechanic from The Waking Cloak, people might not realize just how much work went into this. The Waking Cloak is not feature complete at all, and so I couldn’t just copy+paste all my code, slap on some art, and call it done. I had to build tons of systems from the ground up, which will then be used in The Waking Cloak (and future ProtoDungeons). For example, The Waking Cloak doesn’t even have working doors!

This is what I started with:

-   Camera
-   Collision<br>
-   Dialogue system
-   HUD
-   State machine<br>

That’s it. Might seem like a lot, but let’s compare it to what I built brand new for the ProtoDungeon:

-   Designed the dungeon
-   Actually building the rooms in GameMaker
-   Swap mechanic
-   Block pushing mechanics (the very first version of ProtoDungeon had this before The Waking Cloak as a prototype, but I also improved how collision, player push animations, and so forth worked)
-   Trigger/listener/broadcasting system (to hook up buttons and doors, mainly)
-   Buttons
-   Doors
-   Pits
-   Cliffs and walls
-   Z-height–needed several things from this:
-   Player “teleportation” (stairs, doors, etc.)
-   Transition manager (for fades, wipes, etc.)
-   Cutscenes
-   Throne movement logic<br>
-   Swap mirrors
-   Resetting items when leaving the room and returning–tricky, because we don’t want to reset items if you’ve solved the puzzle<br>
-   Getting hurt
-   Writing
-   Audio
-   Game over state
-   New control system to allow keyboard/controller
-   Win “cutscene”
-   Logo
-   Music
-   Improvements to debugging display
-   Title screen
-   Loads and loads and loads and loads and LOADS of bugfixes and tweaks

All this took approximately 2-3 months. Not too shabby! And I’m very excited for the next ProtoDungeon, because even though the next dungeon won’t have the swap mechanic, I can build on this foundation  instead of creating everything from scratch! That means I might even be able to include stuff like enemies and a boss, or menu settings. And then who knows what I’ll be able to do in the third and onward ProtoDungeons.

All of this loops back into The Waking Cloak. I’ll be able to get feedback as we progress through the ProtoDungeon and really make The Waking Cloak the best it can be.

That’s all for now. See y’all on the demo release on April 6 (or March 30, if you’re a [patron](http://patreon.com/mrdaneeyul)!)
