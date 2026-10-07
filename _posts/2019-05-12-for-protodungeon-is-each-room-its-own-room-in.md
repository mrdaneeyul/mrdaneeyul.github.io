---
title: "For protodungeon is each room its own room in"
date: 2019-05-12 00:57:35 +0000
tags: ["gamedev", "Anonymous"]
image: "/Images/devlog/2019-05-12-for-protodungeon-is-each-room-its-own-room-in.png"
alt: "For protodungeon is each room its own room in"
tumblr_url: "https://www.thewakingcloak.com/post/184814650559/for-protodungeon-is-each-room-its-own-room-in"
tumblr_id: "184814650559"
---

> For ProtoDungeon is each room its own room in GameMaker or is it one giant room. Did you use surfaces for transitions?

. It’s all one giant room!

I use a mixture of surfaces and just plain ol’ drawing on the GUI layer for transitions. The only set of transitions that uses surfaces is the circle in/out. I’d clear the surface to black, then “punch a hole” in it (using the GPU blend mode bm_subtract, if I remember correctly). Then draw it to the GUI layer so it’s nice and on top of everything. The radius of the circle grows or shrinks each step, depending on which transition I’m doing.

The other transitions are much simpler. For example, the fade transition literally just draws a rectangle over the entire screen (again on the GUI layer), and the alpha of that rectangle gets changed every step. You could do this with a surface but that seems like overkill to me.

My transition manager object has a bool property called “isTransitionDone” that gets set when the transition is over. So this can, for example, be checked by the player to set them back to the “stand” state, or move to the next item in the cutscene. But that’s getting into completely different systems. :)
