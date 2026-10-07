---
title: "Hi there if youre able to answer it i have a"
date: 2022-12-20 15:16:47 +0000
tumblr_url: "https://www.thewakingcloak.com/post/704170591655165952/hi-there-if-youre-able-to-answer-it-i-have-a"
tumblr_id: "704170591655165952"
---

> Hi there, if you're able to answer it I have a question about your z-height method. I've adopted your system into my game and am drawing the 3D platforms using tiles, not sprites - the z-height objects are being placed over tilemaps. Will this work with your method and depth sorting (z-tilt) or will I have to convert every platform to a sprite instead of using tilemaps? Just wondering what's going on in your game. Thanks so much in advance!

It really depends! For moveable objects (blocks, etc) or decorations (trees, etc) it’s a tilted sprite on an asset layer, or an object with a tilted sprite. For the most part I’ve got tile layers though, all set to specific depths that match the height they’re at. My main ground layer is -96, and a cliff of “16px above” that would be another layer at -112. The sprite asset layers also have depths set similarly. Hopefully that makes sense!
