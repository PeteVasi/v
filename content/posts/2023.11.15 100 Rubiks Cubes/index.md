---
title: "100 Rubik's Cubes"
date: 2023-11-15T20:00:00-05:00
draft: false
summary: "Dynamic wall art."
---

Awhile ago I had the idea to take Rubik's cubes and build pixel art out of them.  When thinking
about how to make a more interesting Zoom background, I stumbled upon [Twist
Pixel](https://twistpixel.com/) and decided to give it a try.

{{< lightbox src="many-cubes.jpg" alt="A collection of many Rubik's Cubes on a table" layout="center" >}}

They looked great, so it was time to make a frame to fit.

{{< flexwrap >}}
    {{< lightbox src="wood-frame.jpg" alt="An unfinished wooden frame" >}}
    {{< lightbox src="painted-frame.jpg" alt="A painted wooden frame" >}}
    {{< lightbox src="cubes-in-frame.jpg" alt="Some Rubik's Cubes filling up the bottom of a frame" >}}
{{< /flexwrap >}}

Getting them all put together was fun too, I've gotten quite good at solving exactly one side of a
cube.  So far I've changed the design out monthly, we'll see how long I keep up that pace. 

{{< flexwrap >}}
    {{< lightbox src="cubes.2023.08.jpg" srctype="global" alt="Rubik's cubes as pixel art of Link and an Octorok from Legend of Zelda" >}}
    {{< lightbox src="cubes.2023.09.jpg" srctype="global" alt="Rubik's cubes as pixel art of the TCG logo for the TCGbay Hackathon 2023" >}}
    {{< lightbox src="cubes.2023.10.jpg" srctype="global" alt="Rubik's cubes as pixel art of Simon Belmont and a red skeleton from Castlevania" >}}
    {{< lightbox src="cubes.2023.11.jpg" srctype="global" alt="Rubik's cubes as pixel art of the back of a Magic: The Gathering card" >}}
{{< /flexwrap >}}

To assist with cube setup, I put together a little brute-force bash to take a 30x30 pixel image and
break it out into cube slices:
```bash
#!/bin/bash

convert $1 -scale 1000% o_r.png

convert o_r.png -background black \
  -splice 2x2+290+290 \
  -splice 2x2+280+280 \
  -splice 4x4+270+270 \
  -splice 2x2+260+260 \
  -splice 2x2+250+250 \
  -splice 4x4+240+240 \
  -splice 2x2+230+230 \
  -splice 2x2+220+220 \
  -splice 4x4+210+210 \
  -splice 2x2+200+200 \
  -splice 2x2+190+190 \
  -splice 4x4+180+180 \
  -splice 2x2+170+170 \
  -splice 2x2+160+160 \
  -splice 4x4+150+150 \
  -splice 2x2+140+140 \
  -splice 2x2+130+130 \
  -splice 4x4+120+120 \
  -splice 2x2+110+110 \
  -splice 2x2+100+100 \
  -splice 4x4+90+90 \
  -splice 2x2+80+80 \
  -splice 2x2+70+70 \
  -splice 4x4+60+60 \
  -splice 2x2+50+50 \
  -splice 2x2+40+40 \
  -splice 4x4+30+30 \
  -splice 2x2+20+20 \
  -splice 2x2+10+10 \
  o_r_s.png
```
