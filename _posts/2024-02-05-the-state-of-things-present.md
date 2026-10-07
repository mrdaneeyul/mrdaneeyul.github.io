---
title: "The State of Things Present"
date: 2024-02-05 18:45:55 +0000
tags: ["gamedev", "indiedev", "the waking cloak", "devlog", "devblog", "game development", "protodungeon", "gamemaker"]
image: "/Images/devlog/2024-02-05-the-state-of-things-present.jpg"
alt: "The State of Things Present"
tumblr_url: "https://www.thewakingcloak.com/post/741509699141320704/the-state-of-things-present"
tumblr_id: "741509699141320704"
---

*this post was available for patrons a week early! please consider supporting me [over on patreon](https://www.patreon.com/studio_spacefarer)!*

I kept trying to make this post fancier and better and more engaging, and then I realized I was doing that thing where I make myself too overwhelmed to actually finish and post it. The other thing was I kept gunning for a once-a-week posting, and uh… yeah that’s not sustainable. So here we go!

> *The Ghost of Spacefarer Present appears before you*<br>*He whispers, very quietly, yet in a voice that resonates:*<br>***“Time to resurrect the Spacefarer”***

Ok so the spacefarer (me??) was very tired, but he’s awake now and doing things!

## Life status

We moved! My wife and kids and I packed up and headed some miles south of our previous house. It was a risk for sure. We didn’t know how things would pan out. We really needed to get away from our old environment, our old town, our old house. We loved that house, and we’d said so to each other many times even as we were halfheartedly searching for a new one. But at some point that house had become too burdened with bad memories and traumas, not to mention that after the pandemic, we had no more real roots there. Everyone had moved away, the communities we were involved with had disbanded or changed. And anyway, my wife would be starting a new teaching job down south.

We were fortunate enough to find a new house we loved, and fortunate enough to be in a position where we could actually make the move. I’m aware this is a privilege, given the economy and the market, and so I can only express my thankfulness and consider it a blessing, especially as we healed through our grief.

I have an improved office now! This is where I work on my day job (software/web dev) and my unday job (Studio Spacefarer). With my genetics stacked against me, but also with my desire to be able to keep up with my kids and be there for my family, I collected a standing desk, a walking pad treadmill thing, and an ergonomic keyboard. I’m walking or at least standing most of the day now, which has made a surprising difference already.

I was gonna post a wider view of the office, but my 3yo son ran up while I was taking pictures and started “working” (mashing the keypad), so this is automatically the better pic. Them’s the rules.

Anyway, in short, we made it, and it hasn’t been a smooth ride the entire time, but it has been well worth it. I’ve been able to get back into gamedev, which has been a huge boon to my mental health too.

Speaking of… (ghostly drumroll)

## Game status!

The good stuff. Here’s where I’m at presently with Episode III!

-   The game is completable from start to end (definitely NOT feature complete)
-   Jumping, swimming, and [dashing](https://www.thewakingcloak.com/post/721210880142000128/this-is-fun-d) all work like a charm and are super fun
-   Three [enemy](https://www.thewakingcloak.com/post/686634400039960576/testing-a-bunch-of-these-bouncy-friends-all-at) types have been added, including custom [A* pathfinding for the sea monster](https://www.thewakingcloak.com/post/689760664659591168/i-made-it-better-with-ai-the-sea-monster-can-now)
-   Two new collection mechanics (one is heart containers, the other will be a small surprise)
-   [Depth sorting](https://www.thewakingcloak.com/post/678190124352274432/depth-sorting-is-solved-z-tilting-rules) and [fake-3D](https://www.thewakingcloak.com/post/678734498727362560/bridges-are-working), as mentioned previously, which lets me do [lots of fun effects](https://www.thewakingcloak.com/post/681692985313935360/been-playing-with-my-new-depth-sorting-and-come-up)
-   Day/night are now on a new system, and cave darkness is now a thing (I tried to implement this in PD2 but couldn’t figure it out)
-   [Palette swapping for night and lighting effects](https://www.thewakingcloak.com/post/698560103896465408/how-to-use-gamemakers-filters-for-lighting) now uses GameMaker’s built in layer effects
-   Much of the game is now decorated
-   [Updated the game’s palette](https://www.thewakingcloak.com/post/716974487316398080/update-de-palette) to be more pleasing
-   Better borderless windowed mode, frame toggling, etc. (I’d made [a post](https://www.thewakingcloak.com/post/714761184992247809/in-order-to-do-borderless-windowed-i-had-to-turn) about a third party plugin I used to do this previously, but not long after that, GameMaker added an official setting to be toggleable at runtime, so I switched to that… much easier lol)
-   New audio library which has been a MASSIVE boon ([Juju’s Vinyl](https://github.com/JujuAdams/Vinyl))
-   New flexible debug/inspector mode which allows me to change values on the fly more easily
-   State machine rewrite using structs instead of data structures–extremely flexible and less  error-prone (in fact the data structures here were the #1 cause of crashes in Episodes I and II)
-   Save system rewrite, also using structs instead of data structures (thus fixing the #2 cause of crashes in the first two episodes)
-   Adjusted the way walls get displayed in interiors–will make a post on this later
-   Lots and lots and lots and lots of bug fixes

## Post end status!

I’m not exactly sure how to wrap this up lol, but y'all can be encouraging me, if you have the emotional space to do so! There’s still a lot left to do on PD3, and it can be very daunting at times.

Next post up will be looking forward to the future of Studio Spacefarer. I’m very excited about this! Keep an eye out!
