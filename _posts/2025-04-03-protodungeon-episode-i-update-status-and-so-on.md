---
title: "ProtoDungeon: Episode I - update status and so on"
date: 2025-04-03 18:28:33 +0000
tags: ["steam games", "puzzle games", "adventure", "video games", "update", "gamedev", "indiedev", "game development", "pixel art", "protodungeon", "gamemaker", "crt tv", "steam deck", "macintosh", "macos", "linux"]
image: "/Images/devlog/2025-04-03-protodungeon-episode-i-update-status-and-so-on.png"
alt: ""
tumblr_url: "https://www.thewakingcloak.com/post/779831123459080192/protodungeon-episode-i-update-status-and-so-on"
tumblr_id: "779831123459080192"
---

[ProtoDungeon: Episode I is out on Steam!!!](https://store.steampowered.com/app/3495100/ProtoDungeon_Episode_I/)

Getting this on Steam has been a pretty big milestone, so huge thanks to the folks who have supported me throughout the whole process (and boy has it been a *process*).

## Updates on where everything is at:

**The game runs great on Steam Deck**! Verified by two players so far!

**The macOS build of the game is NOT working** (unless you are still on 32-bit like Sierra). I tested on my old macbook, and so the game ran fine. I did not account for 64-bit-only macOS (totally forgot that was a thing). I’m learning!

The bad news here is that the PD1 project files are so ancient that they cannot be used by any modern iteration of GameMaker, even the latest LTS. They can’t be imported, as the conversion process throws mysterious and arcane errors. I’ve even tried some complicated spells and converters to no avail. I have the “correct” old version of GameMaker on my macbook, which might’ve let me make some updates, but the licensing/authentication/whatever won’t actually let me sign in to do anything.

The GOOD news here is that I did already have all the PD1 and PD2 files in the PD3 project, since they’re all just built on top of the previous episodes. However, quite a bit has changed, which means PD1 was initially *very broken* when I booted it up from there.

(this is fine)

![](/Images/devlog/2025-04-03-protodungeon-episode-i-update-status-and-so-on-2.png)

(the entire game is in the upper left corner… but the room borders were out of control giganto and kept yeeting me into darkness)

Okay so that was actually the intermediate news. The ***real*** good news is that getting PD1 working hasn’t been too big of a hassle, despite the various depth rendering, state machine, HUD, etc. changes. AND that means several features I built out for PD3 are now going to be part of a free post-launch update for PD1 (and PD2 pre-launch), *which means* ya’ll get:

-   **An updated HUD** - not the one from PD3, as PD1’s rooms are specifically 20 pixels shorter to accommodate the bottom HUD, and changing everything right now would be tons more work than it’s worth, but the small update here *will be much nicer* than the stark white one with the big goofy hearts
-   **CRT filter effects** - I’ve hinted at this in the past (you can see it in a gif or two, as well as me raving about my love for CRT shaders in the discord server), but I got some really cool CRT effects working!! It’s more of a subtle nostalgia filter than a 1-to-1 replication of an actual CRT monitor. I think y'all will like it. It adds vibes. A full post on this is coming in the future and I’ll show it off some more, but yes you will be able to toggle it on/off or set parameters
-   **Neato “3D” tall grass** - enabled by the depth sorting / sprite z-tilting system from PD3, and also enabled by the fact that I deleted all the code from the old-style tall grass lol
-   **Working macOS build** - which was the whole reason I started this
-   **Mayyyybe a Linux build???** - GameMaker is capable. Depends on how big a lift this is. I’m not promising anything except that I’ll look into it!

There’s still more to fix, so here’s what I’m working on now:

-   Many objects have become jet-black portals into the void
-   Tall grass isn’t generating all the sprites yet
-   All doors lead to the owlery, for some reason
-   HUD still needs a bit of work
-   Lighting system needs to be fixed

![](/Images/devlog/2025-04-03-protodungeon-episode-i-update-status-and-so-on-3.png)

Making progress! Apologies again to the Mac friends, I’ll get this all fixed up for you, and hopefully the update is a pleasant surprise for everyone as well.

**And finally,** this deserves its own post, but [ProtoDungeon: Episode II is up for wishlisting](https://store.steampowered.com/app/3495160/ProtoDungeon_Episode_II/)! Please go give it a wish and look forward to its release. Any improvements I make to PD1 will be pulled in for PD2 as well.
