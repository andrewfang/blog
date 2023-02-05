---
layout: post
title:  "How to control Rinnai water heater"
date:   2023-02-05 10:41:42 -0700
comments: true
categories: rinnai, water heater, smart home, alexa
description: Recirculate hot water via smart home commands
---

{{ page.description }}
<!--more-->

<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "HowTo",
    "name": "{{ page.title }}",
    "image": {
      "@type": "ImageObject",
      "url": "{{site.assets_dir}}/2023-02-05/alexa.jpeg"
    },
    "estimatedCost": {
      "@type": "MonetaryAmount",
      "currency": "USD",
      "value": "25"
    },
    "tool": [
      {
        "@type": "HowToTool",
        "name": "Echo"
      }, {
        "@type": "HowToTool",
        "name": "Rinnai tankless water heater"
      }, {
        "@type": "HowToTool",
        "name": "Rinnai wifi module"
      }
    ],
    "step": [
      {
        "@type": "HowToStep",
        "name": "Install the Control R Skill",
        "url": "/#using-alexa",
        "itemListElement": [{
          "@type": "HowToDirection",
          "text": "Install the Rinnai Control R Alexa skill"
        }]
      }, {
        "@type": "HowToStep",
        "name": "Configure a custom routine",
        "url": "/#using-alexa",
        "itemListElement": [{
          "@type": "HowToDirection",
          "text": "Set up a custom routine so that you can trigger the skill with a shorter phrase."
        }]
      }],
    "totalTime": "PT59M"
    }
  </script>

{% include affiliate.markdown %}

## Time needed
+ \< 10 minutes

## Materials
+ [Amazon Echo](https://amzn.to/40yzdhG)
+ Rinnai tankless water heater with [wifi module](https://amzn.to/3X6SQut)

## The story

I have a Rinnai tankless water heater that can recirculate water when I immediately need hot water. It's got a [wifi module](https://amzn.to/3X6SQut) hooked in which lets me recirculate water via the app or a [push button](https://amzn.to/3DKfemm). The button works fine, but I only have one of them and I couldn't justify spending $60 on another button. The app also works most of the time, but it's a little cumbersome to have to open the app and then navigate to the recirculate screen.

### Using Alexa 

I found that Rinnai actually has an Alexa skill. I have an [Amazon Echo](https://amzn.to/40yzdhG) sitting around, so I set this up. (The Echo dot is also cheaper than the Rinnai button, and can do way more). In the Alexa App, go to the "more" tab, tap on "Skills & Games", and search for Rinnai. Activate that skill and log in with your Rinnai account. 

However, after setting it up, I realized that I had to say "Alexa, ask control r for hot water" which was a bit awkward. I just want to say "Alexa, hot water". Turns out, there is a way to do this!

Back in the Alexa app, go to Routines, and create a new routine that triggers when you say "Alexa, hot water" (or whatever you want). Then, add a custom action with the phrase "Alexa, ask control r for hot water".

![alexa routine]({{site.assets_dir}}/2023-02-05/alexa.jpeg)

Now, you can just say "Alexa, hot water" (or whatever you set), and it will trigger the Rinnai Control R skill!

<div id="amzn-assoc-ad-d2735add-9dd8-4698-bd9d-ee7e2036e217"></div><script async src="//z-na.amazon-adsystem.com/widgets/onejs?MarketPlace=US&adInstanceId=d2735add-9dd8-4698-bd9d-ee7e2036e217"></script>
