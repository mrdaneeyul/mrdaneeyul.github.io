---
title: "Flowers is important!"
date: 2026-03-25 21:48:36 +0000
tags: ["gamedev", "indiedev", "the waking cloak", "devlog", "protodungeon", "steam", "steam games", "games", "video games", "monogame"]
image: "/Images/devlog/2026-03-25-flowers-is-important-doing-some-gardening-in.mp4"
alt: "Flowers is important!"
video: true
tumblr_url: "https://www.thewakingcloak.com/post/812096229786976257/flowers-is-important-doing-some-gardening-in"
tumblr_id: "812096229786976257"
---

Flowers is important!

Doing some 🌱 gardening 🌱 in [Starflower Engine](https://www.thewakingcloak.com/post/810808108281724928/the-starflower-engine) lately. Got tall grass behaving in 3D and 2D, which was a whole thing, and flower (and other) decorations are working properly too!

**Changes!**

-   Full billboarding for tall grass was clipping through stuff like crazy
-   Switched to full 3D grass (which looked neat in isolation but looked terrible in practice)
-   Switched back to two rows of grass sprites and added partial billboarding
-   Fixed grass autotiling (omg it’s SO much easier than placing the correct grass entity one by one in GameMaker!!)
-   Switched all sprites to use the model system (since models are just 1+ sprites) so that I can use the Model Editor
-   Fixed a bug where entities were stuck in “preview” mode after being placed and therefore not being saved
-   Made it so that entities with looping animations (like flowers!) play during edit mode

[**You can wishlist ProtoDungeon 3 on Steam!**](https://store.steampowered.com/app/1063700/ProtoDungeon_Episode_III/)
