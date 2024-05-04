---
title: Installing the .gov.uk prototype kit
author: Mark Berthelemy
excerpt: A technical post about getting the prototype kit working in a mixed nodejs environment using nvm
layout: post
permalink: /2015/12/19/installing-gov-uk-prototype-kit/
tags:
  - Technology
thumb: /post-images/2015/12/gov-uk-ipad-thumb.png
banner: /post-images/2015/12/gov-uk-ipad-banner.png
alt: .GOV.UK site on an iPad
img-credit: <a href="http://alexw.me/ipad2/#!safari" target="_blank">iPad emulator</a>
---
As part of a new contract, I need to use the [GOV.UK prototype kit](https://github.com/alphagov/govuk_prototype_kit) - which is designed to enable people to quickly build out model applications and websites. I say "quickly", but you still still need to do a fair bit of hand-crafting...

It&rsquo;s a departure from my normal way of prototyping, based on wireframes, built in [Balsamiq](https://balsamiq.com/) or [OmniGraffle](https://www.omnigroup.com/omnigraffle). But, this way, the prototype is much more closely aligned to the finished product.

The prototype kit is built using [Express](http://expressjs.com/) - a [node.js](https://nodejs.org) framework for creating web sites. Which means you have to have node installed to be able to use it.

> Node is a brilliant concept - in that it uses Javascript on the server-side - meaning that you only need to learn one language. But that doesn't mean it&rsquo;s easy... When you start using node, you very quickly get into pretty complex territory!

However, the kit only works with node version 4.2.2 or 4.2.3, whilst node's most recent version is 5.2.0. If you come across issues during the prototype kit installation, then check your node version (node -v) first - as I found the installation fails completely without the right version.

The best way to deal with this, without downgrading your node installation, is to use Node Version Manager - aka [nvm](https://github.com/creationix/nvm)

This allows you to have multiple versions of node on your machine at once, and switch between them when working with different applications.

#### Step-by-step to use nvm (Unix & Mac)

In your Terminal, type:

    curl https://raw.github.com/creationix/nvm/master/install.sh | sh

This downloads the nvm package, and runs a set of commands to get nvm set up.

Now restart your Terminal.

Then type:

    source ~/.nvm/nvm.sh

This runs a few more commands. Without it, your system won't know where to find nvm.

Note that you can get this to run automatically when your Terminal starts up by adding it into your bash profile. ([.bash_profile](http://redfinsolutions.com/blog/creating-bashprofile-your-mac) on MacOSX)

To install node v 4.2.3 just type:

    nvm install 4.2.3

Then, after it&rsquo;s installed:

    nvm use 4.2.3

To see which versions of node you have installed, type:

    nvm ls

At this point, you can now follow the [instructions to download and install the GOV.UK prototype kit](https://github.com/alphagov/govuk_prototype_kit)

Once you&rsquo;re done, then use the documentation at [GOV.UK elements](http://govuk-elements.herokuapp.com/) to understand how to use the CSS.
