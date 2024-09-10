---
title: Open sourcing the Adapt elearning framework
author: Wyver Solutions Admin
excerpt: my friends at Kineo today hosted an industry workshop to look at their Adapt responsive elearning framework, and to discuss how it could be managed as an open-source project.
layout: post
permalink: /2013/07/02/adapt-elearning-framework/
tags:
  
  - Content management
  - Open source
  - Solution design
  - Standards
  
---
My friends at [Kineo][1] today hosted an industry workshop to look at their Adapt responsive elearning framework, and to discuss how it could be managed as an open-source project.

## Challenges and Opportunities

This is a new move for Kineo. They have always been strong proponents of the open-source philosophy; contributing to existing projects such as Moodle, and making full use of open-source software in their own service offerings. But *running* an open-source project is a very different matter. It brings with it issues around governance and control, around supporting the diverse needs of a development community, and around creating a viable and sustainable business model.

None of these are insurmountable. Open-source specialist organisations such as Mozilla, Apache, Moodle, Automattic (WordPress) and Drupal have shown the way with highly successful products. Companies like Google, Twitter, IBM and even Microsoft have all released open-source projects which have benefited greatly from the input of wider, active communities of developers.

## What is Adapt?

But let&#8217;s look at what Kineo are looking to release, and why it&#8217;s important to the online learning industry in particular, and perhaps the wider web-development industry in general.

The key is in the name: &#8220;Adapt responsive elearning framework&#8221;.

Many in the industry are currently creating elearning packages that are designed to work across a range of screen sizes and orientations &#8211; using a concept known as Responsive Web Design (see my [Introduction to Responsive Design][2]).

Many start with an existing framework, such as [Bootstrap][3] (from Twitter), which takes much of the pain out of creating these types of resource. They then build in the elearning-specific items like multiple-choice questions and other interactive elements, and also a SCORM (or now Tin Can / xAPI) tracking data interface.

What Kineo have done is build their own framework, from a number of clever technology building blocks ([Backbone.js][6], [Underscore.js][7], [Handlebars][8], [jQuery][9] and [Modernizr][10]), that is specifically designed to operate in the elearning context, and also designed to allow semi-technical people to populate it with content.

You can see it working in the video at the end of this post.

## How is Adapt different?

For us, the key differentiator between Adapt and any other HTML5 framework is the use of [JSON][11] files within the framework to automatically structure and present the content.

JSON is a way of storing structured data in a file, whilst maintaining any relationships between the data objects.

You could imagine it&#8217;s an extension of what&#8217;s possible with a CSV file.

With the Adapt framework, a semi-technical person would just need to create the JSON file, following a documented standard way of writing it, and collect together the media assets, and then you have a complete elearning package, with all the interactions etc.

## New possibilities

Having an open standard for exchanging design information for elearning, and a common framework for rendering that information, will open up a whole world of interesting possibilities.

With the content already indexed and in one place, you immediately are able to implement a search engine inside the content. Essential, but sadly lacking in most elearning content.

I could end up with many different authoring environments &#8211; some based on desktop tools like Word or OpenOffice, some built on [node.js][12] (like Google Docs &#8211; able to operate collaboratively online or independently offline), some built as plugins for LMS applications like [Moodle][13] or [eFront][13], or even pure desktop or tablet apps.

I can also imagine many different ways to deploy the content. Yes, you could just create a single SCORM package, as is done currently. But what about a WordPress theme pack which comes with the Adapt framework built in and a plugin to accept many Adapt JSON files with their associated media? You&#8217;d then be able to build up a properly managed suite of content resources, with cross resource search, workflow, tagging and social elements built in. Once Adapt is able to send Tin Can (xAPI) messages, then you&#8217;ve got the tracking sorted too.

Or even the Content Exchange from City &amp;Guilds&#8217; (Kineo&#8217;s parent company) could be designed to accept and render the JSON files natively, without the packages needing to be played in an iframe or popup window. ([Demo video of the Content Exchange][14])

## Next steps

There are lots of possibilities, but the key thing now is to sort out the [governance model][15] and then to get the framework in front of as many developers as possible, along with documentation on how it works and how to plugin additional functionality.

There was a large section of the audience today from the elearning instructional design community. They were asking for the priority to be an authoring front end. However, for an open-source project to work, it *must* have an active group of developers who are willing to commit their time and effort. In my view, this group should be the initial priority until funding becomes available for creating an authoring tool. Instructional designers can always call in a friendly developer to put their ideas into the Adapt framework, just as is done currently with the multitude of frameworks being created already.

The beauty of releasing Adapt as an open-source project will be that the number of developers on the project will increase rapidly. This will bring improvements in quality and features that could never be realised by many small development teams all working on their own separate framework projects.

I wish Kineo every success in this venture, and look forward to exploring the possibilities of Adapt.

If you want to know more about open source technologies in learning, please come along to the [Elearning Network&#8217;s open source workshop][16] on July 12th.

<div class="aligncenter" style="width: 80%; border: 1px solid #dddddd; padding 10px; text-align: center;">
  <p>
    The open source revolution: low cost, no cost &#8211; too good to be true?
  </p>

</div>

## Kineo&#8217;s Adapt Responsive Elearning Framework: video

 [1]: http://www.kineo.com/
 [2]: /cms/2013/02/18/introduction-to-responsive-design/
 [3]: http://twitter.github.com/bootstrap/
 [4]: http://www.learningconversations.co.uk/main/index.php/2012/03/27/is-scorm-a-barrier-to?blog=5
 [5]: http://www.learningconversations.co.uk
 [6]: http://backbonejs.org/
 [7]: http://documentcloud.github.io/underscore/
 [8]: http://handlebarsjs.com/
 [9]: http://jquery.com/
 [10]: http://modernizr.com/
 [11]: http://en.wikipedia.org/wiki/JSON "Wikipedia article on JSON"
 [12]: http://nodejs.org/
 [13]: efrontlearning.net
 [14]: http://vimeo.com/60079920
 [15]: http://www.oss-watch.ac.uk/resources/governanceModels
 [16]: http://www.elearningnetwork.org/events/open-source
