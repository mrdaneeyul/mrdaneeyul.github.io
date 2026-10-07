---
title: "ProtoDungeon: Episode II by Studio Spacefarer"
date: 2019-11-13 01:59:16 +0000
tags: ["devlog", "devblog", "gamedev", "indiedev", "ProtoDungeon", "bugs", "fixes", "patch", "notes"]
tumblr_url: "https://www.thewakingcloak.com/post/189027000924/protodungeon-episode-ii-by-studio-spacefarer"
tumblr_id: "189027000924"
---

[ProtoDungeon: Episode II by Studio Spacefarer](https://studiospacefarer.itch.io/protodungeon-episode-ii)

I’ve been hard at work updating the game, tweaking things and fixing stuff and adding improvements here and there. There’s still a ways to go, but I’m making good progress and thought I’d share. :)

-   Rearranged the gravekeeper’s hut/basement to allow for quicker travel. You may find yourself passing through here a lot, and this should make it less tedious! I moved the door to the left side of the hut, moved the ladder to the bottom left of the hut, moved the basement ladder to the bottom left as well to match, and made sure the path to the basement exit was easy to reach.
-   Added a better visual indicator to the main secret/challenge rooms.
-   Fixed how blocks get destroyed. If you attempt to place a block on a block, both will be destroyed. If you place a block on a wall and two blocks are out, it will destroy the weaker block. This still needs a bit of tweaking, but you should no longer get stuck in small places. :)
-   Moved the gravestone by the second key. Apparently there’s another solution to this puzzle than the one I intended, and this should let you do that!
-   Blocks now get destroyed if you fall in pits to prevent puzzle cheesing.
-   Doors now save properly.
-   Deteriorated ring blocks now do not get destroyed if there is no fresh ring block and a new ring block is being placed on a wall.
-   Borderless fullscreen windowed mode is now in place of actual fullscreen. It appears GameMaker games can have framerate issues when running fullscreen regardless of how “light” the games themselves are. This should resolve most performance issues people were seeing.
-   Added a YellowAfterlife extension that allows Windows border toggling so that you can still see the window frame at smaller resolutions but it can still be hidden at “fullscreen.”
-   Compiled using YYC instead of VM. YYC makes for much more performant games. I didn’t use it before because there was a neverending teleportation bug when I attempted it earlier, but YoYo must have fixed whatever caused it in a recent GameMaker update.
-   Tweaked the arrow puzzle so it wasn’t quite so brutal (if a small part of you was poking out from behind a ring block, really easy to do due to sprite sizes, you would still get hit).<br>

Thanks for reading! I hope you’ll give the game a shot if you haven’t yet. Have a great day!
