---
title: "Progressing on the PD2 update is going well!"
date: 2025-09-20 16:43:15 +0000
tags: ["gamedev", "indiedev", "the waking cloak", "devlog", "devblog", "zelda", "game development", "pixel art", "protodungeon", "gamemaker"]
image: "/Images/devlog/2025-09-20-progressing-on-the-pd2-update-is-going-well-life.png"
alt: ""
tumblr_url: "https://www.thewakingcloak.com/post/795225982621679616/progressing-on-the-pd2-update-is-going-well-life"
tumblr_id: "795225982621679616"
---

Progressing on the PD2 update is going well! Life was interfering for a few weeks, but today I managed to squeeze in some time.

The PD1 update taught me it’s probably better to just switch to the new perspective and depth system, rather than halfway switching and retrofitting a ton of stuff in a questionable way. There are still some quirks of the design (such as in the image here), but overall it’s been a smoother process.

Most other walls have been converted here, but I’ll need to work out how to represent north-facing walls without messing with the footprint of things (since that does actually affect the puzzles). Thankfully there are only like two locations that do this.

Less exciting for y'all, but I also converted all The Waking Cloak projects into one repository, with WakingEngine as the core project. I then export this as a versioned package to the PD1/PD2/PD3/TWC/etc projects, and just set a few macros at the roots. This way all code and improvements are much easier to share between all games, and I don’t have to keep copy/pasting entire project directories whenever I want to pull new features since that is pretty… time consuming and error prone.

So there it is–not much left on the PD2 update and then we’ll be back on PD3 🙌
