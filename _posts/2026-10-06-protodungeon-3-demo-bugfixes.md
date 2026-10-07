---
title: "ProtoDungeon 3 demo bugfixes!!!"
date: 2026-10-06 00:00:00 -0500
tags: ["demo", "indie game", "pixel art", "gamedev", "protodungeon", "studio spacefarer"]
---

I didn't announce it yet (so I will soon! is this backwards? maybe!) but the [ProtoDungeon: Episode III demo](https://store.steampowered.com/app/1063700/ProtoDungeon_Episode_III/) is released and in the wild for anyone to play. Many, many thanks to my friends who early tested this and got themselves into some absolutely brutal situations (I think they enjoyed doing this tbh).

I've resolved over 55 bugs - more than listed here, but I legitimately bundled so much in my commits that it's going to be too much work to parse each individual thing out.

## Hard locks, soft locks

I don't actually know which is which but these both forced you to restart a new game, or at least quit and reload.

-   **Removed a hole in the world which dropped you off the map near the first major item**. This happened to my very first player lol.
-   **Added a catch to put you back on the earth if you fell off the earth**. Alexa play [Edge of the Earth](https://www.youtube.com/watch?v=C-ToGfKJlEg). Most video games have something like this because players… players find a way.
-   **Fixed respawn putting the player at** **the beginning where they were stuck forever**. I know it's a prison cell, but you shouldn't literally be stuck in the prison cell the whole game.
-   **Cut down a few trees**. Players like to get stuck in weird places so this lets them out.

## Water, falls, and deaths

-   **No more infinite drown loop at the waterfall and river.** Getting into water, especially water with a current, respawned you in the water and drowned you again, over and over until you died. Brutal. Safe ground is now checked with the whole body on dry land.
-   **Prevent death drop drifting downstream.** A death in a current no longer carries the body or the dropped tears away. Now you can get your stuff back!
-   **Two-tile water gaps.** Water edges now behave more consistently, so now you can no longer jump over two 16x16 tiles of water.
-   **Falling off cliffs felt floaty.** A walk-off starts dropping at once instead of hanging for a few frames, with a short downward whoosh (new sound) on any drop of a voxel or more. One player wanted everything *more* floaty but we'll see if we listen to them (you know who you are).
-   **The missing floor by the first leaf.** A 32x8 slot in the leaf basin floor let you fall out of the world. Filled.
-   **Tweaked death scene colors.** Minor but this showed her in daylight colors even at night.
-   **\[THE DARKNESS CONSUMES\]**
-   Now correctly sets interior doorway lights as lights to respawn at. It kept sending you outside or other random places.
-   Speaking of outside, it would drop you outside the cavern onto the ledge where the chapel seal fragment was. Good job. However, this is fixed so you can't do that anymore either.
-   No longer continues while you're in the process of dying because that's just insult to injury.

## Enemies, doors and arrivals

-   **Hoppers ambushing you at a doorway.** Coming out of the Foundation Cavern you were hit before you could move. Enemies have been rearranged a bit here
-   **The darkeye followed you out of the forest and was too persistent.** Its territory is judged at your height, it chases slower, gives up earlier, and finishes going home before it re-engages. No more terminator behavior.
-   **The sea monster bit from any height.** It only bites within six units of its own water level now: safe on the ledge above, bitten in the water. Honestly I don't know how y'all figured this one out given that it's barely accessible at the moment lol.
-   **Ship's hidden stairs now close** after climbing from below without the button. (Also I moved this closer to the button so it could more easily be seen when pushing the button.)
-   **Fixed the mausoleum with no way out**. The stairs are now forced to exist regardless of flags. This room's… readable things… (what, it's a secret, go find it yourself) now have actual text too.
-   **Hoppers in the river** used to idle invisibly on the riverbed; they drown properly now and their tears float and ride the current.
-   **Hopper stomp.** Every stomp lands a hit (no silent refusal in the invincibility window), the bounce means it survived, and a killing blow drops you through. Enemies die in two beats: launched away, then burst.

## Roll, push, ladders and items

-   **The roll.** It passes through enemies (the i-frames make it a dodge) but not through crates or props, so you can no longer end up inside a crate. Rolling into a wall, tree or cupboard gives a small bump with a rattle; only the dash crashes. A jump buffered during the roll still wins at a ledge.
-   **Roll feedback added.** Rolls crash into stuff again (had this a while back and then removed it because I couldn't get it right). This makes some stuff shake. This may be helpful to you!
-   **Roll pass-through and i-frames.** I removed this a while back for same reasons as the roll crash. Wasn't quite ready for prime time at that point. Well it's back! But that led to…
-   **Made it so you can't roll into/through crates.** The roll pass-through makes it so you can roll past enemies. Enemies are classified as "Actors" in the code–that is, they perform actions. Guess what's also an Actor? Crates!! Therefore, crates are enemies. Your fears are real.
-   **No more crate stuck off its grid.** Speaking of crates. Certain situations left crates half-moved and un-pushable forever (and then the game saved it that way, rude). A push now always finishes, and there's some additional logic to rescue savegames with partially-pushed crates.
-   **No more pushing a crate while jumping.** A crate can be pushed from a step above or below it, but you gotta have your feet on the ground.
-   **Various colliders fixed so you can stop jumping on stuff and shortcutting the entire game.** Treasure chests, the ship's rails, and the maggot's cupboard and bookshelf could all be jumped upon. Their colliders are taller than a jump now.
-   **No more jumping up/off ladders when you can't jump yet.** In this case you'll just fall down instead.
-   **Hopefully prevented head bonks at wall corners.** I'd fixed a lot of this but it still happened sometimes. Hopefully it stops now!
-   **You can now jump off beds!** Jumping was getting swallowed by the "rest" code, which has been cut off for this game, so you'd just stand there. The maggot house bed is now plain furniture (resting in beds postponed).
-   **Treasure chests with tears in them now actually give you tears.** This is a holdout from when I was introducing some soulslike mechanics. I deferred those, but these were still additional items that you wouldn't lose on death and would help you level up. In other words, they did nothing for this episode lol.
-   **Trees are one unit wider on each side**, which should have prevented more ledgewalking but doesn't seem to have yet lol.
-   **Can no longer pick up** **items through walls.** No more phasing for you.
-   **Sword now cuts grass**, even though you can't do anything about this. There's no sword in this episode.
-   **Destroyed grass regrows on rest** to maintain the Zelda tradition. (Well and because it kind of sucks to have no more grass in the world lol)

## Camera, screens and visuals

-   **Better support for 4:3 and 16:10 monitors.** Narrower screens keep the 16:9 height and crop the sides instead of zooming the whole view out (I had actually been wondering about this on my main dev laptop which is 16:10). The dialogue box re-wraps to the narrower screen at the same text size, and the menus narrow rather than shrink. In theory, this should work on 21:9 too but I don't currently have a way to test.
-   **This should also fix tree shadows popping in at the bottom of a 4:3 screen**, since it was SO zoomed out. However I also updated the three systems that pinpoint where the center of the view is to hopefully prevent pop-in.
-   **The Darkeye's eyeball clipped through tree canopies.** It sorts properly against the tree now. Let me know if you still see this. He's a tricksy guy.
-   **No more player's toes showing under a house wall**. A stand-in sprite used for the see-through-walls effect drew a sliver of her in the black under the wall. Gone.
-   **Rolling across a stair corner** drew one frame of her inside the ramp. Fixed.
-   **Removed ending** **card after Replay > Quit > New Game**
-   **Added additional HUD hints when abilities are first available**. Some people missed entire abilities which is understandable. I want cryptic but maybe not that cryptic lol.

## Controls and menus

-   **Rebinding was a hassle and the second control set could not be turned off.** Delete or Backspace (keyboard) or Back (pad) clears a slot while rebinding and it stays cleared; an "alt bindings" row turns the whole second column off; keyboard and pad have separate resets; picking a pad layout no longer wipes keyboard rebinds.
-   **Steam Deck read no controls.** The game polled pad slot one only; Steam Input's emulated pad sat in slot two. It now follows whichever pad is talking.
-   **"Your saved game will be replaced"** **is now a proper dialogue choice** with a choice on the title screen, cursor on "Keep my game" by default since that's the non-destructive option.
-   **Mac and Linux builds!!** now both tested on real machines. Linux is live on Steam, Mac is in progress because of Apple's red tape labyrinth.

## Performance

-   **Audio hiccup** **when resting at the altar fixed (hopefully).** The night switch re-meshed almost the whole map's shadow geometry in one frame (0.6 to 0.9s) plus the visible color meshes (0.16s), and the first save of a session cost another 0.1s. The re-mesh is now spread over frames behind the closed iris, only for what the camera can see, and the save is warmed at boot. Let me know if you hear this - I couldn't ever get it to happen so I'm hoping optimization helped.
-   **Fixed half-second stutter on coasts.** Five ocean map chunks were fully rebuilt on every water animation tick, about 80ms twice a second when the ocean was in view, which is kind of insane.
-   **Prevented point-light shadows from rebuilt every frame at night** after the first day/night. Pretty hungry process.

## Other

-   **Foundation cavern reworked to be less punishing/confusing**. This room was designed before \[THE DARKNESS CONSUMES\] and didn't take that extra difficulty into account. Also, jumping was hard to judge because of the ocean/beach tiles used. The room has been updated accordingly! There is also intended to be more to this room, but that'll have to wait until the full game.
-   **Maggot's bed no longer counts as a save point**. No, you don't get to rest in beds this episode. Stop it. (Nobody actually did this since the code is turned off, but a friend testing kept respawning there when they died because I guess they touched the bed briefly or something.)
-   **Added a secret room**. I won't tell you which one. Some of you have found it. Some of you got stuck in it because the stairs out disappeared. That may end up being a real puzzle mechanic, so thank you for your efforts.
-   **Removed the village enemy**. I like there being a monster roaming around the outside of the houses, but this particular one caused too much game-breaking trouble. Maybe full game once I get a few more monsters coded.
-   **Interior windows no longer render in front of the player**. I know y'all like eldritch geometry, but you'll have to suffer without.
-   **Cupboard roll feedback.** People were getting VERY confused and trying to roll into the cupboard, which, fair. I put back a bit that I'd removed where the maggot lady gives you a small hint. I then added another fix so you couldn't cue up a bunch of the same hints by spamming the roll.

## Still open

-   Jitter walking diagonally along a wall.
-   Rolling up the forest ramp and ending "in the walls". Maybe a backrooms thing, idk, I haven't seen the YouTubes or movie. I may have fixed this but I can't tell.
-   OBS capturing only the menu in fullscreen. Some rendering shenanigans going on here, probably, but I haven't had the chance to repro yet.
-   Getting stuck between the maggot lady and her bed (not like that, stop it). There's some weird collision and idk why.
-   Wave decorations are a different color from the sea monster's underwater silhouette.
-   Various out of bounds holes around the edge of the world (Alexa, play [Edge of the Earth](https://www.youtube.com/watch?v=C-ToGfKJlEg) again). Mostly this will be tree collider touchup.
-   The open chest lock reportedly reads as "a black slime." More to come?
-   Can get a bit stuck behind the dead tree.
-   Bug in the grotto near the beginning where jumping around and walking around in the doorway you can fall off the map (Alexa, play [Edge of the Earth](https://www.youtube.com/watch?v=C-ToGfKJlEg) again)
-   You can finagle your way onto the rooftops of the houses (wait! this is intentional! I'm not fixing this! It shall remain open forever.)
-   Secret area that nobody has gotten to needs a way to get to, eventually, at least by the time the full game is out. (…or???)
-   Torch shadow running into the night and over the sea**.** Shadow tails stop at the edge of the light, and hopper shadows no longer flicker as they hop past a brazier.
-   Some really nasty iron fence shadows.
-   Player doesn't render when they're at southernmost edge of room, even in doors.
-   Further rebinding improvements: one set of controls for keyboard at a time, different presets available for quick choices for both keyboard and gamepad.
-   Dialogue scrolling vs full pages - should make for a bit more natural reading vs the hard page breaks right now.
-   Text that shows when you get the leaf will be made nicer

\*I have never asked Alexa to play a song for me.
