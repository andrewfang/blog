---
layout: post
title:  "How to add an outlet to a light switch"
date:   2022-07-16 18:55:42 -0700
comments: true
categories: electrical, outlet, switch
description: Changing out a light switch for a combination outlet + switch
---

{{ page.description }}
<!--more-->

## Time needed
+ \< 20 minutes

## Materials
+ Phillips-head and/or flathead screwdriver(s)
+ Needle nose plier (maybe)
+ Voltage tester (maybe)
+ Combination switch and outlet like [this](https://www.homedepot.com/p/Leviton-15-Amp-Tamper-Resistant-Combination-Switch-and-Outlet-White-R62-T5225-0WS/202035011) or [this](https://www.homedepot.com/p/Leviton-Decora-15-Amp-Tamper-Resistant-Combo-Switch-and-Outlet-White-R62-T5625-0WS/202027001)

## The story
Ever wish you had an outlet somewhere? I did — I wanted to put my vacuum cleaner in my closet, and have it be able to charge while it was in there. Sure, I could call an electrician to lay new wiring, but who knows how much that would cost. Fortunately for me, I have an light switch in my closet, so I searched the web for a way to reuse that, and I came across the combination switch and outlet.

![Combination switch and outlet]({{site.assets_dir}}/2022-07-16/combination_switch_outlet.png)

The concept behind this is quite simple — instead of just having electricity go through the switch in order to control something (in my case, a light), the current also goes in to power the outlet.

## The installation

> ⚠️ WARNING: Touching a live wire _can_ kill or seriously injure you. If you are unsure or uncomfortable about any part of the installation process, contact an electrician.

You don't need to be electrician to do this, but you should have some basic knowledge on how electrical wiring works.

Before we start, make sure you've turned off the power. Go to the circuit breaker and find the corresponding breaker to that part of your home (hopefully it's labeled well, otherwise it'll be trial-and-error — flip on the switch where you're doing the installation and try each breaker switch until the power to the switch goes off). Flip the circuit breaker switch off.

Next, use your screwdriver to carefully remove the cover from your light switch. Unscrew the screws holding in the existing switch. Pull out the switch, and then take note of which is the load, which is the line. If it's not labeled, you might need to get a voltage tester to verify (watch [this](https://youtu.be/gJpS0-5JQgU?t=68) to see how). Separate the wiring from the old switch (having a pair of needle nose pliers is useful here), and ready the wires for installation. Note: you should have at least one hot, one load, one netural, and one ground wire.

[The video](https://youtu.be/gJpS0-5JQgU) mentioned above is actually very useful to see the various ways the combination outlet + switch can be wired in. In my case, I wanted to have the outlet always on (so that the vacuum could charge), and the switch should maintain the same behavior (turns on/off the light). To do this, there's two ways (depending on the number of wires that you have available). In my case, the wiring I had available was 1 hot (black), 1 load (black), 1 neutral (white), and 1 ground (bare copper). Wiring instructions for this configuration can be found at [3:46](https://youtu.be/gJpS0-5JQgU?t=226). The wiring looks like this:

```
Hot --> Black "common" screw
Load --> Brass "A1" screw
Neutral --> Silver "N" screw
Ground --> Green screw
```

If you have two hot wires and want to this same thing, but on separate feeds, start watching at [6:21](https://youtu.be/gJpS0-5JQgU?t=381).

Other ways of wiring this together are:
+ The switch controls the outlet (switch flipped off == outlet off): start watching at [2:48](https://youtu.be/gJpS0-5JQgU?t=168).
+ The switch controls both the light and the outlet (switch flipped off == light off AND outlet off), start watching at [5:05](https://youtu.be/gJpS0-5JQgU?t=305)

Once you have the wires connected to this new combination outlet + switch, screw this back into the wall and reattach the wall plate.

Celebrate!

![Installed vacuum and outlet]({{site.assets_dir}}/2022-07-16/completed.png)