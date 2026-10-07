---
title: "Here’s the first in-game “whitebox” for the ProtoDungeon!"
date: 2019-02-07 16:28:21 +0000
tags: ["devlog", "devblog", "The Waking Cloak", "games", "video games", "game development", "game design", "gamedev", "zelda", "game boy color", "link's awakening", "oracle of ages", "oracle of seasons", "prototype"]
image: "/Images/devlog/2019-02-07-heres-the-first-in-game-whitebox-for-the.gif"
alt: "Here’s the first in-game “whitebox” for the ProtoDungeon! Nothing’s hooked up or finished (hopefully that’s obvious lol), but this will be useful for getting the foundational stuff working before committing to art!<br>  This is a going to be the first demo for The Waking Cloak, specifically for the swap mechanic, but since I don’t want to spoil anything, I’ve been considering just what exactly I’d like to do artwise. Do I use all my existing tiles and sprites–even Tav? Do I go for something completely different, maybe sci-fi?  For now I’ve settled on somewhere in the middle. I’ll use the existing tiles, but maybe recolor them. I’ll create a new set of player sprites (I think it’ll be an orange-themed girl). I’d like to include hints and clues for The Waking Cloak, but I’d also like this to be a completely separate experience!  But **before all that**, I need to get some big pieces in place. Right now I’m getting the doors and stairs to work properly! They’ll need to essentially “teleport” the player object to the proper location, which is a bit trickier than it sounds because the camera also has to follow suit. Since the camera has a fair bit of code around it to make sure it smoothly scrolls between rooms, I have to sidestep that entirely… which currently means this, lol:  {{PC_IMG:0}}  I’m pretty confident I’ll be able to figure that out today. Then it’s on to a transition so the player won’t be completely bewildered by the teleportation–probably some kind of wipe to black."
tumblr_url: "https://www.thewakingcloak.com/post/182633892549/heres-the-first-in-game-whitebox-for-the"
tumblr_id: "182633892549"
---

Here’s the first in-game “whitebox” for the ProtoDungeon! Nothing’s hooked up or finished (hopefully that’s obvious lol), but this will be useful for getting the foundational stuff working before committing to art!<br>

This is a going to be the first demo for The Waking Cloak, specifically for the swap mechanic, but since I don’t want to spoil anything, I’ve been considering just what exactly I’d like to do artwise. Do I use all my existing tiles and sprites–even Tav? Do I go for something completely different, maybe sci-fi?

For now I’ve settled on somewhere in the middle. I’ll use the existing tiles, but maybe recolor them. I’ll create a new set of player sprites (I think it’ll be an orange-themed girl). I’d like to include hints and clues for The Waking Cloak, but I’d also like this to be a completely separate experience!

But **before all that**, I need to get some big pieces in place. Right now I’m getting the doors and stairs to work properly! They’ll need to essentially “teleport” the player object to the proper location, which is a bit trickier than it sounds because the camera also has to follow suit. Since the camera has a fair bit of code around it to make sure it smoothly scrolls between rooms, I have to sidestep that entirely… which currently means this, lol:

![](/Images/devlog/2019-02-07-heres-the-first-in-game-whitebox-for-the-2.gif)

I’m pretty confident I’ll be able to figure that out today. Then it’s on to a transition so the player won’t be completely bewildered by the teleportation–probably some kind of wipe to black.
