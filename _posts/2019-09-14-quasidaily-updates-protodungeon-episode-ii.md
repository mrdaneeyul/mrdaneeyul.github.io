---
title: "Quasidaily Updates - ProtoDungeon: Episode II - August 31 - September 13, 2019"
date: 2019-09-14 15:31:02 +0000
tags: ["gamedev", "indiedev", "devlog", "devblog", "ProtoDungeon", "The Waking Cloak", "daily", "changelog"]
tumblr_url: "https://www.thewakingcloak.com/post/187710541774/quasidaily-updates-protodungeon-episode-ii"
tumblr_id: "187710541774"
---

**August 31, 2019**

Been grinding away at PDII for some time, and as much as I talk a good talk about avoiding burnout and getting stuff done, I fell into the trap. I started crunching myself. With a baby, and a day job, and this as a hobby, my brain has been overworked to the point of being unable to solve simple coding problems.<br>

I’ve been playing games again (haven’t played any for two months!!!) and Bounty Train has completely sucked me in.

I’ll probably do a little work on the dungeon entrance for Episode II tonight or tomorrow, but I’ve been enjoying the unwind.

**September 7, 2019**

-   Worked on dungeon entrance logic. It’s… close. Still some quirks. Gonna take a break from this for a bit.
-   Prevented bug which caused you to be stuck reading a certain book forever.
-   Fixed crash when loading the game due to the door collision masks losing their doors. There were two parts to this fix: 1) Doors are now considered solid objects instead of creating a collision mask (this ended up being an annoyingly gigantic task involving editing GUIDs in GameMaker’s .yy files because GM handles instance variables weird), 2) collision masks delete themselves if their object no longer exists.

**September 9, 2019**

-   More dungeon entrance logic. I have it finally doing what I want… almost. Still some coordinates values to tweak, namely for any ring blocks caught up in the shift.

**September 11, 2019**

-   I believe the dungeon entrance logic is basically done now. Linked ring blocks shift properly.
-   Fixed an issue with the building exterior and ring block depth.

**September 12, 2019**

-   Fixed an issue with the dungeon entrance floor not displaying properly.
-   Save the state of the dungeon entrance.

**September 13, 2019**

-   FINISHED THE DUNGEON ENTRANCE AAAAAAH. This has seriously been a huge blocker in completing this episode… there’s a couple things that I just didn’t consider that, when combined, would conspire against me so thoroughly. I also know a couple different things that would’ve made it way easier but OH WELL.
-   Drew an actual sprite for the day/night object. Not sure it’s the final one, but it’s better than the super stretched bed, lol.
