---
title: Does Tin Can mean the demise of SCORM?
author: Wyver Solutions Admin
excerpt: In this article, first published in Training Journal (September 2013), I discuss the capabilities and potential of the new Experience API, and whether it means that SCORM is no longer needed.
layout: post
permalink: /2013/09/06/does-tin-can-mean-the-demise-of-scorm/
tags:
  - Supplier selection
  - Advocacy
  - Standards
---
<div style="padding: 5px; border: 1px solid #5b5b5b; margin: 5px; text-align: center;">
  This article was first published in <a href="http://www.trainingjournal.com/magazine/" target="_blank">Training Journal</a> &#8211; September 2013
</div>

Thanks to <a href="http://uk.linkedin.com/in/markaberdour" target="_blank">Mark Aberdour</a> and <a href="http://www.linkedin.com/in/andywooler" target="_blank">Andy Wooler</a> for their input and technical review.

<div>
  <p>
    Over the last year or so, many people have written and spoken about the new Experience API (also known as Tin Can API).
  </p>
</div>

It’s creating quite a buzz in the learning and development community, with many seeing it as the death of SCORM, and as the means to really understand how my learners behave.

So much so, that the question: “Does it do Tin Can?” is starting to appear in general conversations about learning systems. This reminds me of when “Are you SCORM compliant?” started to become a standard requirement in the early 2000’s – regardless of whether SCORM was actually relevant, useful or necessary for a particular context.

In this article we are going to look at three key questions and examine whether the Experience API really is the answer to all my problems, or whether it might just bring different ones!

  1. What will the Experience API enable me to do?
  2. Does this mean the end of SCORM?
  3. What should I be thinking about?

I will not be dealing with the technicalities of how the API works, although you can find some useful references below.

# What will the Experience API enable me to do?

## Record learning activity

At its most basic, the Experience API allows one system to send a message (known as a statement) to another system about something a user has done.

The statement is usually of the form:

<div style="padding: 5px; border: 1px solid #5b5b5b; margin: 5px; text-align: center;">
  Actor -> Verb -> Object -> Context -> Score
</div>

For example:

<div style="padding: 5px; border: 1px solid #5b5b5b; margin: 5px; text-align: center;">
  Jenny -> achieved -> Level 1 -> in Office Simulation -> scoring: 10,500 points
</div>

The data sent can be much, much richer than just that simple statement. Within the API specification, there are fine-grained levels of detail available for each component of the statement.

At the receiving end for these statements is a system known as a Learning Record Store (LRS). There are currently a few standalone LRS applications, and also some of the LMS vendors are building LRS functionality into their systems.

Given the richness and quantity of the data that can be sent to the LRS, a lot of people are now thinking about how to use analytics techniques (similar to Google Analytics for websites) to pull meaning out of the data. This then involves high-powered statistics to ensure that the meaning that’s derived is valid and accurate.

## Record any activity

One of the really exciting things about the Experience API is that it isn’t just about learning. In fact, if it was just about learning then we’ve not really gained very much at all.

Imagine an IT support system that recorded:

  * Calls resolved
  * Feedback scores from callers
  * Who resolved the call

So I could then pass a statement to the LRS that said something like:

<div style="padding: 5px; border: 1px solid #5b5b5b; margin: 5px; text-align: center;">
  Joel -> resolved -> Password reset call -> in Support Application -> scoring: 5 stars
</div>

If you then combine that with a system that provides training or support for the help desk agents, which could send statements like:

<div style="padding: 5px; border: 1px solid #5b5b5b; margin: 5px; text-align: center;">
  Joel -> read -> How to do a password reset
</div>

You can then start to do some analysis to show whether people that are solving problems well are the same ones as those reading the support materials.

You could even do some cause and effect tests, seeing what the resolution scores are like, then releasing some support materials and watching how the scores change.

Of course, that’s a simple example. But I hope it illustrates what’s possible.

## Store data

As well as just sending messages to a Learning Record Store, it’s also possible, using the Experience API, for the LRS to act as a repository for any arbitrary data. This is just like the Kindle app on your phone, which can store information about bookmarks and annotations. When you then read via the Kindle app on your tablet device this data gets picked up and used.

For those who know SCORM this is similar to suspend data, but there is no size limit, and the data can be stored in a structured way, rather than one long string of characters.

# Does this mean the end of SCORM?

Before I answer that question, let’s have a quick reminder of what SCORM is, and what it is for.

The Shareable Content Object Reference Model (SCORM) is a collection of ideas that describes how to put &#8220;Content Objects&#8221; together in a way that they can be reused (Shared) across multiple, different systems.

These ideas cover:

<ol start="1">
  <li>
    How to describe such content with metadata
  </li>
  <li>
    How the content should be bundled together into a single package
  </li>
  <li>
    How the content should talk to the receiving system
  </li>
  <li>
    How the content should be sequenced to other pieces of content
  </li>
</ol>

In corporate learning, (1) and (4) are very rarely used &#8211; because they&#8217;re pretty complicated and very few Learning Management Systems know what to do with the data.

In theory, by using SCORM&#8230;

  1. Designers should be able to create materials independently of the host LMS&#8217;s in-built authoring tools
  2. Content is not locked into the host LMS. It can be ported to another LMS with no loss of functionality
  3. Learning materials can come from many suppliers and will just &#8220;work&#8221; in the host LMS
  4. Learners will be able to find materials from a catalogue that is populated by the metadata

In reality though…

  1. Different content suppliers, authoring tools and LMS&#8217;s have different interpretations of what SCORM means.
  2. SCORM-packaged learning content knows nothing about the functionality available in your LMS. So, if you&#8217;re using an LMS that has collaborative features like forums and wikis, or functions like polls, surveys and sophisticated assessments, all of that will have to be handled outside of the SCORMed content.
  3. SCORM is just about delivering content, tracking its use and providing an overall pass/fail score. It’s very limited in terms of what meangingful information can be extracted.
  4. Once content is locked into a SCORM package it’s unlikely it will ever be found by a learner, since search engines will not see it, and most LMS systems do not know what to do with the metadata contained in the package.

Outside of corporate learning very few people will have ever heard of SCORM. Yet many people will have used learning content delivery systems such as Youtube, Scribd, Slideshare and Flickr.

All of these take learning content in a particular packaged format and deliver it in the most efficient way possible to the end user.

But these platforms do so much more than I get from my corporate learning systems:

  * The content is embedded in the platform, not separate to it
  * Therefore the learner always has access to the platform&#8217;s functionality when they&#8217;re using the content.
  * Around the content, the platform wraps social elements such as comments, ratings, and social media links.
  * It also displays metrics such as aggregate ratings and viewing numbers.
  * The platform displays other, related content items, based on the metadata and the way other users have behaved.
  * The platforms allow users to engage with the content, again through comments, and through adding to personal &#8220;playlists&#8221; or &#8220;favourites&#8221;.
  * The platforms, in some cases, allow users to enhance the content, through the addition of layers containing links and explanatory text.
  * The platforms allow users to embed the content in their own websites &#8211; the ultimate in shareable content.
  * The platforms put &#8220;search&#8221; at the centre of their user-experience. By exposing as much content as possible to the search engines, they make the content more useful.

All these are for the benefit of the end-user. If they weren&#8217;t they wouldn&#8217;t get used, and no-one would publish content to them.

In contrast, how do I use SCORM packages?

  * I hide content from search engines, and only allow users to search by metadata (if there is any)
  * I treat the platform as secondary to the content, and ignore the user experience of getting to, from and between the content packages.
  * I treat learners as if they are in isolation from each other while they&#8217;re using the content, and forget the social elements of learning.
  * I take away anything that will help learners exercise choice (a key element in self-motivated learning), whether that&#8217;s cues to help them choose (eg. ratings and usage figures), or how they will use the content (eg. full screen, no ability to bookmark in their browser, and, often, no ability to cut and paste)

For most current corporate elearning, I could easily get by without using SCORM, if my systems allowed it. The ideal, of course, would be for my systems to be able to accept multiple content types (including SCORM) and display them all in a consistent user-centred way, like Slideshare, Youtube etc.

If you still want to track who has done what, that’s where the Experience API comes in.

You can take a content management system, like WordPress, and add Experience API capability using a plugin such as <a href="http://www.nextsoftwaresolutions.com/grassblade-xapi-companion/" target="_blank">GrassBlade</a>. Every time someone views a page, a statement is sent to your LRS with information about the user and what they did. Grassblade even allows you to embed content from compatible sources (like Articulate Storyline) with statements fed from the content via Grassblade to the LRS.

So, with the Experience API you get all the benefits of using a proper content management system (or whichever system you’d prefer your users to be in), along with the ability to track activities, with rich data, in an independent system.

# What should I be thinking about?

Each implementation of the Experience API will be different. Unlike SCORM, which is very Learning &amp;Development / Training focussed, and relatively simple to implement, the Experience API, used properly, can have organisation-wide implications, and will require quite detailed planning.

## Who owns this data? L&amp;D, Operations or the end user?

For the data to be useful to your organisation you need to really be pulling it in from operational systems as well as L&amp;D systems. How you divide up the responsibilities is up to you, but Operations should certainly be involved in the decision-making.

But also, you’ll need to consider the end-user’s perspective. Much of the data may be very personal to them. Should it be transportable to other systems when they move on?

## How do I connect my operational systems?

At the moment, the Experience API is almost exclusively being driven by the Learning Technology community. As Analytics capabilities develop, and as Operations start to see what might be possible, that will hopefully change.

In the meantime, you can use the API’s provided by your operational systems vendors to connect to your LRS, by translating data to Experience API statements. Reuben Tozman’s post on <a href="http://blog.edcetratraining.com/?p=269 " target="_blank">Rethinking Design with Tin Can</a> demonstrates the possibilities of connecting Salesforce to your LRS.[  
][1]

## How do I make sure the data is meaningful?

This is the biggest question of all. As I know with SCORM, it’s very easy to collect lots of data that actually means very little. The trick is to make the important measurable, rather than the measurable important.

Which brings me onto the verbs. These are the parts of the statement that will have the most impact on what information you’re able to gather.

The Experience API is completely open in that you can choose to use any verbs you like. However, your system vendors (particularly in the learning technology space) may well have preset verbs embedded in their systems or their content. You will need to assess whether these verbs work in your context.

If you are using the Experience API to build custom integrations with other systems, then you can choose your own verbs, and what conditions generate them. That will require careful designing so that you can extract meaningful information from the inevitable noise.

Anecdotal tales of early, large-scale adoptions of the Experience API speak about drowning in data, or systems that are unable to cope with the quantity of data being transferred. That doesn’t mean the API is at fault, but perhaps how it was being used might be.

## What about privacy?

This question seems to come up at most Experience API workshops. If you think of the Learning Record Store as a data warehouse that is storing information about what individuals have done, how they’ve performed, and the characteristics of that individual, then you might be right to be concerned.

This is the sort of thing that Enterprise systems like SAP and Oracle do, so I can’t see that it’s that big an issue. But you will need to make sure your data protection and information security policies and practices are up to scratch, and that you comply with whatever jurisdictions you’re working within.

# The future of the Experience API

Version 1.0 of the API was released in April 2013. So it’s still very early days. My hope is that we’ll see vendors that are not in the traditional learning technology market adopting the API. Once I get statements coming from CRM systems like Salesforce, social media tools like Yammer, and help desk systems like Zendesk then we’ll know it’s really making an impact on performance, not just learning.

# Useful references

## The Experience API official home and specification

Hosted by ADL, the people behind SCORM, and sponsors of the Experience API

<http://www.adlnet.gov/tla/experience-api>

## The Rustici Software Tin Can API site

Provided by the people tasked with producing and promoting the API

<http://tincanapi.com/overview/>

## Statements 101

How the Experience API messages are built up.

<http://tincanapi.com/statements-101>

## Tin Can API Blog – The open source landscape

A great list of open source tools, applications and documents that will help people to understand and use the Experience API

<http://tincanapi.com/2013/07/11/the-open-source-landscape/>

## Efront Learning (LMS provider) – Tin Can demystified

An opinion piece on the Experience API, but without the usual hyperbole

<http://blog.efrontlearning.net/2012/11/tincan-demystified.html>

## Guy Wallace (performance consultant) – Kicking the tin can

The Experience API from the point of view of improving performance, rather than just tracking activity

<http://eppic.biz/2012/09/10/kicking-the-tin-can/>

## Eric Fox – (behavioural scientist) – Initial thoughts on the Tin Can API, Big Data and Learning Analytics

A post that asks key questions about trust and what the data can and cannot show us. The comments, in particular, are very valuable.

<http://ericfox.com/tincan>

## Reuben Tozman – Rethinking design with Tin Can

Reuben looks at the exciting possibilities of connecting learning systems and operational systems (eg. Saleforce) with the Experience API

<http://blog.edcetratraining.com/?p=269>

## Koreen Olbrish (learning technology specialist) – Data is meaningless out of context

Koreen picks up from her conversation with Eric Fox and widens it out; asking questions on privacy and meaningful analytics, and getting great responses from the wider community.

<http://learningintandem.blogspot.co.uk/2013/02/data-is-meaningless-out-of-context.html>

## WaxLRS

One of the few available standalone Learning Record Stores, with analytics functions

<http://www.saltbox.com/wax-learning-record-store.html>

## Learning Locker

An LRS service, and also an open-source system to install on your own servers, which is designed to allow learners to take control of their data. It&#8217;s from <a href="http://www.ht2.co.uk/" target="_blank">HT2</a>, the same people that brought me Curatr.

<a href="http://www.learninglocker.net/" target="_blank">http://www.learninglocker.net/</a>

## 5.11   Grassblade

An Experience API plugin for WordPress

<http://www.nextsoftwaresolutions.com/grassblade-xapi-companion/>

## 5.12   Articulate Storyline

A content authoring tool which produces Experience API statements.

<http://www.articulate.com/products/storyline-overview.php>

&nbsp;

 [1]: #_ftn1 ""
