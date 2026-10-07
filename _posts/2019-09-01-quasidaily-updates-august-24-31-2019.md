---
title: "Quasidaily Updates - August 24-31, 2019"
date: 2019-09-01 02:05:04 +0000
tags: ["devlog", "devblog", "gamedev", "indiedev", "ProtoDungeon", "The Waking Cloak"]
tumblr_url: "https://www.thewakingcloak.com/post/187408445829/quasidaily-updates-august-24-31-2019"
tumblr_id: "187408445829"
---

**August 24, 2019**

\-Haven’t been doing much lately, been kinda burnouty and dealing with some big stresses elsewhere. But I’m pretty close to being done with the Episode II entrance art, which I’m pleased about since it’s been bothering me for a while!

**August 25, 2019**

\-Actually got some time to relax and spend time with my wife and baby–and then was refreshed enough to work on the dungeon entrance. There’s some trickiness with the logic here that would be a bit spoilery to explain right now, but I’m ironing those out bit by bit. Art is done, though, I think!<br>-Fixed a bug where locked doors weren’t saving after you unlocked them.<br>-Fixed a bug where solved puzzle elements were resetting to unsolved, which meant the player could get stuck if they exited the game after getting the ring, for example.<br>-Fixed a bug where items (the ring upgrade, keys, etc) would disappear when reloading the game. I’d fixed this before, but a (necessary) structural change is probably what brought it back. Unfortunately, now I’ve created a bug where items you’ve gotten will reappear. So… the opposite issue. Which is progress, I guess?

**August 27, 2019**

\-Fixed the bug where items you’ve obtained are reappearing after reloading the game. Turns out running the game from the external builder extension for GMEdit creates a separate ProtoDungeon 2 folder in the AppData directory, so it was saving to and loading from a completely different save file than the one I was watching. That was a nice misdirection for about a day. The fix was in making sure not to save the items twice. I’d added a section to save items specifically, forgetting that they were considered solvable objects (which already have a section in the save file).<br>-Working on the quirky logic for the dungeon entrance setup. Seems like I’m gonna have to embrace a janky solve here. Just trying to figure out how to do it without breaking the game.<br>

**August 31, 2019**

I have been on a “burnout break” for a few days. Been grinding away at PDII for some time, and as much as I talk a good talk about avoiding burnout and getting stuff done, I fell into the trap. I started **gamedev crunch**. It’s bad even when self-imposed! With a baby, and a day job, and gamedev as a hobby, my brain has been overworked to the point of being unable to solve simple coding problems.

I’ve been playing games again (haven’t played any for two months!!!) and Bounty Train has completely sucked me in.

I’ll probably do a little work on the dungeon entrance for Episode II tonight or tomorrow, but I’ve been enjoying the unwind. Feels good.
