---
title: 'Review: Xerte authoring tool'
author: Mark Berthelemy
excerpt: A look at this open source, server-based content authoring system
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/03/24/xerte-review
img: 
imgalt: 
imgcredit: Mark Berthelemy
tags:
  - Open source
  - Content management
  - Reviews
---
The more I play with [Xerte](https://www.xerte.org.uk/), the more I realise how powerful it can be in the right hands.

## Introduction to Xerte

Xerte is an open-source, multi-user, server-based content authoring and delivery sytem. It's come from the university sector - with the main development team based at the University of Nottingham. But don't let that put you off. I've seen it used very successfully in a commercial "Teaching English as a Foreign Language" setting.

Digging into some of those words a bit... By **open source** we mean that the code in which the application is written is available for anyone to examine. You'll find it on [Github](https://github.com/thexerteproject/xerteonlinetoolkits). But not only examine. You can also download and modify it freely.

It's **multi-user**. It's designed for settings where you'll have lots of people creating and reviewing content. In that respect, it's playing in the same space as tools like Dominknow and Elucidat, but without the huge price tags.

It's **server-based**. There's nothing for the end-user to download or install. Everything is managed and stored on the server. You could, if you wanted, install it on your own computer - as long as you've also installed the necessary software to run a web server, PHP scripting and a database. So, it's a bit technical, but you don't have to be a superbrain to do it.

Most people will be using Xerte through some sort of hosted server setup, like a shared hosting provider or an institutional IT team. Unlike a lot of modern server software, it's actually pretty straightforward to do, even on the cheapest hosting package. No need for Docker or shell access.

It's a **content authoring system**, by which I mean it's a simple way to create web-based content without needing to know any HTML, CSS or Javascript. Now, I'd always argue that you'll get better results if you can work in those languages, but for most of us, an authoring tool is a shortcut to quick results.

Xerte can create three types of content:

- "Traditional" elearning packages, based on a series of pages, each one built using one of over 60 templates. These are great for creating instructional content. The packages can be delivered directly from Xerte or exported in various formats to go into a Learning Management System (LMS).
- Responsive website, with far fewer templates. Perfect for creating hubs for courses or for documentation.
- Decision tree, designed to take you through a process to reach an end conclusion. It's ideal for branching scenarios.

Xerte encapsulates the positives and negatives of open source software. There is so much about it that is really good, but it's let down by the sorts of things that would rarely happen in the commercial world.

## Good points

- It's meeting the needs of its target audience - remember these will be mostly teaching academics, needing to create lots of content in a very short time.
- It's powerful and flexible - at every point in the authoring process you're given the option to dig deeper and change settings - but without that flexibility getting in the way of less experienced authors
- It's designed to integrate - out of the box you can connect it to a range of organisational authentication systems. And it even has XAPI built in. So no need to use an LMS. Just serve the content up from Xerte and send tracking data to a Learning Record Store.
- Accessibility is designed in from the start. This is Xerte's real strong point - encouraging and enabling accessible content design.

## Areas for improvement

- Xerte has been in active development for over 15 years, and there's a lot that is left over from previous versions, such as Flash files and out of date copyright messages. Even more worrying is that the core elearning package design is not responsive. It doesn't work well on mobile devices. I'm surprised at that, given the target learner group - university students.
- The documentation is all over the place. There's a wiki, a readthedocs site, legacy documents in the main website and documents last updated in 2013 inside the installation package. Unfortunately, a Google search for Xerte documentation returns the out-of-date docs as the first link. And the documentation that does exist is difficult to use and not complete - especially that for administrators.
- The last release was in March 2023 (as of March 2024). Work is taking place inside Github, but it's not making its way out to users. It gives the impression that the software is no longer well supported, which I believe to be untrue.
- The marketing is confused. Is is called Xerte? Is it Xerte Online Toolkits? Is it XOT? Personally, I'd go with the simplest - "Xerte". The online toolkits moniker seems to be a leftover from previous incarnations.
- They are driven too much by users who want the ultimate in flexibility, without thinking about the impact this will have on the experience for learners. For example, the editing toolbar lets designers change fonts, font sizes and font colours. Now, you might think that's reasonable? But I've seen the mess this leaves for learners - with every page looking like a year 7 student's first play with Microsoft Word. Far better to **only** give access to a standard set of styles, that are controlled centrally.
- There doesn't seem to be an underlying business model, meaning that further development, documentation and support will always be reliant on volunteers or project-funding. It leaves me with a bit of a worry about the software's long term future (although given how long Xerte has been around perhaps I'm worrying unduly?)

## Summary

Xerte is extremely powerful and useful in the right contexts. It does take some work to set up - including some fairly technical stages. But once that's done, then it's relatively easy for content authors to pick up and produce quality materials.

If you are going to use Xerte, then, unless you're a developer, consider "paying" for it by volunteering with the documentation or the marketing. That's where you will probably have the most impact.

## Response from the product team

You'll find a helpful response to this review on the associated [LinkedIn post](https://www.linkedin.com/posts/markberthelemy_mark-berthelemy-learning-and-knowledge-activity-7178299698338770944-GLG1)

![Xerte screenshot](/post-images/2024/xerte-screenshot.png)

