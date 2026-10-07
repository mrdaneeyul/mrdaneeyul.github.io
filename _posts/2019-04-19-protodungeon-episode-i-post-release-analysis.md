---
title: "ProtoDungeon: Episode I - post-release analysis"
date: 2019-04-19 21:00:26 +0000
tags: ["ProtoDungeon", "The Waking Cloak", "devlog", "devblog", "game development", "game design"]
tumblr_url: "https://www.thewakingcloak.com/post/184302760378/protodungeon-episode-i-post-release-analysis"
tumblr_id: "184302760378"
---

The first ProtoDungeon released without a hitch, thanks to some excellent testing from some friends and patrons. The feedback so far has been incredibly heartwarming and positive. I’m so glad that you’re all enjoying this demo and sharing your thoughts.<br><br>I did learn a few things, and that’s what I wanted to center this post on. The ProtoDungeon did exactly what I wanted: gave me valuable feedback and practice.<br><br>**Mainly: puzzles are too hard, too easy, and just right.**<br><br>This was (initially) confusing feedback to receive, but I think there’s something to be gleaned from it. Most of the people who thought puzzles were too hard were 1) overwhelmed by the amount of puzzle elements, 2) not aware that you could leave the room, or 3) not able to properly read the puzzle elements (mirrors mainly) <br><br>*And the good news is all of those can be addressed without actually making the puzzles too easy.* <br><br>The Treasury - Move the key elsewhere. We haven’t seen a locked door yet, most likely, so the assumption is that the key is needed to open the gate. It’s too distracting. Also remove one of the elements from this room: teaching mirrors, jars, blocks, and different levels all at once is too much.<br><br>The Dining Room - This room was designed before the changing direction upgrade was decided upon (it was originally short range upgraded to long range, which felt really bland and artificially restrictive). Getting the Lv2 swap spell upgrade early actually makes this puzzle WAY harder, because you can get the swap blocks into weird places, and then wonder stuff like “What’s that button over there for then? What’s *that* block for?” Also: too many mirrors, which made the puzzle feel way more chaotic than it actually was.

*(Note: I actually fixed the Lv2 sequence with v1.2–you can’t get Lv2 before finishing the dining room, which means it’s much less confusing)*

That addresses specific issues. In general, puzzles should be more readable/less chaotic, and I should use at least *some* linearity in order to keep the confusion down. But as far as providing more difficult puzzles: I’d like to create optional difficult puzzle rooms. I don’t know what to put in here as prizes for solving them yet due to the short, disconnected nature of each episode–maybe additional lore? Story? Confetti and balloons?

**Some other tweaks:**<br>

-   The player needs to know they can hold down the button to slow down the swap spell for easier aiming. Teach this! *(I added a brief description for this in v1.2 when the player picks up the spell.)*
-   Somehow teach the player that the answer sometimes lies in another room. Still thinking about this one.
-   Show the player the goal first, or at least locks before the keys.
-   The ability to get the level 2 swap spell upgrade in the owlery early is cool for speedrunning, but really honestly makes some puzzles confusing and others too easy. In the future I’d put this behind some kind of locked door. *(Fixed this in v1.2 with the owl key.)*
-   People like little “puzzle complete” chimes, and I should invest in these chimes.
-   Don’t put all the locked rooms in one place. Spreading them out means the player needs to keep more of a mental map of the dungeon–which is what we want!
-   Be careful about accidentally “punishing” the player–breakable puzzle elements like jars mean the room should be easily resettable. Otherwise things get frustrating.

So there’s that! This was a blast to write up, and I can’t wait to put these improvements into play for Episode II.
