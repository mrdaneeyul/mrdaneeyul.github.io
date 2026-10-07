---
title: "My stance on generative AI"
date: 2026-03-01 16:20:34 +0000
tags: ["gamedev", "ai", "indiedev", "indie", "devlog", "the waking cloak", "indie games", "steam games", "steam", "gamemaker", "video games", "monogame"]
tumblr_url: "https://www.thewakingcloak.com/post/809901264532111360/my-stance-on-generative-ai"
tumblr_id: "809901264532111360"
---

I’m going to put this plainly to start and then explain myself a bit more throughout because I don’t want this to feel like some kind of bait-and-switch.

I have a nuanced opinion on generative AI: I think AI is an abysmal replacement for human thought and creativity, was unethically trained, is overhyped by tech bros and CEOs, and is a massive money and energy sink; I also think it’s getting good at coding, and while I have significant reservations about this as well, I’ve found it’s a pretty decent coding assistant.

I’ve had to use it in my day job (as in, it was officially part of a research/proof-of-concept project I was assigned to), where I’m thankful it’s viewed as, at best, an assistant and never a replacement for our developers. And let me tell you, there’s nothing like firsthand improvement way down in the weeds to realize how hugely overblown this whole AI thing is. Don’t believe the executives who are claiming it will replace humans anytime soon. It’s way too stupid. It’s maxed out its intelligence stats and made wisdom its dump stat. I’ve witnessed firsthand how much work it actually takes to get it to work. But it’s also freed us up out of a pretty big backlog of very mundane gruntwork so we can work on stuff that’s more important.

I’ve used it in gamedev too. I’ve used it to help me debug, teach me how to use shaders, and build tools so I can actually spend more time making the games. I’ve been extremely hesitant to say this because I know how generative AI is (rightfully) viewed. However, I also want to be honest: I use Claude Code.

But I’m not letting Claude Code make a game for me (it’s not good at that anyway). I’ve been moving away from GameMaker into MonoGame, which is something I’ll dive deeper on in another post soon! For now: MonoGame is a framework more than an engine; it’s very bare bones on its own. You’re pretty much just given a bit of code and told “have fun.“ No editor, no sprite management, no object/entity creation, not even stuff like window resolution management. But also a LOT more freedom, and, AI aside, that resolves some really tricky issues I was starting to run into at the fringes of GameMaker’s capabilities (I do love me some GM, but it’s a 2D engine, and I was having to do some really janky stuff to get “3D-in-2D” working).

So my use of Claude Code is more in building a focused editor/engine than anything else. Any features built with Claude Code are limited to features that any major game engine already has. It’s only assisting in building features Unreal or GameMaker already have. In a word: scaffolding.

In more words, I only use Claude Code for:

-   Debugging
-   Optimization
-   Using it to analyze freely licensed code for educational purposes
-   Building editor features that other engines have by default
-   Moving my own code from GameMaker to MonoGame (this is the bulk of my use)

I will not use generative AI for:

-   Art
-   Sound
-   Music
-   Special effects (puffs of dust, weather, that kind of thing)
-   Puzzles
-   Mechanics or game design of any kind
-   World design
-   Characters
-   Writing
-   Lore
-   Dialog

I’m still over here placing tiles by hand. Any game made by me, or Studio Spacefarer if it grows beyond me, will be made by humans and not AI. In my use, AI must be limited to being more like a machine that’s assisting in building my tools. It’s not the painting, the painter, or even the paintbrush. It’s a 3D printer that helped assemble a new palette board or canvas frame.

And the only reason I’m getting anywhere with it is because I know what I’m doing with code, and I know when AI is trying to give me bs. I’ve been a professional developer for almost 14 years, and on the side I have 7-8 years of code for The Waking Cloak and ProtoDungeon. This isn’t some vibe coded mess or a stack of cards. It’s targeted, specific use with the intention of hopefully one day not even needing AI.

But I also get it. There are issues with using generative AI at all, even if I’m not using it to make my art for me.

One such consideration: LLMs were unethically trained. Even code was scraped without consent. This is a prickly issue, and I don’t like that it happened. However, my usage doesn’t meaningfully change this historical training cost. I don’t endorse it. I’m only making a constrained choice within imperfect systems, and I remain uncomfortable with it.

(So why choose it at all? Because it has overwhelmingly enabled me to get back on my feet and actually enjoy gamedev again with very limited time and resources. Instead of fighting at the edges of GameMaker’s 2D capabilities, I’m using custom-built capabilities that work for my very specific use case.)

Another consideration: is coding with generative AI an energy hog? Am I burning down forests for convenience? This worried me greatly, so I stopped using AI and did some research into it (actual reading, not just googling vaguely). I was very surprised by what I found. Even under heavy use and including the cloud-based processing, text-only Claude Code is *roughly* equivalent to gaming on a desktop PC. There aren’t solid numbers here. But in terms of order of magnitude, we’re talking pretty tame. [Sources here](https://www.notion.so/Claude-Code-energy-use-sources-31101a60f29b80528b02e1c9ec09cf07?pvs=21).

The real culprits are image, audio, and especially video generation. These are significantly more intensive than text, and I will not be using these.

Even if AI gets better at that type of thing, even if we were talking energy-efficient, high-fidelity, convincing, “beautiful” output, it’s still not worth it to me creatively.

Art should be human. AI should at most only enable more human creativity, rather than supplanting it. So while I’m using AI, my line will always be that it enables me to enjoy making the game, rather than making the game itself. Robots don’t get to do the fun part! I care too much about making games to let something else make them for me.

So that’s the less fun part of this conversation. Next time we get to talk new engine stuff. :)
