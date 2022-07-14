---
layout: post
title:  "How to control Tesla with Siri"
date:   2022-07-13 18:55:42 -0700
comments: true
categories: tesla, siri, shortcuts, automation
description: Performing Tesla controls (such as opening the trunk) with Siri via Shortcuts
---

{{ page.description }}
<!--more-->

## Time needed
+ \< 10 minutes (assuming you're familiar with how Shortcuts work)
+ \< 5 minutes if you want to skip over the story and go straight to the bottom to download the Shortcut

## Materials
+ iPhone running iOS 13+, with [Shortcuts](https://apps.apple.com/us/app/shortcuts/id915249334) and [Auth app for Tesla](https://apps.apple.com/app/id1552058613) installed
+ A Tesla car ([Don't have one?](https://ts.la/andrew11282))

## The story
One of the features that's missing from the default [Tesla](https://apps.apple.com/us/app/tesla/id582007913) app is the ability to make requests to the car via Siri. When I'm walking to the car with a cart full of groceries, I want to easily open the trunk without having to unlock my phone, open the Tesla app, then tap on the trunk button.

As of late 2021, Tesla's app now allows you to configure 4 quick actions, which also show up on the widget. These controls can be customized by long pressing on one of the four icons in the app. As you can see here, I've set mine to lock / hvac / trunk / frunk.

![tesla widget]({{site.assets_dir}}/2022-07-13/tesla_widget.png)

This isn't bad, but there's something to be said about being able to perform these actions without having to look at the screen. There are actually several apps out there that solve this problem, but they're all paid apps. I went in search for a free solution.

Enter [Shortcuts](https://apps.apple.com/us/app/shortcuts/id915249334). Introduced in iOS 13, Shortcuts lets you write custom workflows that can then be triggered by Siri, or even added as a widget on your home screen. People have done amazingly complex things via Shortcuts, and I actually found a wonderful [post](https://jordanmerrick.com/shortcuts/shortcuts-for-tesla/) by Jordan Merrick that showcases a bunch of shortcuts that do the exact things I want. I used this for a while, but recently, things seem to have stopped working (maybe because these Shortcuts use an unofficial Tesla API? 🤷🏻).

So, I did some more Googling. I came across [this article](https://tesla-info.com/guide/tesla-automation.php) by tesla-info, which introduces a service written by the folks at tesla-info to invoke what is probably another unofficial Tesla API.

Before I go further, I want to note that I'm not sponsored by tesla-info. I wish I were. Additionally, I haven't done a comprehensive investigation into the tesla-info APIs to make sure they're 100% safe, so let me know in the comments if you've found otherwise. Ultimately, in order for this to work, we're going to have to trust them with our authentication token.

Here's a blurb from the [tesla-info blog](https://tesla-info.com/tesla-token.php):

> In general, tesla-info does not like the idea of third parties having access to your tesla details including token. This put us in a moral dilemma as many owners want to make use of the unofficial Tesla API for various activities and as part of scripting.
>
> What we have come up with is the best compromise we can think of, we don't need your Tesla email address or password to generate your tokens, you use the Tesla login to generate an intermediate code we can use, and we don't store the resulting information.
>
> We have also created an approach to sending commands to your car using either the API or refresh token, these can be turned into Apple shortcuts or included in home automation. We still don't store your details and require you to send is either a valid API token or fresh token on every request. Obviously, you have to trust us here, but we are no different to any other application or web solution that uses your tokens, where we are different is that we don't store them and if our security is compromised, your details are not available to be taken.
>
> If at any time you feel the security of yours, ours or any third party that has ever had yo9ur details has been compromised or your token leaked, visit tesla.com and change your Tesla password.

Assuming we trust them enough, we can use the tesla-info APIs to ask our car to perform specific actions. The different commands are detailed in their [automation blog post](https://tesla-info.com/guide/tesla-automation.php).

Obviously in order to send commands to your car, you're going to need to be logged in. Recently, Tesla updated their 3rd party authentication to go through their SSO (single sign on) portal. For Shortcuts, I've found Kim Hansen's [Auth app for Tesla](https://apps.apple.com/app/id1552058613) to be exactly what I need. After downloading the app, sign in with your Tesla credentials and the app will store a refresh token and an access token. Now, instead of needing to pass your Tesla username and password around, you can simply use these tokens. In fact, this app exposes itself to Shortcuts, so you don't even need to worry about anything, just launch the app once, sign in, generate your token, and then let Shortcuts handle everything else.

Now, putting it all together, we can create a shortcut like this:
 
:-------------------------:|:-------------------------:
![]({{site.assets_dir}}/2022-07-13/shortcut_trunk1.jpeg)  |  ![]({{site.assets_dir}}/2022-07-13/shortcut_trunk2.jpeg)

(If you just want the shortcut without an explanation of how it works, skip to the bottom for the download link.)

In this example, we're asking the car to open the rear trunk. This particular command requires a `request`, as well as a `value`, though some other commands will only require a `request`. Note that the `Get Refresh Token` is donated by Auth app for Tesla, and that will deliver your token as long as you're signed in to that app. Once we have all these pieces, we simply need to make a request to that URL and that should trigger the action for your car.

One more thing. We'll need to give the shortcut permissions. Hit the (i) at the bottom of the Shortcut edit page and make sure it has all the permissions like so:

:-------------------------:|:-------------------------:
![]({{site.assets_dir}}/2022-07-13/shortcut_trunk3.jpeg)  |  ![]({{site.assets_dir}}/2022-07-13/shortcut_trunk4.jpeg)

Now, when you play the Shortcut, your action should be carried out and the request should be sent to your car. Even better, you can "Hey Siri ... Open Trunk" (or whatever you call your shortcut), and it'll perform that same request.

## Download
[Get the shortcut](https://www.icloud.com/shortcuts/3bdbb03cd79e44b686b1636e1f9b894c) & give it a try!