---
title: "devtober day 30"
date: 2019-10-31 03:13:59 +0000
tags: ["devtober", "devlog", "devblog", "gamedev", "indiedev", "ProtoDungeon"]
image: "/Images/devlog/2019-10-31-devtober-day-30-spent-all-my-free-time-today.png"
alt: "Spent all my free time today hunting down a nasty bug that resurfaced recently. Turns out our duplicate items are back after quitting and reloading the game in some instances. I believe this is due to saving the game before an item is able to destroy itself, meaning when the game loaded, it was pulling in an invisible, undead version of that item that could not be destroyed (which I guess is appropriate for Halloween).  I moved the save to a more appropriate location, which seems to have fixed this instance of the bug. However, I believe other, similar bugs could occur due to the way certain state machine values are saved and loaded, so I will be looking into that post-launch.  So yeah, kinda exhausting and not the way I wanted to spend the penultimate day of devtober, but there you have it. Tomorrow I’ll work on the other game-breaking bug and hopefully finish up the outro!"
tumblr_url: "https://www.thewakingcloak.com/post/188713345104/devtober-day-30-spent-all-my-free-time-today"
tumblr_id: "188713345104"
---

Spent all my free time today hunting down a nasty bug that resurfaced recently. Turns out our duplicate items are back after quitting and reloading the game in some instances. I believe this is due to saving the game before an item is able to destroy itself, meaning when the game loaded, it was pulling in an invisible, undead version of that item that could not be destroyed (which I guess is appropriate for Halloween).

I moved the save to a more appropriate location, which seems to have fixed this instance of the bug. However, I believe other, similar bugs could occur due to the way certain state machine values are saved and loaded, so I will be looking into that post-launch.

So yeah, kinda exhausting and not the way I wanted to spend the penultimate day of devtober, but there you have it. Tomorrow I’ll work on the other game-breaking bug and hopefully finish up the outro!
