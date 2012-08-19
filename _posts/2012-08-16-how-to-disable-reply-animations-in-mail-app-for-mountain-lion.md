---
layout: post
title: How to disable reply animations in Mail.app for Mountain Lion
permalink: /2012/08/16/how-to-disable-reply-animations-in-mail-app-for-mountain-lion
---

{{ page.title }}
================

<p class="meta">16 August 2012 - Colorado</p>

I have been using this trick for awhile, and there is a lot of false information out there, so I figured I should post this for posterity.  To disable that super annoying reply animation in Mail (where it slowly fades into the center of the screen) – open Terminal or iTerm2 or whatever and type:

    defaults write com.apple.mail DisableReplyAnimations -bool TRUE

But wait! you say – I have seen numerous posts that say something similar. True dat – but they are all wrong (at least the many I saw). defaults for Mail (in Mountain Lion at least) is case sensitive – I was going crazy trying to get it to work, but they all said com.apple.Mail, which is incorrect – you need com.apple.mail.

Hopefully this saves you all some headaches.
