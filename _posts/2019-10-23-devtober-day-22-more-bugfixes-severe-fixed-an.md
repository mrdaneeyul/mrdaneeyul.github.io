---
title: "devtober day 22"
date: 2019-10-23 02:35:02 +0000
tags: ["devtober", "devlog", "devblog", "gamedev", "indiedev", "ProtoDungeon"]
image: "/Images/devlog/2019-10-23-devtober-day-22-more-bugfixes-severe-fixed-an.png"
alt: "More bugfixes!  -   **Severe**: Fixed an issue where obtainable items (keys, ring upgrades, etc.) were improperly saving some of their data. When this data got loaded back into the game, it overrode the correct data, causing various and sundry errors. Mainly, when picking up an item, you would get two of that item, and the item wouldn’t disappear. -   **Severe**: Fixed a memory leak by cleaning up the state machine data structures -   **Severe**: Fixed a crash when loading the game under certain circumstances. This was actually related to the improper saving bug above and would have been fixed simultaneously, but I added some extra handling to prevent the crash regardless–just in case. -   **Major**: Retrieving a ring upgrade, leaving the room, quitting the game, then continuing that same game and going back to the place where the ring upgrade was located would grant you another ring upgrade. Fixed this so the ring upgrade would properly destroy itself.  **This means all (known) severe bugs have been fixed, and many of the major/minor as well!**<br>"
tumblr_url: "https://www.thewakingcloak.com/post/188529711564/devtober-day-22-more-bugfixes-severe-fixed-an"
tumblr_id: "188529711564"
---

More bugfixes!

-   **Severe**: Fixed an issue where obtainable items (keys, ring upgrades, etc.) were improperly saving some of their data. When this data got loaded back into the game, it overrode the correct data, causing various and sundry errors. Mainly, when picking up an item, you would get two of that item, and the item wouldn’t disappear.
-   **Severe**: Fixed a memory leak by cleaning up the state machine data structures
-   **Severe**: Fixed a crash when loading the game under certain circumstances. This was actually related to the improper saving bug above and would have been fixed simultaneously, but I added some extra handling to prevent the crash regardless–just in case.
-   **Major**: Retrieving a ring upgrade, leaving the room, quitting the game, then continuing that same game and going back to the place where the ring upgrade was located would grant you another ring upgrade. Fixed this so the ring upgrade would properly destroy itself.

**This means all (known) severe bugs have been fixed, and many of the major/minor as well!**<br>
