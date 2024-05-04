---
title: 'Mid-year reflections'
author: Mark Berthelemy
excerpt: |
  It’s always good to look back every now and again, to assess what’s been achieved and what could have been done differently. This is important for organisations as well as individuals.
layout: post
permalink: /2015/06/30/mid-year-reflections/
tags:
  - Standards
  - Open source
thumb: /assets/P1010067-reflection-thumb.jpg
banner: /assets/reflection-1000-cropped.png
alt: Church reflected in glass
img-credit: Mark Berthelemy
---

<p>It’s always good to look back every now and again, to assess what’s been achieved and what could have been done differently. This is important for organisations as well as individuals.</p>
<p>Six months ago, I was in the middle of managing a project to implement a <a href="https://moodle.org/" target="_blank">Moodle</a> and <a href="http://learninglocker.net/" target="_blank">Learning Locker</a> backend with a bespoke Javascript front end application - working with a global social media organisations.</p>
<p>Alongside that I was working with a global professional body to design the technology underpinning their Continuing Professional Development (CPD) programme.</p>
<h2>Experience API (aka Tin Can)</h2>
<p>Both of these projects had <a href="http://www.adlnet.gov/capabilities/tla/experience-api.html" target="_blank">xAPI</a> at their heart. With the social media organisation, as well as function-specific APIs to allow the front-end to communicate with Moodle, I also used xAPI as the main means to store the learner’s progress and activity.</p>
<p>With the CPD programme, Learning Locker became the primary database for all the user interactions with the system. This meant designing a bespoke implementation of xAPI with a set of function scenarios, each one requiring its own statement design.</p>
<p>Wherever possible, I have tried to make use of standard statement components (such as verbs, activity types and recipes) as described in the <a href="https://registry.tincanapi.com/" target="_blank">xAPI Registry</a>. I also have tried to avoid functions that are specific to a certain Learning Record Store (LRS), such as the <a href="http://docs.learninglocker.net/postman/" target="_blank">custom APIs provided by LearningLocker</a>.</p>
<p>Whilst custom APIs are often really useful ways to solve problems, as soon as you start to use them you are then tied to that particular application. To minimise issues later on if you need to migrate to another application, then you need to stick to the standards as much as possible.</p>
<p>It’s a similar case with the verbs and other statement components. It’s usually far better to use language that is commonly understood, rather than inventing your own language and structures. In my case that wasn’t always possible, but I did make sure that anything that I created specifically was fully documented in a structured specification document - written using git and Markdown.</p>
<h2>Git and Markdown</h2>
<p>It’s been a really interesting year, so far, exploring how the technologies used by developers can play a part in learning solution design.</p>
<p>Initially this was inspired by the the UK Government Digital Service’s thinking on how they use <a href="https://gdstechnology.blog.gov.uk/2014/01/27/how-we-use-github/" target="_blank">Github</a> (a distributed <a href="https://en.wikipedia.org/wiki/Revision_control" target="_blank">version control</a> system) to collaboratively create their <a href="https://gds.blog.gov.uk/2012/11/06/shipping-the-digital-strategy/" target="_blank">strategy documents</a> as well as their code.</p>
<h3><strong>Git</strong></h3>
<p>Git, at its simplest, is a way of keeping progressive backups (known as repositories) of text files, with the ability to roll-back to any previous version.</p>
<p>More than, this, it’s possible for other members of the team to have their own copies of the Git repository, make changes, and merge those changes into everyone’s versions. It’s quite magical seeing it in operation!</p>
<p>We’ve used Git for managing the version control on documents. It’s so much more robust than sending Word documents by email with version numbers in the file names…</p>
<h3><strong>Markdown</strong></h3>
<p>Git does work best on text files - which is where <a href="http://daringfireball.net/projects/markdown/" target="_blank">Markdown</a> comes in. It’s a <strong>very</strong> simple way of specifying formatting (such as headings, bullets and tables) within a plain text file.</p>
<p>Using Markdown allows you to focus on the content, rather than the design - which you can always tweak later.</p>
<p>The <a href="http://www.wyversolutions.co.uk/" target="_blank">Wyver Solutions website</a> is now built using Markdown. Following a major service failure at my hosting provider, I decided to take what was left of my website and migrate to a <a href="https://en.wikipedia.org/wiki/Static_web_page" target="_blank">static site</a>, which has no need for databases and should be far quicker to use than the old <a href="https://wordpress.org/" target="_blank">Wordpress</a> site.</p>
<p>We’ve built the site using <a href="http://jekyllrb.com/" target="_blank">Jekyll</a> and hosted it for free on <a href="https://help.github.com/articles/using-jekyll-with-pages/" target="_blank">Github</a>. The basic framework took a weekend to sort out, and now it’s just a matter of taking the old content from Wordpress and converting it to a set of Markdown files. This is made simpler using the <a href="https://wordpress.org/plugins/jekyll-exporter/" target="_blank">Wordpress -&gt; Jekyll exporter plugin</a>, but there’s still a bit of tweaking to do on each page, particularly around images.</p>
<a href="http://www.wyversolutions.co.uk/feed.xml" rel="nofollow" target="_blank" style="float:right; margin-left:20px;">![RSS icon](/assets/rss-35468_40.png)</a>
<p>In the process, unavoidably we’ve had to lose the links to the old pages, and we’ve now got a new <a href="http://www.wyversolutions.co.uk/feed.xml" target="_blank">RSS feed URL</a>. I hope this doesn’t cause too much confusion!</p>
<p>It’s been a good process to work through. There’s a lot you can do if you write with Markdown files. From a single, collaborative, version-controlled source you can create a responsive website, a PDF, HTML5 presentation slides or an ebook! We’re looking forward to exploring more…</p>
<h2>Lean Learning</h2>
<p>Back in February, along with <a href="https://www.linkedin.com/in/seanbuckland" target="_blank">Sean Buckland</a>, one of the UK’s leading experts on “<a href="http://www.lean.org/WhatsLean/" target="_blank">lean</a>” service delivery, I led a workshop on using lean ideas within the context of learning &amp; development.</p>
<p>As well as looking at generic lean principles - like <a href="http://www.dummies.com/how-to/content/how-to-write-a-problem-statement-for-six-sigma.html" target="_blank">defining the problem statement</a> (harder, and more important, than you think) and the <a href="http://www.institute.nhs.uk/quality_and_service_improvement_tools/quality_and_service_improvement_tools/plan_do_study_act.html" target="_blank">Plan, Do, Study, Act</a> cycle, I also looked at more specific learning-related ideas.</p>
<p>For example, did you know that Lean actually started out in Learning &amp; Development? It began as a programme in the me in the 1940s, called <a href="https://en.wikipedia.org/wiki/Training_Within_Industry" target="_blank">Training Within Industry</a>. Its methods enabled companies to get people productive within weeks rather than years.</p>
<p>TWI focussed on three core areas:</p>
<ul>
<li>Job Instruction - how to break down jobs into tightly defined steps which can be taught, observed and coached</li>
<li>Job Methods - how to evaluate your own job for efficiency, how to suggest improvements by eliminating, combining, rearranging, or simplifying, and then how to “sell” those ideas back into the organisation</li>
<li>Job Relations - how to deal with workers effectively and fairly</li>
</ul>
<p>In my consulting work recently I have included a focus on Job Methods and process mapping as well as just the technologies that can help to provide instruction and learning.</p>
<p>Lean is all about working “just in time” and “reducing waste” - ideas which many learning organisations could usefully employ.</p>
<h2>What’s next?</h2>
<p>We’re looking forward to digging further into xAPI. There are a lot of people now developing real case studies which illustrates its benefits.</p>
<p>We’ll also be exploring more single-source technologies for content development. There are already a handful of high-end applications which do this for commercial publishing organisations. We’d like to identify a toolkit that can be used by smaller organisations with just a small amount of technical knowledge.</p>
<p>And we’ll be picking up more on Lean ideas. Just adding technology to an already convoluted process will not solve all the problems. Improvements in both&nbsp;go hand-in-hand.</p>
<p><strong>If you would like to know more about what we’ve been doing and how I can help your organisation, please <a href="/contact.html">get in touch</a></strong></p>
