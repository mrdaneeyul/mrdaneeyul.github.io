---
title: "Retrospective - ProtoDungeon: Episode II"
date: 2019-11-04 02:32:38 +0000
tags: ["devtober", "devlog", "devblog", "retrospective", "post-mortem", "gamedev", "indiedev", "ProtoDungeon"]
tumblr_url: "https://www.thewakingcloak.com/post/188801841744/retrospective-protodungeon-episode-ii"
tumblr_id: "188801841744"
---

The second episode of ProtoDungeon is just about complete, and I hope you’re all looking forward to its release as much as I am! :D

And as [devtober](https://itch.io/jam/devtober-2019)(working on the game every day for the month of October) is over, it’s about time for a retrospective too. I prefer that term over “post-mortem,” which makes it sound like the project died (though I guess this episode is graveyard-themed, so that might be appropriate!).

## What didn’t go well:

Mainly, I took on too much. This wasn’t intentional, but it WAS a result of:

1.  Not planning long-term.
2.  Not breaking down big tasks and spreading them out

For example, the menu should’ve been broken out into the basic menu, audio settings, video settings, saving, and control remapping, and then divvied them up over the next few episodes. Instead, I did ALL OF THEM AT ONCE. It was a big task, and doing it all at once slowed me wayyy down. The lack of variety made it tough to make good progress.

Also the mausoleum… as happy as I am with the results, building out an extensive series of logic that I would only ever use once… bad idea. If I’d thought it through, I would have built it differently. Unfortunately, by the time I realized this, I was already halfway through, and undoing it would’ve been more work than just forging ahead.

## What went well:

Devtober! I was able to work on the game every single day, and despite that I wasn’t able to finish the game by the end of the month (not necessary for Devtober, just something I wanted to do), I made a ton of progress in little tiny steps. Momentum is a great ally.

Speaking of momentum, posting every day on the social medias—even just images of code or my Trello board—helped regain some of the interest that had waned over my quiet months. Posting every day forever is certainly not sustainable, but it’s something I could consider for once or twice a week.

Oh, and despite that I did too much this episode, I’m happy I won’t have to build all these systems in the future. :)

## What to start doing next time:

-   List out the remaining (known) tasks for the whole ProtoDungeon series
-   Make sure the tasks are broken down to an appropriately small size
-   Build these into a (flexible) roadmap
-   I wouldn’t say this went *badly*, but I’d like to keep early alpha testing more restricted and then only open it to patrons when it’s closer to being finished.

I think with some better planning, I’ll be able to finish Episode III quicker than six months.

## The major new things we got in Episode II:

-   **Ring of starlight**—a new item is always a big deal and will be for every episode!
-   **New audio engine**—thanks to Wandersong for this! I was able to do some cool stuff with two different versions of the same music track
-   **Menus**—Episode I was just a static screen, but now we have new/continue game, audio settings, graphics settings, and controls remapping!
-   **Autosaving**—a huge undertaking, much bigger than expected. But now you can actually quit the game and come back and pick up where you left off. This is part one of the complete saving system, but it is the *biggest, most difficultest* *part*.
-   **NPC**—I’d planned a lot more dynamic action for this guy walking around and tending to the graveyard, but I managed to trim it down after spending so much time on everything else.
-   **Day/night**—another huge undertaking, including the ability to switch between day/night, lighting, day/night sensors and logic, and the palette shift shader (which means I had to rewrite how everything gets rendered due to the pixel scaling).

That’s not to mention dozens of fixed bugs and incremental improvements in various areas!

Anyway, I hope you’ll look forward to Episode II’s release on November 9. If you haven’t yet,[**check out Episode I here** **(it’s free!)**](https://studiospacefarer.itch.io/protodungeon-episode-i). And if you’re a [patron](https://www.patreon.com/mrdaneeyul), I’ll be opening up the poll for the Episode III item soon!!
