---
title: 'What is single source publishing?'
author: Mark Berthelemy
excerpt: How to create content at scale
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/06/12/single-source-publishing
img: 2024/gears-1236578_1280.jpg
imgalt: Machine with cogs
imgcredit: MustangJoe on Pixabay
imgurl: https://pixabay.com/photos/gears-cogs-machine-machinery-1236578/
tags:
  - Solutions architecture
  - Content management
---
It was a workshop at the Open University that introduced me to the concept of Single Source Publishing ([Wikipedia: Single Source Publishing](https://en.wikipedia.org/wiki/Single-source_publishing)).

For years I'd been exploring the world of databases - where the data is kept separate from how it's presented. It means that you can take a set of data and deliver it in many different ways.

For example, data about planets in the solar system (my first database project whilst in teacher training - yes, that long ago!) could be used to create a list of planets by size, or a set of pages with details about each planet's moons. Many outputs from a single source.

So, when the OU team shared how they published content from a single XML ([W3Schools: What is XML?](https://www.w3schools.com/xml/xml_whatis.asp)) file it all made sense. Rather than a monolithic file, where the content and how it's presented are all stored in the same place, their process took two files, one with the data (XML) and one with the styling information (XSLT ([W3Schools: XSLT Introduction](https://www.w3schools.com/xml/xsl_intr.asp))) and merged them together to create the finished output.

You could easily change how the output looked by changing the XSLT file, without touching the data itself.

The problem was that the toolchain - the suite of software tools to make this work - were  technically challenging to use. You had to understand the links between the XSLT template and the XML data structures. Then you needed to type arcane terminal commands to do the conversion.

In some ways, that is still the case. You need a particular mindset to get to grips with single-source publishing. It's a way of thinking that separates the content and its structures from the way the content is presented.

## Separate content from presentation

Anyone that has created a website using HTML5 will know this. Whilst old-style webpages were awash with instructions about how to display particular elements, modern ones keep the data (HTML ([W3Schools: Introduction to HTML](https://www.w3schools.com/html/html_intro.asp))) in one file, and the presentation instructions (CSS ([W3Schools: Introduction to CSS](https://www.w3schools.com/css/css_intro.asp))) in another.

In this way, an element like `<h1>My heading</h1>` which gives the content of the main heading, can be adjusted by CSS so that the heading is, for example, a different colour: `h1 { color: red; }`

So, at its simplest, single-source publishing is about changing how content looks. But, of course, it can get way more complex than that...

A single-source publishing toolchain can not only change the way it looks, it can change the type of product.

## Multiple outputs from a single source

For example, taking our basic HTML file (or, more often, an XML or [Markdown](https://www.markdownguide.org/getting-started/) file - these are just different ways of "marking up" content to show how it is structured. XML is complicated. Markdown much less so)... Anyhow, the HTML file can be processed in one way to create a webpage, in another way to create a PDF file, and in another to create an ePub.

This is similar to how [Leanpub](https://leanpub.com/lfm/read#leanpub-auto-how-markdown-is-used-in-leanpub) lets authors write in Markdown, and then output their books as either PDF or ePub. 

Even more complicated, you can start to use the data to create different products for different audiences. For example, you might be creating a training product. Some parts of the content will go in the participants' guide, and all of the content will go in the trainers' guide. There is one central store containing the structured content, with two templates, one that displays all the content, and another that ignores anything that is marked up as for the trainer only.

## Reusing content chunks

And then there's one more layer of complexity... You could have some content that should be repeated across all your products. For example a copyright message, or some boilerplate text about your organisation. With single-source publishing you only create that once. It's stored centrally and you instruct the templates to pull it from the central store when it's needed.

This is a common way of working when writing code. Developers quote the acronym "DRY" (Don't Repeat Yourself"). Anything that can be reused in multiple places should only be written once.

That means that, if something needs to change, perhaps after a change in the organisation, or a legal requirement, you change it in one place, and then republish everything with the click of a button. Well, that's the theory!

## Where to get help

In training/learning circles, the experts at single-source publishing are [Xyleme](https://xyleme.com/). Over the  years, they've built a highly sophisticated suite of tools, that have gradually become easier to use. Now, from a single piece of structured content, you can create a trainer's guide, a participant handbook, a set of slides, an ePub book, and even interactive elearning content. 

Of course, the elearning content won't be as sophisticated as what you can produce with tools like Articulate Storyline, Evolve or Elucidat. But, if all you need is multi-media with assessment questions (as seen in the vast majority of elearning), then this will be enough.

However, Xyleme is enterprise software. It's expensive. It's designed for organisations creating large quantities of training and documentation, where efficiency in the production process is paramount.

Other process-driven content development toolchains created for elearning and documentation include [Dominknow](https://www.dominknow.com/), [eXactLS](https://www.exactls.com/), [Paligo](https://paligo.net/) and [Author-IT](https://www.author-it.com/).  

Single-source publishing is more commonly found in academic publishing, where there are highly sophisticated suites of software designing to ingest content from researchers and use that content to create citation databases, abstracts, journal articles, full journals, proceedings documents and even books. All with highly granular metadata to help enable cataloguing and "discovery" - the process by which other researchers find the content.

Specialist suppliers in this field include [67Bricks](https://www.67bricks.com/), [Coko Foundation](https://coko.foundation/) and [Atypon](https://www.atypon.com/), among many others.

## Getting started with single-source publishing

If you just want to get started, without the complexity of a complete, enterprise level system, there are five things you should begin to do:

1. Use styles consistently in your Word documents. (Other word processors are available. In fact styles in LibreOffice are way easier to use than in Word). Once you start using them, you'll wonder how anyone creates documents efficiently without them.
2. Explore how content development tools like Word and LibreOffice can turn your writing into different formats, like PDF and ePub. Look especially for how they automatically create bookmarks or chapters based on the styles you use.
3. Learn Markdown. It's supported by many tools including Google Docs, Obsidian, Github, Gitbook, and many other writing tools. You'll find yourself thinking much less about how your writing is presented and more about the writing itself.
4. Learn HTML5. HTML is a specific flavour of XML, and so gives a really nice introducion to structured content. Once you have your content in HTML you can then use other tools to pull it apart and re-present it.
5. Learn Jekyll (or pretty much any coding language, like Python). You'll quickly discover the importance of reusable chunks - often known as `includes`, `modules`, `functions` or `partials`. Remember this is about a mindset change. As soon as you start thinking like a programmer, you'll want to bring this into your content creation.

## Conclusion

If you are creating more than one-off documents, especially if those documents are going to multiple audiences, you need to start considering aspects of single-source publishing. You will save time and effort almost immediately.

## Disclaimer

I have worked for Xyleme in the past. Other than that, I have no commercial interest in any of the organisations represented in this article.