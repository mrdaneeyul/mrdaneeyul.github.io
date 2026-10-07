---
title: "Um wow you know that thing they say about how"
date: 2023-10-02 12:38:24 +0000
tags: ["rubber duck", "gamedev", "indiedev", "game development", "gamemaker"]
tumblr_url: "https://www.thewakingcloak.com/post/730071359337676800/um-wow-you-know-that-thing-they-say-about-how"
tumblr_id: "730071359337676800"
---

> Um... wow. You know that thing they say about how writing something down in detail can sometimes trigger a revelation? Within an hour of sending you that question, I fixed the problem: as I suspected, your script is perfect and does exactly what I needed it to do(and you'll be credited for it, I assure you!). After weeks of frustration and checking/doublechecking every bit of code and documentation, it suddenly occurred to me: what if GMS2's error reporting is misleading the direction of my troubleshooting? What if the error messages I keep getting are entirely arbitrary and not in any way related to the issue, even though they must be related in some way to the script (since it's the only script I'm using so far to utilize those layer functions)? What if the problem and the error messages represent an example of correlation devoid of causation, but I overlooked that possibility because the two began to appear at the same time? Well... yeah, that was it. Once I began to consider that possibility, I started going through related code and ended up slapping myself on the forehead rather roughly: I had forgotten that sprites created from surfaces aren't automatically drawn by the instances that create and assume them, and therefore neglected to specifically instruct the instance using draw_sprite. Once I did that, evrything worked brilliantly... such a simple solution. The debug report continues to throw those errors at me, and I have no idea why.... but my z-height objects are now skinning themselves as intended, so... thanks for the great code! Here's hoping this bizarre pair of messages from me will, at least, provoke a laugh... and I'm still looking forward to The Waking Cloak. cheers!

So glad you were able to figure it out and that everything is working! You’ve probably heard this before, but software engineering calls that “rubber duck debugging”, as in explaining your problem to a rubber duck usually helps you figure out the issue. I’m always happy to be a rubber duck lol

And yeah those layer error messages are weird. I think they’re just noise. I tried to resolve them back then but at this point I don’t even think about them anymore lol. Might be able to solve with a try/catch, except it’s not actually throwing an exception. They don’t seem to cause any issues either way!

Oh and don’t feel like you need to give me credit for a script. Happy to share 😁
