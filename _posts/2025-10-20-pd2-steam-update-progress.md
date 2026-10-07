---
title: "PD2 Steam update progress!"
date: 2025-10-20 17:24:08 +0000
tags: ["gamedev", "indiedev", "devlog", "devblog", "game development", "protodungeon", "gamemaker"]
tumblr_url: "https://www.thewakingcloak.com/post/797946464403865600/pd2-steam-update-progress"
tumblr_id: "797946464403865600"
---

As usual, I’ve been quiet for a while, so here’s the progress on the PD2 update on Steam! The current version on Steam works, so almost all of these fixes are a result of updating to the latest “Waking Engine” framework. (Waking Engine is what I’m calling the mechanics/code/assets for The Waking Cloak, ProtoDungeon, and anything else down the pipes that winds up using this!)

**Updates**

-   Implemented CRT filters
-   Implemented new menus, etc.
-   Updated title screen card from white to black
-   Updated water to latest version (so if you jump off the bridge you’ll drown, instead of just not being able to fall off at all)
-   Changed save functionality to no longer save as soon as you get an item; we don’t need this anymore as we are no longer sending the player back to the start of the room if they fall in a pit

**Bugfixes**

-   Fix: starlight ring use crashes the game :)
-   Fix: bridges (all of them)
-   Fix: cliffside colliders (you can drown now so let’s be careful)
-   Fix: various objects positioning after sprite origin changes
-   Fix: intro cutscene broken
-   Fix: title screen broken
-   Fix: missing region borders
-   Fix: if you quit and reload you can get the ring item over and over
-   Fix: ring block disappears immediately upon creation
-   Fix: arrow generator positions
-   Fix: UI missing starlight ring
-   Fix: stairs
-   Fix: invisible key
-   Fix: upside down key (??)
-   Fix: “FATHER” headstone moves when you push the mausoleum button, whoops
-   Fix: mausoleum exterior not displaying, covered by mask
-   Fix: basement block not saving position
-   Fix: moon plant and sun headstone not disappearing at day and night respectively

**In Progress**

-   Finalizing z-tilt on various objects/decoration
-   Finalizing perspective change from 2D Zelda-like interior perspective to full orthographic cutaway perspective
-   Fixing various small “wiring bugs” (fences not hooked up to buttons, etc.)
