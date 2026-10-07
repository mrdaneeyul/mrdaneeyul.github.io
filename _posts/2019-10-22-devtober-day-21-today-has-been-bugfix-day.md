---
title: "devtober day 21"
date: 2019-10-22 01:54:37 +0000
tags: ["devtober", "devlog", "devblog", "gamedrawing", "indiedev", "ProtoDungeon", "trello", "bugs"]
image: "/Images/devlog/2019-10-22-devtober-day-21-today-has-been-bugfix-day.png"
alt: "Today has been bugfix day! Resolved some bugs:  -   **Severe**: Incorrect saving of mausoleum state meant that quitting the game and loading it outside during the day would display the ridiculously giant black mask over the center of the overworld, obstructing your vision. It has been properly chastised and fixed. -   **Major**: Set the time of day to always be the same when starting a new game. This bug wouldn’t have actually affected anything with the current build, but once I switch “Save & Quit” to go back to the main menu, this will prevent the player starting on the wrong time. -   **Minor**: Obstacles that cover stairs will now be “open” if you come up from underneath them and close as soon as you walk away. This fix prevents funky collision issues when you come up from underneath them and appear “inside” the object. -   **Minor**: Fixed two issues with the dialogue input: first, you can now press either item button to advance through the dialogue, and second, the first pane of dialogue doesn’t immediately skip to the end of that pane anymore. -   **Minor but irritating**: Prevented bridges, doors, and buttons from all playing their sounds on game start"
tumblr_url: "https://www.thewakingcloak.com/post/188506535009/devtober-day-21-today-has-been-bugfix-day"
tumblr_id: "188506535009"
---

Today has been bugfix day! Resolved some bugs:

-   **Severe**: Incorrect saving of mausoleum state meant that quitting the game and loading it outside during the day would display the ridiculously giant black mask over the center of the overworld, obstructing your vision. It has been properly chastised and fixed.
-   **Major**: Set the time of day to always be the same when starting a new game. This bug wouldn’t have actually affected anything with the current build, but once I switch “Save & Quit” to go back to the main menu, this will prevent the player starting on the wrong time.
-   **Minor**: Obstacles that cover stairs will now be “open” if you come up from underneath them and close as soon as you walk away. This fix prevents funky collision issues when you come up from underneath them and appear “inside” the object.
-   **Minor**: Fixed two issues with the dialogue input: first, you can now press either item button to advance through the dialogue, and second, the first pane of dialogue doesn’t immediately skip to the end of that pane anymore.
-   **Minor but irritating**: Prevented bridges, doors, and buttons from all playing their sounds on game start
