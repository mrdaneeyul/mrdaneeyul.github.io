---
title: "Week of June 17, 2018"
date: 2018-06-23 19:22:11 +0000
tags: ["devlog", "devblog", "gamedev", "indiedev", "the waking cloak"]
tumblr_url: "https://www.thewakingcloak.com/post/175179579904/week-of-june-17-2018-over-the-weekend-i-started"
tumblr_id: "175179579904"
---

Over the weekend I started ironing out the bananas movement for the AI. Still some stuff to tweak here–it seems to get stuck moving left after some time, and likes to endlessly walk into solid objects, but IT WORKS.

**Monday**

Spent the whole day working on my day job, so yay.

**Tuesday**

Honestly, I completely forgot to work on the game, lol.

**Wednesday**

Added first implementation of a way to stop the enemy from moving when it runs into a wall… so it doesn’t just continually attempt to walk through walls. It works! Except now the enemy moves SUPER fast because I haven’t yet separated out the movement and collision code. I’ll probably just create a similar “collision check” script that won’t actually move the enemy.

**Thursday**

Created that collision check script, so now we’re doing pretty well! There are still some cases where the enemy doesn’t stop when they hit a wall, but it’s looking really nice. I changed my script that chooses the direction of the enemy when they are about to start walking so that it won’t choose a collision. I’ll also be able to use this so they don’t choose to walk into a pit. :)

**Friday**

Brainstormed a few plot issues with my writing cousin and then did a lot of work on v3 of the outline! Getting better every draft.
