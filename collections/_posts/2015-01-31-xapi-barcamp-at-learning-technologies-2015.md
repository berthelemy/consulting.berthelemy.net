---
title: '#xAPI barcamp at Learning Technologies 2015'
author: Wyver Solutions Admin
excerpt: 'In this short write-up of the xAPI barcamp, run by @learnpatch, I discuss some key ideas around implementing xAPI - particularly in the areas of designing and specifying the content of the xAPI statements'
layout: post
permalink: /2015/01/31/xapi-barcamp-at-learning-technologies-2015/
tags:
  - Standards
  - Advocacy
---
This week I had the privilege to work alongside <a href="https://twitter.com/bbetts" target="_blank">Ben Betts</a>, <a href="https://twitter.com/jonarchibald" target="_blank">Jonathan Archibald</a>, <a href="https://twitter.com/mrdownes" target="_blank">Andrew Downes</a>, and <a href="https://twitter.com/maberdour" target="_blank">Mark Aberdour</a> at the <a href="http://www.adlnet.gov/tla/experience-api/" target="_blank">xAPI</a> barcamp run by <a href="http://learnpatch.com/" target="_blank">LearnPatch</a>. Over 40 of me gathered at the <a href="http://www.thecumberlandarmspub.co.uk/" target="_blank">Cumberland Arms</a> to spend an hour or so in conversation about xAPI (aka Tin Can API).

Each of the team spent 15 minutes chatting about my own take on xAPI at each table. Then I moved on. It was like consultant speed dating!

There was a great buzz in the place, with some of the great minds in learning and development grappling with the difficult questions around xAPI:

  * If I can now collect data about everything that a person is doing, what about privacy?
  * Who owns this data?
  * If many implementation of xAPWe are going to be bespoke and unique where does that place it as a &#8220;standard&#8221;?
  * How do you know what data to collect?
  * Is xAPI ever going to break out of the L&amp;Dbubble and start to be used by operational systems?

All of these questions deserved digging into in far more depth than was possible, given the available time.

During all my conversations with people, I was asked about the xAPI implementations Wyver Solutions is involved in. Some key points came out, which I thought I&#8217;d share here.

## Bespoke &amp; unique

At the moment, many implementations of xAPI will be bespoke and unique, with their own vocabulary. Eventually, different communities/industries will start to develop their own particular flavours, which allow data to be moved between systems with relative ease.

For now, each time we implement xAPI in an organisation I have to work through the following thought process&#8230;

## Why are you collecting data?

Most of the time, I don&#8217;t just want to collect data for the sake of collecting it. I'll want to use it to help me make decisions. Usually these will be focussed on the core &#8220;business objectives&#8221; for my particular organisation. For example, in a sales-based organisation, I'd want to know what learning activities make a difference to the sales figures, so that I can decide which activities to invest in.

## What information do you need to make decisions?

Here I think about the reports that might be used to help me decide. In my example sales organisation, I would want charts that show sales figures correlated with when different types of learning activities were undertaken.

## What data is required to produce that information?

This is when I start getting into the detail. In my example organisation, I'd want to be capturing data when an individual does a particular type of learning activity, and also capturing when they sold something, and how much for.

## What bespoke vocabulary do I need?

The <a href="https://registry.tincanapi.com/" target="_blank">Tin Can API registry</a> contains a community generated set of vocabulary (verbs, activity types, extensions etc) that have recognised, generic definitions. Ideally I would limit my own vocabulary to this lists.

However, in many contexts, I need to create additional vocabulary so I can model the organisation more accurately.

For example, in a professional development organisation, which has annual CPD returns, I might want to create the following statement:

<p style="text-align: center;">
  Joe Bloggs <strong>audited</strong> [another statement]
</p>

<p style="text-align: left;">
  Audited doesn&#8217;t exist in the registry, so will need to be defined and possibly submitted to the registry. However, &#8220;audited&#8221; in this context means something very different to &#8220;audited&#8221; in an accountancy context. So it is likely to remain as a domain-specific definition.
</p>
