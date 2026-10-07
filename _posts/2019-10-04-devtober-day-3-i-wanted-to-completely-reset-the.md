---
title: "devtober day 3"
date: 2019-10-04 03:08:58 +0000
tags: ["devtober", "devlog", "devblog", "ProtoDungeon", "gamedev", "indiedev"]
image: "/Images/devlog/2019-10-04-devtober-day-3-i-wanted-to-completely-reset-the.png"
alt: "I wanted to completely reset the audio editor stuff and reimport it fresh, since I’d been tweaking it in another solution. The first reimport attempt somehow kept some of the changes I (shouldn’t have) made to the audio engine, such as purple background AND purple text (??). Well, the git revert went bad and removed a bunch of stuff I didn’t want it to. After about fifteen minutes of panic and one failed attempt, I reverted the reversion, and we’re back in business.  Except that the audio editor is in Purple Unreadable Edition, which is 100% my fault (and why I was trying to revert it). Ehh. Anyway. Starting to fix it piece by piece:  1.  added a cursor sprite since my game hides the mouse altogether 2.  fixed the font–editor needs to use the debug font that came with the audio engine instead of my sprite font"
tumblr_url: "https://www.thewakingcloak.com/post/188119305729/devtober-day-3-i-wanted-to-completely-reset-the"
tumblr_id: "188119305729"
---

I wanted to completely reset the audio editor stuff and reimport it fresh, since I’d been tweaking it in another solution. The first reimport attempt somehow kept some of the changes I (shouldn’t have) made to the audio engine, such as purple background AND purple text (??). Well, the git revert went bad and removed a bunch of stuff I didn’t want it to. After about fifteen minutes of panic and one failed attempt, I reverted the reversion, and we’re back in business.

Except that the audio editor is in Purple Unreadable Edition, which is 100% my fault (and why I was trying to revert it). Ehh. Anyway. Starting to fix it piece by piece:

1.  added a cursor sprite since my game hides the mouse altogether
2.  fixed the font–editor needs to use the debug font that came with the audio engine instead of my sprite font
