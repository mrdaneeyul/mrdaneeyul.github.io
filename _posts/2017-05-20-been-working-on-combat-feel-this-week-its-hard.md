---
title: "Been working on ~combat feel~ this week!"
date: 2017-05-20 15:30:49 +0000
tags: ["screenshotsaturday", "screenshot", "pixelart", "pixel art", "pixel graphics", "pixel", "gamedev", "game development", "game design", "indiedev", "indie", "video games", "gameboy", "gameboy color", "Zelda", "oracle of ages", "link's awakening", "The Waking Cloak", "devlog", "devblog"]
image: "/Images/devlog/2017-05-20-been-working-on-combat-feel-this-week-its-hard.gif"
alt: "Been working on ~combat feel~ this week! It’s hard stuff. I’ve been touching up the appearance of some of the frames here and tweaking the speed of each frame. Lots of behind-the-scenes code too.  The plan is if you use the sword once, it will complete one swing (as you’d expect, lol). Use it again, and it will swing the other way. However, as the second half of the gif shows, if you press the key again *while still attacking*, it will skip the “wind down” frames after the swing and launch directly into the next attack. This should help it feel more responsive.  Previously, you wouldn’t be able to get the “down” swing unless you hit the button again halfway through the “up” swing, but before the animation ended. It was complicated and didn’t feel particularly good. Now, it will just always switch swing direction regardless of the time in between.  I have some changes planned for how hitting enemies works:  -   They won’t fly off if they’re not dead–they’ll just get a bump and come back. This way you won’t have to chase an enemy down to hit it again, which has proven to be annoying in testing. If a hit *does* kill an enemy, then we can fling them away!<br> -   Touching most enemies won’t hurt you anymore (unless, say, they’re spiky or on fire or something). This will allow Tav some movement during combat without killing himself, as well as give me some room for variety in enemy design.  I’ve wanted to get back to combat for a while. Still plenty of work to do, but I’m excited!"
tumblr_url: "https://www.thewakingcloak.com/post/160875491440/been-working-on-combat-feel-this-week-its-hard"
tumblr_id: "160875491440"
---

Been working on ~combat feel~ this week! It’s hard stuff. I’ve been touching up the appearance of some of the frames here and tweaking the speed of each frame. Lots of behind-the-scenes code too.

The plan is if you use the sword once, it will complete one swing (as you’d expect, lol). Use it again, and it will swing the other way. However, as the second half of the gif shows, if you press the key again *while still attacking*, it will skip the “wind down” frames after the swing and launch directly into the next attack. This should help it feel more responsive.

Previously, you wouldn’t be able to get the “down” swing unless you hit the button again halfway through the “up” swing, but before the animation ended. It was complicated and didn’t feel particularly good. Now, it will just always switch swing direction regardless of the time in between.

I have some changes planned for how hitting enemies works:

-   They won’t fly off if they’re not dead–they’ll just get a bump and come back. This way you won’t have to chase an enemy down to hit it again, which has proven to be annoying in testing. If a hit *does* kill an enemy, then we can fling them away!<br>
-   Touching most enemies won’t hurt you anymore (unless, say, they’re spiky or on fire or something). This will allow Tav some movement during combat without killing himself, as well as give me some room for variety in enemy design.

I’ve wanted to get back to combat for a while. Still plenty of work to do, but I’m excited!
