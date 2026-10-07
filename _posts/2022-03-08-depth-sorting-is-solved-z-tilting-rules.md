---
title: "Depth-sorting is solved! Z-tilting rules!"
date: 2022-03-08 20:48:23 +0000
tags: ["gamedev", "ProtoDungeon"]
image: "/Images/devlog/2022-03-08-depth-sorting-is-solved-z-tilting-rules.gif"
alt: ""
tumblr_url: "https://www.thewakingcloak.com/post/678190124352274432/depth-sorting-is-solved-z-tilting-rules"
tumblr_id: "678190124352274432"
---

After many months wasting away, I at last came upon the final solution for depth sorting (if you don’t know what I mean by “depth sorting” see the gif above–it’s harder than it looks in 2D!).

So the answer was something called [z-tilting](https://www.yoyogames.com/en/blog/z-tilting-shader-based-2-dot-5d-depth-sorting). Essentially leveraging some 3D functionality of GameMaker to tilt the sprites. Here’s an example by the author of the method:

![](/Images/devlog/2022-03-08-depth-sorting-is-solved-z-tilting-rules-2.gif)

Since I implemented this solution, I’ve been making great progress getting PD3’s dungeon back up to speed (and beyond). Very excited to be working on gamedev again. :)
