---
title: "ProtoDungeon: Episode II"
date: 2019-08-19 17:26:43 +0000
tags: ["gamedev", "indiedev", "devlog", "devblog", "game development", "The Waking Cloak", "prequel", "ProtoDungeon"]
image: "/Images/devlog/2019-08-19-protodungeon-episode-ii.gif"
alt: "ProtoDungeon: Episode II"
tumblr_url: "https://www.thewakingcloak.com/post/187122665479/protodungeon-episode-ii"
tumblr_id: "187122665479"
---

Hey all!

ProtoDungeon Episode II (TWC prequel) is coming along nicely, and I’m building out a lot of vital systems for it, future episodes, and The Waking Cloak. I also began a sort-of-daily update on the [Discord server](http://discord.gg/thewakingcloak) that I’ve been meaning to post here but keep forgetting to because I am a scattered, scattered person.

Anyway, uh, yeah, there are a lot of these, lol. I’ll try to post these more regularly in the future, but I hope this is fun and informative for those of you who like reading weirdly specific details about gamedev.

**Daily Update - May 24, 2019**<br>

Summing up what I’ve already done before today:<br>-Ring mechanics are done<br>-Day, night, and light sensors are done (though don’t have any art)<br>-Created an object that will switch day/night

Today:<br>- Reworking my “interaction” code so that you stop walking after interacting with something during the walk state.

**Daily Update - May 25, 2019**<br>-Finally resolved the “interact” code by adding a new player state. Now the player actually stops when interacting with objects instead of just walking into them the whole time.<br>-Fixed a small bug where dialogue boxes would show up with the first message already “fast-forwarded” to the end with no sound.<br>-Started working on polishing up the day/night switcher object (this is what the interact code was for). Should be important in this dungeon since the player won’t have the cloak!

**Daily Update - May 26, 2019**<br>-I tend to take Sundays easy. I worked on a bed sprite for like ten minutes though!

**Daily Update -  May 27, 2019**<br>-Added the ring and its upgrades to the test room! We’re now technically ready for super early patron alpha testing, which I’ll put up sometime in the secret patron channel in the next few days!

**Daily Update - May 28, 2019**<br>-Set up the Itch build for pre-alpha patron testing<br>-Worked on figuring out how to clarify the day/night and ring mechanics, visually<br>-Began sketching out dungeon layout, now that I have mechanics set (as opposed to Episode I where I had to retrofit my design a few times after it was mostly done).

**Daily Update - May 30, 2019**<br>-Finished the rough draft of the dungeon layout!!!

**Daily Update - May 31, 2019**<br>-Finished the second draft of the dungeon map, including several more detailed rooms with puzzle designs

**Daily Update - June 1, 2019**<br>- Finished the THIRD draft of the dungeon map, think I’ve finally got the layout and puzzle locations pretty much settled (it’s been a toughie with day/night/dayshift/nightshift)

**Daily Update - June 3, 2019**<br>-Updated level 2 of the Ring of Starlight to generate two blocks instead of one block with a dayshift/nightshift effect. This is like what was originally level 3, except the blocks will move in sync with each other<br>-Changed the ring upgrade descriptions. I’m going to try for a more lore-based, somewhat poetic approach for these over a mechanical explanation. (Level 3 is obviously a temporary description)<br>-Pushed the build up to Itch as v0.3.0

For those of you who have access to the pre-alpha and are using the Itch client, updating should be very easy! However, since something got renamed somewhere along the line, you will most likely have to remove the previous version of the game if you don’t want it to ask you to select your version when launching the game. I don’t think this will happen again… probably. :)<br>I’m still working on the level 3 mechanic, also.

**Daily Update - June 5, 2019**<br>-Decided on new lvl3 of the ring<br>-Fixed blocks so they now fall into pits. Long live the king.<br>-Updated Itch app to v0.3.1

**Daily Update - June 7, 2019**<br>-Added level 3 of the ring.<br>-Fixed a bug where pushable blocks couldn’t be pushed. You had one job, pushable blocks.<br>-Fixed a bug where the player wouldn’t fall into a pit after swapping with something that’s over the pit.<br>-Fixed a bug where the synced level 2 ring block would not collide with objects when starting from “rest”.

**Daily Update - June 8, 2019**<br>-Fixed bug where the dialogue box would crash sometimes. I fixed this bug before. I don’t know why it came back. The code I used to fix it was gone. Will keep an eye on this code to see if it disappears again.<br>-Updated HUD to display ring and ring level instead of scroll and swap spell level.<br>-Fixed the controls. Space was mapped to both item “A” and item “B”, and apparently it doesn’t work that way when the item isn’t mapped to both slots :P<br>-Fixed a bug where the game would be very, very tiny if it was not in focus when starting in fullscreen mode. I commented out a line of code when updating the application surface resizing and forgot to uncomment it.<br>-Updated v0.3.9 to Itch<br>-Started work on the next draft of the dungeon sketch now that the ring mechanic has been finalized wooooo

**Daily Update - June 12, 2019**<br>-Competed new draft of the dungeon, pretty happy with this one. I’ll just need to work in the puzzles and make sure the dungeon graph (a la GMTK Boss Keys) works out so players can’t get stuck.<br>-Fixed an issue where you could push blocks past the edge of the screen (and a related one where when you tried to do that, you would keep moving through the block while the block stayed still).<br>-Fixed an issue where you could create blocks on top of each other.

**Daily Update - June 14, 2019**<br>-Started working on Tiled draft of dungeon<br>-Began experimenting with larger default room sizes. One aspect I liked from Blossom Tales. Still keeping rooms, of course, since that’s what counterintuitively makes an overworld feel big, but bumping up their width/height by about 50% each makes them feel that much larger and explorationy.<br>-Updated test room to new room size.<br>-Uploaded v0.3.12 to Itch, which includes the new room size, as well as the fixed bugs from the June 12 daily update

**Daily Update - June 16, 2019**<br>-Continued working on Tiled draft of dungeon. Slow work at this stage, but I believe the overall layout is complete.<br>-Started laying out my sticky note version of the dungeon and puzzles. Lots has changed since last time I built puzzles for this dungeon, so reworking it has been fun.

Trying to decide whether the blocks should stay put when you move out the room, or disappear like the Cane of Somaria. Persistent blocks would make for some interesting puzzles.

Also trying to decide how the overworld will map down to the dungeon, since some of the dungeon rooms are a bit small and constrained. I’d like them to line up. Might still make them the same size as the overworld rooms, just with long connecting bits.

**Daily Update - June 18, 2019**<br>-Puzzle design is done! <br>-Tiled map draft is coming along much faster now that I know what to fill the rooms with. Already making tweaks to the puzzles (and I’ll certainly make more tweaks when building in GameMaker, just how it goes)

**Daily Update - June 19, 2019**<br>-Tiled map draft is almost done! Getting verrrry close now.

**Daily Update - June 21, 2019**<br>-Tiled map draft is COMPLETE!!!

**Daily Update - June 23, 2019**<br>-The actual dungeon in GameMaker is underway and making quick progress. Already improving on the Tiled map, I think! Could be done with the graybox and have it playable for patrons by the end of the week–stay tuned.<br>Lemony Snicket voice *“Graybox” here means “with crappy programmer art and white/black tiles”*

**Daily Update - June 24, 2019**<br>-Made major headway on the dungeon in GameMaker. Very close to wrapping up the graybox tiles, and I’ve made a bunch of refinements to the existing layout and puzzles!

**Daily Update - June 26, 2019**<br>-Layout and graybox tiles are done<br>-Colliders are done<br>-Cliffs are done<br>-Stairs are done<br>-Pits are done<br>-Item upgrades are placed<br>-Some keys are placed<br>-Buttons are placed (not hooked up yet)

**Quasidaily Update - June 27, 2019**<br>-Worked on hooking up buttons and bridges and simplified the lvl1 ring room (for me, should be about the same for the player)

**Quasidaily Update - June 28, 2019**<br>-Finished doors and hooked up buttons<br>-Fixed various puzzles and rooms that weren’t working correctly

**Quasidaily Update - June 39, 2019**<br>-Finished the ladder!<br>-Finished bridge collision<br>-Completed… the trap room<br>-Hooked up the doors/buttons I missed (pretty easy to find since I use a red color blend on the offending buttons ingame)<br>I… uh… am just gonna leave that as the 39th<br>Very very close to alpha now, unless those two bugs end up just crushing me

**Quasidaily Update - July 1, 2019**<br>-Added day/night blocks<br>-Added a missing teleporter (int/ext door)<br>-Fixed one of the two softlocking bugs (in about 5 minutes)!

Remaining before patron alpha release:<br>-Secret thing<br>-Second bug<br>-Verification that the dungeon is playable from start to finish

**Quasidaily Update - July 2, 2019**<br>-The second bug is technically fixed, but it’s pretty janky and unpolished. I’ll keep working on this tomorrow.<br>-Cleaned up and optimized the block pushing check logic, which had all kinds of duplicate collision checks and wack timers being set all over the place

**Quasidaily Update - July 3, 2019**<br>-Finally fixed the second bug. This was a block syncing/pushing issue that would’ve prevented everyone from completing the dungeon<br>-Began testing the dungeon’s playability from beginning to end. Ran into a few more things I fixed:<br>    -Added a level 3 ring upgrade description since it actually does something now<br>    -Some bridges were missing pits under them, so you could walk across even if the bridge wasn’t activated.<br>    -Discovered the level 1 and 2 ring blocks don’t fall in pits anymore. Oops. Gotta fix this still.<br><br>**Quasidaily Update - July 3, 2019 PART 2**<br>-The dungeon is playable from start to end (except you can’t get in the final room yet, but that’s a quick fix)<br>-Hooked up MORE buttons/doors that I had missed<br>-Replaced/moved the keys around–I think this will be much more satisfying now<br>-Added the method to get to t h e    s e c r e t<br>Pretty pleased with it this time around–I think it’s even more cryptic and fun to discover ehehehe<br>“ehehehe” is to be read with a witch’s voice

**Quasidaily Update - July 4, 2019**<br>-Tweaked t h e s e c r e t entrance ほほほ<br>-Worked on t h e s e c r e t puzzles…. they’re pretty devious お~~ほほほ

**Quasidaily Update - July 5, 2019**<br>-Fixed broken challenge puzzle.<br>-Fixed bug with lv1 and lv2 ring mechanics–they weren’t falling down pits anymore. That just makes this game way too easy.<br>-Fixed a bug with lv3 ring blocks that was also breaking the challenge puzzle<br>-Added some tiles to cover up my greybox “answers”<br>-This wraps up all the changes for alpha. We’ll go live with the alpha for patrons early tomorrow!

**Quasidaily Update - July 6, 2019**<br>-Released the patron alpha! Woohoo! Rali has been enjoying it at least/<br>-Released v0.4.2 update:<br>    -Fixed two unmarked pits. Kinda sucks to fall into the solid ground.<br>    -Game Over now resets only the player, not the entire game.

**Quasidaily Update - July 7, 2019**<br>-Released v0.4.4 update:<br>    -Added collision around water bridges so you can’t walk on or get trapped on the water…<br>    -Removed a call to GMLive that may be causing a crash on the PlayerEquipmentRingState script.**<br>**

**Quasidaily Update - July 7, 2019 PART DOS**<br>Released v0.4.10 update:<br>-Removed “You got a key!” text because… well, it should be obvious.<br>-Do not freeze player on headstone moving.<br>-Fix stutter when a level 0 equipped item is “used.”<br>-Made it so you can’t push jars and blocks up stairs. They are TOO HEAVY.<br>-Added an escape route to the challenge room so you don’t have to throw yourself in a pit to get back to the start if you get stuck. It doubles as a “skip” for one of the puzzles once it has been opened.<br>-Fixed challenge room exit so you don’t get trapped. :)

**Quasidaily Update - July 9, 2019**<br>-Fixed colors on the east/west player “use ring” sprite so that the night palette shader doesn’t miss it (meaning it would render her skin in the day palette)<br>-Updated teleporters to use channel strings so I don’t have to manually set the target coordinates for ALL THE TELEPORTERS AAAAAAAH.<br>-Oh, and yeah, most importantly: released v0.5.0 update! Completed dungeon remodel!! It uses the build-a-final-key method like in Episode I. This allowed me to make the dungeon a bit less linear. It also meant I knocked down a wall or two, added another puzzle or two, and all around made something I’m much more satisfied with.

**Quasidaily Update - July 10, 2019**<br>Released v0.5.5 update!<br>-Fixed a crash when attempting to push arrows (read: moving toward an arrow while it’s trying to kill you).<br>-Toned down the arrow knockback effect<br>-Fixed awkward/slow interaction with arrows knocking you into pits<br>-Shortened room respawn freeze time<br>-Fixed a bug where the player could walk directly into the arrow and avoid taking damage. Pretty sure that’s not how arrows work (this was related to the pushing bug above!).

**Quasidaily Update - July 11, 2019**<br>-Starting to place actual tiles over the greybox tiles and gosh it’s nice to have real art.

**Quasidaily Update - July 12, 2019**<br>-Majority of the final tiles have been placed and it looks great. I still need to make a few interior wall sets and a handful of floor tiles.<br>It really brings the dungeon to life

**Quasidaily Update - July 14, 2019**<br>-Released v0.6.0!!! I’m very excited about this one because it’s the first of the graphics updates. The majority of the basic final tiles have been placed. There are more graphics updates to come (which you’ll note if you play this version), but is the biggest of ‘em. Looks great in day and night!

**Quasidaily Update - July 15, 2019**<br>-Added new one-way-jump wall tiles<br>-Completed secret room tiles and decorations<br>-Added lighter tall grass

**Quasidaily Update -  July 16, 2019**<br>-Today was a writing day, mainly. I’d like to have the little snippets of dialogue and bookshelves and so on done in a day or two. It’s exciting stuff, showing off the tips of all these icebergs.<br>-Last night I pushed v0.6.4, an update that had lots of good graphics updates. Except I forgot to replace the player back at the start of the level after testing, so neipo had some fun times starting at the END of the level. Fixed and uploaded in v0.6.5!

More!<br>-Uploaded v0.6.6 in which I fixed an arrow issue that I already fixed previously. Except, I had only fixed it for ProtoDungeon I. Which is why @neipo13 ran into it to my great confusion.

More!!!<br>Uploaded v0.6.8:<br>    -Fixed one of the lvl3 ring puzzles so it didn’t have a ridiculously easy solution (thanks for finding that, neipo).<br>    -Fixed description of round key.

**Quasidaily Update - July 17, 2019**<br>I intended to do some writing today, but I got more excited about something else…. sooooo, cue the upload of v0.6.13 - The Optimization Patch! - in which the average framerate on my dev laptop is now 260fps up from 120fps.<br>  -Moved the half-speed/GIF mode to only be available in debug mode (this was “G” on the keyboard, so people could just press it and not be sure why the game was running so badly).<br>  -Scott’s [regular & mod on the server] lappy had major framerate issues running the game, so I did some optimization and found out the pits were accounting for 50% of the time of every single frame. The best part: they only needed to run the offending code ONCE. So I moved that code from the step event to a one-time event and voila, framerate is way more stable.<br>  -Turned off GMLive entirely and added an easy toggle for me. This is very useful during development, but it likes to make lots of calls when turned on.<br>  -Updated the “listener” step event, which was setting a blend mode every single step. In debugger mode, this is so that stuff like buttons and doors turn red if they’re not hooked up. Otherwise it “unsets” the blend mode by setting it to -1 every single step (regardless of debug mode). Apparently this has some unexpected overhead, even if the blend mode is ALREADY -1. A quick and easy fix.<br>  -Swapped out the existing (non-moving) tombstone objects for different objects. Almost all of the tombstones were instances of the same object as the ones that move, but that came with a lot of additional overhead (my “listener” object still accounts for a lot of time because it’s doing some checking with ds_lists every frame for every listener object; the moving tombstones have listeners, the normal tombstones do not). They’re behaving themselves now.

**Quasidaily Update - July 18, 2019**<br>Uploaded v0.6.14!<br>  -Fixed up collision in the secret room<br>  -Finished secret room lore dialogue

There’s still more writing to do for the headstones, bookshelves, and a certain NPC who isn’t in the game yet, but yeah! Getting there!

**Quasidaily Update - July 20, 2019**<br>Over the last day or two, I’ve slowed down a lot–think I’m getting close to burning out, plus not certain I’m satisfied with the story implementation thus far in Episode II (am I too obscure? Revealing too much? Will people care? etc). That said, I’ve gotten some stuff done, and uploaded v0.6.19<br>  -Fixed some borked collision near the hut (thanks for finding that, Rali)<br>  -Fixed tombstones so they could display text<br>  -Added text to various tombstones >:) (and bookshelves)<br>  -Fixed the interaction check so that you don’t interact with objects to the north of you when facing to the east or west.

Today I switched gears and created a batch file that could compile an executable without even opening GameMaker!! This is actually pretty exciting. I could almost, at this point, switch completely to GMEdit, which is significantly faster and more intuitive tham GM workspaces.<br>Oh, and the batch file also uploads the compiled exe to Itch

**Quasidaily Update - July 20, 2019**<br>I decided to switch gears again and work on the save game feature. Not done yet, but it IS saving the player/inventory objects, and I’m setting it up to be pretty easily able to take in any set of objects, auto-read all their variables, and set 'em.

**Quasidaily Update -  July 22, 2019**<br>Been working on the ol’ save system still. It’s going well. I had to fight a bit with my camera system (like always lol), and now I’m making sure the ring blocks properly reset–currently they crash the game which isn’t quite right…

The system as planned for PDII will essentially be an autosave that triggers on entrance of each room. When loading the game, all solved puzzles should remain solved, and ring blocks should remain in place, and you’ll appear at the entrance of whatever room you exited the game from.<br>At some point in a later episode I’ll include slots and specific save points not unlike bonfires from Dark Souls

**Quasidaily Update - July 23, 2019**<br>Saving and Loading Continued<br>Cleaned up the loading–it would snap you back to the load point and the camera had trouble keeping up. Now it’s a nice, clean fade transition with no camera moving around.

What’s left:<br>-Properly saving blocks and other puzzle elements. Currently it, uh, duplicates them? So that’s nice.<br>-For some reason, the ring itself disappears when you reload the game<br>-Need to set up the fadeout transition so it finishes before puzzle elements get reset and the time of day changes<br>-Set up an autosave on room enter<br>-You can actually get stuck in the first ring room by crossing a bridge and having that bridge disappear behind you, then quitting and loading your save. I’m trying to think of a good way to solve it now and in the future without making it easy to miss setting up something manually.

**Quasidaily Update - July 25, 2019**<br>Moar Savingz<br>Ring blocks are finally managing their own order, and it’s wayyyyy more stable and uses a ton less code than before. Previously, during the player’s “use ring” state, it would call the inventory manager to update the order of the blocks, which it stored in two variables. It worked, but occasionally the order would get really weird and so on, plus it was going to be a nightmare for reloading. The problem is that the inventory manager was holding the ring block IDs in those two variables, and IDs are not guaranteed to be the same on re-run.

Solution: ring blocks get an integer variable that stores their order, called order. When a ring block is created, it tells the other block to update its order. If that order is already 2, destroy it. Simple, and easy to save since it’s an int.

**In a pre-quasidaily update today**<br>Daniel learns why his ring blocks aren’t loading<br>They are<br>And then they’re instantly destroying themselves<br>Because of the code he wrote<br>To tell them to destroy themselves<br>Thank you

**Quasidaily Update - July 26, 2019**<br>Uploaded v0.6.22, possibly the final 0.6 version since saving is coming sooooooooooon. BUT. Here’s what you guys get:<br>    -Fixed some more collisions near the hut (seriously, did I move that entire room over one tile somehow)<br>    -Allow jumping off ANY ledge (WOOO)<br>    -Fixed occasional crash when creating ring blocks

The save/load system is working also, but not available outside of debug mode yet! As far as I can tell everything is saving and loading properly as expected. There are a couple places you can save scum past, and I have a few ideas for handling those, but that probably won’t be something I deal with for a bit. However, the player is not currently able to save or load (unless they’re in debug mode, as mentioned), which leads me to the next major update I will be working on: M E N U S  and  O P T I O N S

**Quasidaily Update - July 27, 2019**<br>I’m 25 minutes through a 70 minute series by FriendlyCosmonaut on a menu system. This is a lot lol.

In the process, I did a little bit of reworking/cleaning on my controls system. I now have some global variables that hold all the currently configured controls, instead of hardcoding the controls into the input manager. This was in preparation to allow control remapping!

**Quasidaily Update - July 30, 2019**<br>Been quiet for a few days–hard at work on the new menu system. This one is a doozy, you guys. I haven’t done this much straight code on the TWC “engine” since Episode I…. maybe even longer.

Finished the FriendlyCosmonaut series, which was a great foundation. Now I’m building off it (and trying to get tons of parts of it to actually work still). I’d ideally like to have it look a lot like the old mockup from my blog post on difficulty settings (many of those difficulty settings will not be used in ProtoDungeon or TWC).

Here’s what I got so far. Still a lot of the FriendlyCosmonaut design in this, which is good, but doesn’t quite fit with this game.

brightness/contrast do nothing, window actually works pretty well–unless you change the smoothing size, in which case it starts acting up…

vsync…. I think works?<br>I haven’t even tried toggling screenshake<br>I want to use the “bouncing arrows” style from the mockup instead of color, fix the on/off to use arrows instead, fix the sliders so they use pixel arrows instead of drawn circles….<br>so much left to dooooo<br>I just have to remember it was loading a black screen this morning

**Quasidaily Update - August 7, 2019**<br>Been alternating between taking breaks and working furiously on menu stuff, as you can see with screenshots.

Spending a lot of time on remapping. There’s a lot to polish here, stuff you might not think about on first glance (What happens if a key is already mapped to another? Do you handle the menu not closing while you’re remapping the menu key? Do you handle the menu so it doesn’t navigate when mapping the back key? Do you include primary and secondary control sets, and if so, how do you display that clearly? Etc.)

Not all these questions have difficult answers, but they add up. So that’s basically all I’ve been working on for the past week or so :)

Today I got the gamepad up and running and the secondary control set as well. I forgot how good it feels to play the game with a controller vs a keyboard. My wife happily exclaimed “You’re playing with a controller!” :D

The secondary control set was a back and forth decision. The deciding factor was mainly wanting to ease the initial “time to start” for different players–so you can move with WASD and the arrow keys, or with the dpad and the stick. I have a pretty good idea how the UI will work for this too, so now that the gamepad is working, I’m gonna start on the secondary controls.

**Quasidaily Update - August 11, 2019**<br>-Primary and secondary gamepad button remapping are working<br>-Got some cool new gamepad icons, improved thanks to Corvos<br>-Fixed the menu so you couldn’t close it on the menu page when starting the game<br>-Added a second, ingame menu with resume/settings/save & quit as options<br>-The new menu will pause all “actors” (objects with states)<br>-Fixed a bug where the secondary gamepad right input was not mapped

**Quasidaily Update - August 13, 2019**<br>-“Defaults” option now works for keyboard and gamepad<br>-Fixed an issue where you couldn’t remap some of the secondary keyboard inputs (broke it with the gamepad remapping).<br>-Fixed an issue with the menu arrow being in the wrong place (broke it with the gamepad remapping).<br>-Removed light blue coloring on selected menu items. Judging by other menus, arrow seems to be enough by itself.<br>-When remapping, the current selected control will now blink instead of remaining static.<br>-Made sliders more usable–it wasn’t really possible to move them 1% at a time, which was unwieldy and annoying. Now they have a “ramping” speed and are much easier to control.

**Quasidaily Update - August 13, 2019, Part II**<br>-Toned down the strength of the brightness slider just a bit.<br>-Updated the shaders to affect the GUI as well as the game. This should include the menu as well as the HUD, the dialogue box, and, in TWC, the inventory screen. I kinda like this. We’ll see if it bothers people. :D

**Quasidaily Update - August 17, 2019**<br>-Fixed an issue with menu sliders not being drawn when the shader is applying to GUI elements. Turns out the built-in line drawing doesn’t pass texture information to the shader. At this point I’m not sure how to configure the shader correctly, so I just made the lines into sprites instead lol.<br>-Added title to the top-level menu! Yay!<br>-Fixed game loading so it would load the correct room (both GameMaker room and in-game “area”).<br>-Autosave the game on room entrance.<br>-Autosave the game on getting an item (this way you can’t cheese certain rooms). At this point, playing the game, quitting, and coming. back to continue is working REALLY WELL.<br>-No longer save “region” (rooms in the game) objects, since these get created and setup perfectly fine on room creation.<br>-Added SOME SECRETS YAY!<br>-Autosave the game on “teleporting”–going through doors, up/down stairs, etc.<br>-Fixed the “circle out” transition, which was apparently not working or used anywhere.<br>-Changed all “teleportation” to use circle-in/circle-out transitions–a little less visually jarring and much nicer looking than a fade-to-wipe-from-center.

**Quasidaily Update - August 19, 2019**<br>-Added tiny pause in the middle of the teleportation transition so that it’s a bit less jarring<br>-Simultaneously, allowed toggle to camera easing so that I don’t have to add fragile pauses to loading and certain transitions and so on (to wait for the camera to finish moving to catch up with the player loaded position). This fixed a small camera jerk when loading the game. This will eventually be an option on the menu for those that don’t like the easing (and also because turning off subpixels makes camera easing REALLY BAD).<br>-Fixed issue with audio groups not loading (by loading them, wow). This is probably temporary since next big task is to add the Wandersong audio engine, but the fix let me actually see my debug messages instead of spamming “Audio Group 2 is not loaded” whenever a sound is played lol.<br>-Fixed bug with loading the game on a teleporter (doors, stairs, etc.) where it would immediately take you to the target location. This had multiple parts, but namely 1) just making sure to set the global “isLoading” flag and to not teleport during that, and 2) setting the “isLoading” flag earlier, since the teleporters were faster than my load manager lol.<br>-Fixed “New Game” issue where it would fade to black, start the game, and then fade to black again. Turns out if you call “fade out” twice, it will fade out twice.
