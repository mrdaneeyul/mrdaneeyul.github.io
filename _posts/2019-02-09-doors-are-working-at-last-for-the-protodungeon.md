---
title: "Doors are working at last for the ProtoDungeon!"
date: 2019-02-09 19:00:51 +0000
tags: ["devlog", "devblog", "The Waking Cloak", "game development", "game design", "Zelda", "prototype", "demo", "oracle of ages", "oracle of seasons", "link's awakening", "game boy"]
image: "/Images/devlog/2019-02-09-doors-are-working-at-last-for-the-protodungeon.gif"
alt: "This is an example of something that looks really simple but took me three days to implement! Part of that was adding a lot of underlying systems to support not only this, but also a lot of future important things. These systems include:  -   Transitions<br> -   Cutscenes (I didn’t actually end up using it for this since it was too finicky, but it’ll definitely be useful later)<br> -   Updated state machine (thanks to PixelatedPope, as usual… this one can do drawing, which helps with the transitions)<br>  **And so now doors, stairs, and certain pits all work properly!** Hooray! This is one of the biggest core mechanics missing from The Waking Cloak. Now I can add it in and use it to go inside houses, dungeons, between floors, etc. Very exciting stuff.  Next on the list? I don’t know exactly what order I’ll tackle these in. Depends on what it feels like. But here’s what’s on the menu:  -   Getting those ~certain pits~ that drop you down to the floor below working (these actually work already, but I need to animate the character falling between floors)<br> -   Reintroduce grid snapping for swapping, swap objects, and pushing (it was way too complicated without)<br> -   Add “room reset”–jars and unfinished puzzles reset when you leave the room and come back, just like Zelda<br> -   Fix a bug where pits (the ones that actually hurt you) don’t always put you back at the beginning of the room<br> -   Art?  Stay tuned! In a few (several?) weeks, the demo will be available for y’all to try out. :)"
tumblr_url: "https://www.thewakingcloak.com/post/182687317062/doors-are-working-at-last-for-the-protodungeon"
tumblr_id: "182687317062"
---

This is an example of something that looks really simple but took me three days to implement! Part of that was adding a lot of underlying systems to support not only this, but also a lot of future important things. These systems include:

-   Transitions<br>
-   Cutscenes (I didn’t actually end up using it for this since it was too finicky, but it’ll definitely be useful later)<br>
-   Updated state machine (thanks to PixelatedPope, as usual… this one can do drawing, which helps with the transitions)<br>

**And so now doors, stairs, and certain pits all work properly!** Hooray! This is one of the biggest core mechanics missing from The Waking Cloak. Now I can add it in and use it to go inside houses, dungeons, between floors, etc. Very exciting stuff.

Next on the list? I don’t know exactly what order I’ll tackle these in. Depends on what it feels like. But here’s what’s on the menu:

-   Getting those ~certain pits~ that drop you down to the floor below working (these actually work already, but I need to animate the character falling between floors)<br>
-   Reintroduce grid snapping for swapping, swap objects, and pushing (it was way too complicated without)<br>
-   Add “room reset”–jars and unfinished puzzles reset when you leave the room and come back, just like Zelda<br>
-   Fix a bug where pits (the ones that actually hurt you) don’t always put you back at the beginning of the room<br>
-   Art?

Stay tuned! In a few (several?) weeks, the demo will be available for y’all to try out. :)
