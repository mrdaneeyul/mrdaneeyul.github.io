---
title: "Episode I version 2.0.x and macOS support!"
date: 2020-01-02 13:32:09 +0000
tags: ["protodungeon", "major", "update", "devlog", "devblog", "changelog", "zelda", "game boy", "pixel art", "GameMakerStudio2", "gamemaker"]
image: "/Images/devlog/2020-01-02-episode-i-version-20x-and-macos-support-happy.gif"
alt: "**Happy New Year everyone!**  I hope it’s is a good one for all of you. Here’s to another year of community, friendship, and gamedev. :)  So… it seems like a good way to start off the year is with a big ol’ **update for ProtoDungeon: Episode I**! Not only have I made a TON of changes thanks to developments from Episode II, but now available for the first time is…  (drumroll please)  ## PROTODUNGEON ON MAC!!!  But even if you’re not a macOS kind of human, don’t fear. As mentioned, this update contains quite a lot of updates for both PC and macOS versions thanks to Episode II. Here’s the full changelog:  **From Episode II:**  -   Lighting (reorganized the the torches in the level, as the new lighting draws emphasis to specific places; some places did not need to be emphasized, while I was able to take advantage of the lighting to draw attention to other locations). -   Menu system (including a new Episode I title card). -   Updated logo. -   Saving/loading (all things considered, this dropped in surprisingly well; I did have to add a few extra cases to fix, such as falling through a pit to the level below). -   Graphics settings. -   Audio settings. -   Updated to the Wandersong audio engine (also updated all audio container names to use constants instead of writing out the strings every time… there were way more of these than I expected). -   Key remapping (new default keys as well to match the updated defaults from Episode II). -   Ability to jump off all cliffs (had to rearrange some stuff to prevent softlocks and other issues).  **Other improvements:**  -   Repaired swap mechanic–this had broken after changing some of the underlying code for another mostly-unrelated system. -   Updated the tiles for the pits that lead to floors below–these should be more distinguishable from the normal hazard death pits now. -   Updated the swap spell item descriptions to be lore-based for consistency. -   Simplified the lv1 swap spell puzzle, as it was trying to teach too much all at once and MANY players found this confusing (this was one area that the new lighting came in handy too). -   Updated the lv2 swap spell puzzle, as it never actually taught the player how to USE the lv2 spell–this was the trickiest change, but adding a new room underneath both gives space for a lvl2 teaching puzzle and makes the punishment for falling a lot less brutal. -   Fixed a collider in the outside room transition. -   Updated the object activation/deactivation manager to account for falling to the floor below. -   Updated the player “fall to target” state so modifying the target coordinates elsewhere won’t interfere with this state (“targetX” and “targetY” are variable names used for a handful of different states). -   Tweaked the top of the teleporter collider so you can’t accidentally miss it.  ## [Play **ProtoDungeon: Episode I** here! It’s free!](https://studiospacefarer.itch.io/protodungeon-episode-i)"
tumblr_url: "https://www.thewakingcloak.com/post/190015485654/episode-i-version-20x-and-macos-support-happy"
tumblr_id: "190015485654"
---

**Happy New Year everyone!**

I hope it’s is a good one for all of you. Here’s to another year of community, friendship, and gamedev. :)

So… it seems like a good way to start off the year is with a big ol’ **update for ProtoDungeon: Episode I**! Not only have I made a TON of changes thanks to developments from Episode II, but now available for the first time is…

(drumroll please)

## PROTODUNGEON ON MAC!!!

But even if you’re not a macOS kind of human, don’t fear. As mentioned, this update contains quite a lot of updates for both PC and macOS versions thanks to Episode II. Here’s the full changelog:

**From Episode II:**

-   Lighting (reorganized the the torches in the level, as the new lighting draws emphasis to specific places; some places did not need to be emphasized, while I was able to take advantage of the lighting to draw attention to other locations).
-   Menu system (including a new Episode I title card).
-   Updated logo.
-   Saving/loading (all things considered, this dropped in surprisingly well; I did have to add a few extra cases to fix, such as falling through a pit to the level below).
-   Graphics settings.
-   Audio settings.
-   Updated to the Wandersong audio engine (also updated all audio container names to use constants instead of writing out the strings every time… there were way more of these than I expected).
-   Key remapping (new default keys as well to match the updated defaults from Episode II).
-   Ability to jump off all cliffs (had to rearrange some stuff to prevent softlocks and other issues).

**Other improvements:**

-   Repaired swap mechanic–this had broken after changing some of the underlying code for another mostly-unrelated system.
-   Updated the tiles for the pits that lead to floors below–these should be more distinguishable from the normal hazard death pits now.
-   Updated the swap spell item descriptions to be lore-based for consistency.
-   Simplified the lv1 swap spell puzzle, as it was trying to teach too much all at once and MANY players found this confusing (this was one area that the new lighting came in handy too).
-   Updated the lv2 swap spell puzzle, as it never actually taught the player how to USE the lv2 spell–this was the trickiest change, but adding a new room underneath both gives space for a lvl2 teaching puzzle and makes the punishment for falling a lot less brutal.
-   Fixed a collider in the outside room transition.
-   Updated the object activation/deactivation manager to account for falling to the floor below.
-   Updated the player “fall to target” state so modifying the target coordinates elsewhere won’t interfere with this state (“targetX” and “targetY” are variable names used for a handful of different states).
-   Tweaked the top of the teleporter collider so you can’t accidentally miss it.

## [Play **ProtoDungeon: Episode I** here! It’s free!](https://studiospacefarer.itch.io/protodungeon-episode-i)
