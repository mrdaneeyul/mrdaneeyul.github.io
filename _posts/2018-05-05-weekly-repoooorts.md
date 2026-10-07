---
title: "Weekly Repoooorts"
date: 2018-05-05 14:00:39 +0000
tags: ["gamedev", "indiedev", "indiegame", "devlog", "devblog"]
tumblr_url: "https://www.thewakingcloak.com/post/173606567083/weekly-repoooorts"
tumblr_id: "173606567083"
---

Last week, I felt it was time to get back the ol’ momentum. Creative projects follow Newton’s Laws of Motion–projects at rest tend to stay at rest unless an outside force is applied to them, and once they get moving, it’s easier to stay moving. Even after I got back to working on the game after my burnout earlier this year, the project was still “at rest.”<br><br>One of the easiest, healthiest ways for me to keep inertia is to do one thing a day. Since I’m pretty limited on time, this allows me to sit down even for five minutes and get something, *anything* done. Usually it ends up being longer than that, and more than one thing, because starting is the hardest part. Once I’ve started, it’s easier to keep working.<br><br>In lieu of this “one thing a day” program (which has gone well so far!), I wanted to try out something new: **WEEKLY REPORTS!**<br><br>This was a lot less work than most blog posts, keeps things nicely documented, and holds me accountable. It’s pretty encouraging to be able to see exactly what’s been done.<br><br>These weekly reports won’t be anything fancy most of the time, but I hope you’ll find them informative and an interesting look into development. Keep in mind I only have an hour or so a day to work on the game, so cut me a bit of slack if it looks like I’m not doing much. :)<br><br>Dunno if this is a one-time thing or if I’ll continue posting these for all eternity, so we shall see.<br>

## Week of April 29, 2018

**Sunday**

Worked on the first draft of the Tiled overworld map. I have several major areas blobbed out with their main colors. The starting zone is probably about 40% done, and I’ve made good progress on the southern shores of the island too.

**Monday**<br>

Reverted a bunch of collision code that wasn’t working (I used PixelatedPope’s method but had to modify the player’s movement, which made it jittery). Instead I went down the path of trying to refine my precise collision checking function, but no luck. Going to undo that and try a middle ground with PixelatedPope’s method.<br>

**Tuesday**<br>

Added some Vector2 scripts thanks to PixelatedPope (again) and re-added much of his collision framework. We’re eventually going to use this to remove tile collision altogether.<br>

**Wednesday**<br>

Hooked movement up to the new collision. Pretty buggy–we’re back to sliding around like a maniac and being unable to stop moving unless we hit the single collision object in the room (which judders badly from certain directions), but I’m implementing movement better this time. Getting there.

**Thursday**

Didn’t have a lot of time today, but I fixed that bad collision judder AND the slippin’ and slidin’. Collision is much, much smoother than my original method, which would sometimes jitter during certain movements (especially the sword attack) due to using subpixels. Still plenty left to do though. For example, when you hit the top or left side of the slider, you’ll slide off of it even if you’re coming at it at a 90 degree angle.

**Friday**

Fixed diagonal speed so it’s no longer faster than horizontal/vertical speed (this was fine before, but I had to update it now that I’m doing movement a bit differently). Investigated the sliding issue–looks like it thinks the square collider is a diagonal collider!
