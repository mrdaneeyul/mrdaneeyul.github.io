---
title: "The Starflower Engine - Dialogue Creator"
date: 2026-06-04 19:20:37 +0000
tags: ["gamedev", "indiedev", "devlog", "the waking cloak", "protodungeon", "monogame", "gamemaker", "video games", "games", "pixel graphics"]
image: "/Images/devlog/2026-06-04-the-starflower-engine-dialogue-creator.mp4"
alt: ""
video: true
tumblr_url: "https://www.thewakingcloak.com/post/818519303657848832/the-starflower-engine-dialogue-creator"
tumblr_id: "818519303657848832"
---

One of the really fun things about building my own engine and tools is I can just *make stuff*. That sounds stupid, like duh, but it’s very freeing!

A current example is a dialogue editor. I’m moving from NPC/journal/sign dialogue directly in the objects themselves out to external files. Dialogue is just text in JSON now! This makes it easier to:

-   Find and change dialogue easily without digging through objects in the IDE
-   Immediately update dialogue in-game without rebuilding
-   Translate! Translators can work with files!
-   Mod the game???

You can do this in GameMaker too (or any other good engine), and some folks have created some really neat tools around doing this (see: Juju, Yellowafterlife), so this isn’t exactly exclusive to a custom engine. But it *does* let me make my own neat tools integrated directly into my games.

So before I was just kind of doing this:

![](/Images/devlog/2026-06-04-the-starflower-engine-dialogue-creator-2.png)

Assigning an array of strings to “dialogue”, which is what triggers when the player interacts with this lil guy.

I’ve already mentioned that it’s better to have this in its own easily-accessible file, but it’s also:

-   Hard to tell how it will look or paginate in game (ran into this a lot, sometimes it would overflow or paginate weirdly)
-   Hard to remember effect syntax, like shake (the \4 you can see in there) or color, or whatever else

So for The Starflower Engine, I made a neat little dialogue editor. :)

It’s still in progress (as is everything I guess), and I’m working out the details for choices and flags and stuff, but as it is now it’s really fun to preview it immediately, work out the pagination, see the effects in progress, and see how things will branch and effect.

Any dialogues and ids and flags and such used here will also go into the aggregated list of flags, which is another thing I’m working on for visibility, design, and debugging (maybe some kind of… node graph??). It’ll basically let me see what the game is doing at a high level glance and easily find what does what (ex: this button opens that door, this guy has that dialogue).

So that’s it for now! Making good progress on this stuff. Building and improving the toolset is really helping the actual gamedev process be way smoother and way more fun.
