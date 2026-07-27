---
title: 'Are your technology decisions creating debt?'
author: Mark Berthelemy
excerpt: I consider the long term impact of quick fixes
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2026/07/27/technical-debt
img: 2026/07/jakub-zerdzicki-dEwvH-LlpWc-unsplash.jpg
imgalt: 50 euro notes surrounded by items like a model house
imgcredit: Jakub Żerdzicki on Unsplash
imgurl: https://unsplash.com/fr/photos/quelques-cles-sont-assises-dans-un-support-dEwvH-LlpWc
tags:
  - Decision making
  - Technical debt
  - Assumptions
---
As I talk to senior leaders about technology decisions, one of the most common topics of conversation is the long term impact of "quick fixes".

You know the sorts of thing I mean:

- Using software that someone's purchased on their personal bank card, without going through any sort of due diligence
- Setting up a customer in a way that is different to the rest of your customers so you get a sale
- Using tools in non-standard ways to meet immediate needs
- Allowing your internal coder to build a custom application
- Bypassing the standard change process to "get it working"
- Having unofficial and undocumented processes
- Not upgrading the software because it's "too difficult"
- Using a spreadsheet to manage a process
- Using unlicensed or unsupported software

At some point in the future, all those workarounds will, inevitably, come back to bite you. They are like a debt. The longer you leave it the more it grows, and the more impact it will have when you decide to pay it off.

## The upgrade debt

Let's take upgrading software as an example.

You're a company with tight budgets, so you've picked up some open-source software to help run your business. There are many examples of great open-source software for all types of organisation - from full blown Enterprise Resource Planning, through Content Management, Customer Relationship, Project Management and Learning Management Systems.

You get someone to install it on a server, as that's a bit too technical for your team. The software runs well, and does just most of what you need. But you add a plugin or two to make it a better fit, and perhaps an integration with your finance system. The technician sets up a backup system so you feel happy you can always recover if there's a problem.

Over time, you receive notifications that there are upgrades available. But the software's still working well, and the technician costs money, so you put it on the back burner.

But then you hit a point where you have to do something. Perhaps you've bought a new finance system and the software doesn't work it, or your data protection officer identifies a high priority risk, or you hear about a significant vulnerability in the version you're using. Or maybe you actually get hacked...

There are all sorts of things that might prompt an urgent upgrade. But that's the point where the technical debt has to be paid off.

What could have been a simple process has now become a major project - often requiring changes to the underlying server software, managing multiple upgrade steps, and testing customisations at each stage. All this takes time during which the software  - and potentially your business - is out of action.

## Non-standard practices debt

The same is true of workarounds like non-standard ways of using software. For example, you might be using a content management system like [Jekyll](http://jekyllrb.com/) or [WordPress](https://wordpress.org/). These tools are highly flexible, but they're still designed to work best in certain ways.

So, if you decide to use "blog posts" as "pages", or a "data file" instead of a "collection", one day you'll have to deal with the consequences.

As you add content, you might start creating links to it - both internally and from external places like social media.

You might create processes and systems that are based on the content using these non-standard structures.

And the more time goes on, and you add more content, the more the technical debt accrues. It becomes ever more complex to pull yourself out of that debt. It won't be just a matter of reorganising things. You've also got to deal with broken links, with the pain of re-educating your users, and with your search engine rankings dropping overnight.

## Custom application debt

With anyone and everyone now able to create their own applications using AI, it's extremely tempting to build everything from scratch - bespoke, just for your organisation.

Yes, in the short term, you'll get the application you wanted. Maybe a system to help manage your clients and their projects, or a data dashboard, or a student tracking tool.

Don't get me wrong. In the right environment, and with the right humans in the loop, this can be a valid approach.

Without that environment and those people, all you're doing is creating a large debt to repay in the future. The software might work on the product owner's laptop, but does it work at scale? Does it meet accessibility and security standards? Does it talk nicely with your other systems? What happens when those systems change around it?

Just as with our other examples, you have the choice whether to deal with the debt incrementally, or in one go when you hit that point where something breaks.

## Conclusion

There are no right answers in any of these scenarios. We all make the best decisions we can given the information available at the time. What we can do, though, is be more aware of the consequences of those decisions - both for the short and the long term.


