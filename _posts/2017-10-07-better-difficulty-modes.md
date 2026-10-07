---
title: "Better Difficulty Modes"
date: 2017-10-07 15:00:38 +0000
tags: ["game development", "game design", "devlog", "devblog", "video games", "difficulty", "options", "settings", "gaming", "games", "design", "modes"]
image: "/Images/devlog/2017-10-07-better-difficulty-modes.jpg"
alt: "image"
tumblr_url: "https://www.thewakingcloak.com/post/166144863849/better-difficulty-modes"
tumblr_id: "166144863849"
---

Difficulty in games is a pretty hotly-contested subject.

The most recent hullabaloo came about from [this article on a “skip boss” button](https://www.rockpapershotgun.com/2017/10/02/assassins-creed-origins-tourism-difficulty/). Many are vehemently against the idea. Others loved it. A few fell somewhere in the middle. My opinion? It depends on the game. A “skip boss” button itself might not be a good idea, but maybe an optional invincibility mode is (Nintendo games used to offer an invincibility star if you died too many times, or there’s the old school godmode cheat). Ideally, this is tied to bonus points, or score, or achievements, or unlockables–but I digress.

Here’s what I want: **better difficulty options for all kinds of players**. We can have our cake and eat it too, if we just spend some time thinking.

First things first: not all games need difficulty options. **For some games, difficulty is integral to the experience.** Dark Souls is a common example: its core gameplay loop is built entirely around its difficulty, and the experience would unravel if it was too easy.

But I’d argue most games aren’t built around difficulty.

## Enter difficulty options

The standard approach is a decision between some variation of **Easy/Normal/Hard** at the beginning of the game. Normal might be the developer-intended way to play the game, Easy is for those who want to relax after a hard day’s work, or for little kids, or for those who want to experience a story, or for those who just aren’t very good at games (and that’s ok, by the way). Hard is for those who want an extra challenge and maybe extra achievements or unlockable secrets.

**But we need better difficulty settings**, because there’s a problem with Easy/Normal/Hard: it’s an uninformed choice.

## Uninformed choice is a bad choice<br>

In other words, when you ask the player if they want to play on hard mode, what does that mean? More HP to enemies? More complex AI? (ha, right) *Cheating* AI? Fewer powerups? More XP needed to level up? **You don’t know until you actually play the game**, and sometimes even then you aren’t sure. The player has to guess what they’re getting themselves into.

This isn’t good choice.<br>

Sure, you might know you generally prefer Easy mode, and for most games that offer these options, it ends up working out. *But we can do better!*

## Informed difficulty settings

First, let’s tell the player what’s going on. Some games explain what different difficulty modes mean. This is a much better version of Easy/Normal/Hard. For example, Shadow Warrior 2:

If you’re going the traditional Easy/Normal/Hard route, **add these descriptions**. Inform your players’ choices. Tell them they’ll take 50% less damage and get more healing items. I enjoy the personal touch here, reiterating that Easy Mode is a perfectly valid way to play.

(Another good example of this is Baldur’s Gate: Enhanced Edition. [Check it out](http://i.imgur.com/t6nXOK8.jpg)! Even though I usually like a challenge, I’m unashamedly playing on Easy because AD&D 2 is freakin’ brutal.)

This is a good choice, because players now have an understanding of what they’re getting themselves into. But guess what? We can do even better–we can give the player control!

## The ideal: custom difficulty settings!

Keep **Tourist,** **Easy**, **Normal**, and **Hard** modes, but also display a list of more granular difficulty options beneath–these granular options can get highlighted and switched on when a particular difficulty mode is selected. The player can choose one of the basic options, or create a **Custom** difficulty–perhaps even save custom difficulty profiles if there are a lot of settings.

The mockup below isn’t perfect (I got tired of placing each individual letter), but it’ll give you a general idea. Also *these are not options for The Waking Cloak* (though some of them might be).

![image](/Images/devlog/2017-10-07-better-difficulty-modes-2.gif)

Some things I might change even here: I didn’t highlight which individual settings get counted as Easy/Normal/Hard as they were selected. And I’d like to add a better description for what each option does, especially for players who’ve never played the game before. I also considered some kind of indicator for whether a setting counted as very easy, easy, normal, hard, or very hard, like a colored underline–green for easy, red for hard. There’s more, but the mockup should at least give you the idea.

## Ideas for custom difficulty settings

-   **Story/Tourist mode** - just wander around and experience the story. No fighting.
-   **Save types** - player can save wherever they want, only at designated save points, or ironman (only one “suspend” save file, deleted on death).
-   **Dungeon guide** - a glowing “critical path” to guide players through dungeons. If you have this option on, you can still turn the guide on/off.
-   **Skip boss button** - display the skip boss button to optionally allow players to avoid them.
-   **Enemy amount** - fewer, normal, lots. Ideally on the “more enemies” settings, you’d have different types of enemies that force the player to think more critically
-   **Enemy speed** - movement, attacks, etc. Test those reflexes! This is a more meaningful, fun way to increase difficulty than just giving enemies more health. Bullet sponges aren’t fun.
-   **Enemy strength** - Also much more meaningful than bullet sponges. You can even have an instakill option.
-   **Enemy health -** some people like bullet sponges. More power to them. You can even have different options, like regenerating health.
-   **Passive enemies** - enemies are all still there, but they don’t attack you. Good for little kids or those who don’t like violence.
-   **Healing hearts/potions** - turn your ability to heal on or off. Want the harrowing feeling of no healing items out in the field? Go for it!
-   **Survival Mode** - you need food/drink/shelter to survive. Also? Diseases! [Fallout 4 and Skyrim are adding these modes](https://bethesda.net/en/article/5lz4Q7F4li6kwKmakkgWww/skyrim-survival-mode-coming-soon?utm_medium=bitly&utm_source=SocialMedia), and I approve!
-   [**Nuzlocke Challenge Mode**](http://www.nuzlocke.com/challenge.php) - specifically for monster collection RPGs!<br>

The main thing to keep in mind is that not everything will work in every game. Design difficulty settings around particular mechanics in your game. As we’ll see later, a driving game might have options that ignore hydroplaning to make things easier or manual shifting to make things more difficult. A stick shift mode wouldn’t work in The Waking Cloak, nor would survival mode make sense in a racing game.

## Ok, so what’s the catch?

**More settings means more testing**. More options means more development time and more work. You need to decide which variables to expose. You need to program the game so that these variables can be exposed in the first place. You’ll need to spend more time considering completely different play styles.<br>

**You also want to be very careful to not lead players down the path of least resistance against their will**. This is the thing I have against fast travel. Some people like it, and that’s fine. But to people like me, who enjoy the journey of walking around and exploring, it’s more like a temptation. From experience, I know I’ll enjoy the journey more, but once I start fast traveling, I always fast travel, and the game becomes a lot more shallow to me.

(There’s another principle of game design around fast travel–make walking around more interesting and varied. But that’s another discussion for another time.)

**You don’t want to overwhelm the player with options**. [Analysis paralysis](https://en.wikipedia.org/wiki/Analysis_paralysis) is a thing. Try to only reveal the options that are most meaningful to the player and the game’s mechanics. Walking the fine line between too few and too many options might be difficult.

## Examples!

This isn’t a new concept. Plenty of games have implemented granular difficulty settings.

![image](/Images/devlog/2017-10-07-better-difficulty-modes-3.jpg)

**Way of the Passive Fist** - four sliders allow you to choose your difficulty. This is nice and granular, allowing for all kinds of tweaks.

![image](/Images/devlog/2017-10-07-better-difficulty-modes-4.jpg)

**Darkest Dungeon** - [from Mark Brown’s tweet](https://twitter.com/i/web/status/915587773482061824). I like that this explains that you’ll be changing the experience. Notice how the difficulty settings are linked very closely to game mechanics, like monster corpses or enemy crits.

![image](/Images/devlog/2017-10-07-better-difficulty-modes-5.jpg)

**Forza Horizon 3** - the description is nice, because that makes your choice even more informed. I also like that it’s clear that you get bonuses for harder settings. Again, notice how difficulty settings are linked to game mechanics, such as steering, ABS, and tire wear.

![image](/Images/devlog/2017-10-07-better-difficulty-modes-6.jpg)

**Invisible, Inc.** - I’ve heard good things about the difficulty setting here! Once again, difficulty settings are linked to game mechanics. One [review](https://kotaku.com/invisible-inc-the-kotaku-review-1703519658)stated that choosing custom settings was letting the player try out game design, and I agree.

## Further reading:

-   **[Check out this accessibility site with even more!](http://gameaccessibilityguidelines.com/allow-gameplay-to-be-fine-tuned-by-exposing-as-many-variables-as-possible/)**
-   **[Assassin’s Creed announces “Tourist Mode”](https://waypoint.vice.com/en_us/article/xwg4dj/the-new-assassins-creed-will-have-a-tourist-mode-and-so-should-other-games)**
-   **[A polarizing argument for a “Skip Boss Fight” button](https://www.rockpapershotgun.com/2017/10/02/assassins-creed-origins-tourism-difficulty/)** and
-   **O[ne of the bigger indie devs speaks up in favor of the “skip boss” button, and discussion](https://twitter.com/tha_rami/status/915201350643757056)follows**<br>

## **Got more games with good difficulty settings? Got more ideas? Comment or reblog ‘em!**
