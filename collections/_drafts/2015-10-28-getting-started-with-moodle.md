---
title: 'Getting started with Moodle'
author: Mark Berthelemy
excerpt:
 Where to get help for those looking to setup their own Moodle site.
layout: post
permalink: /2015/10/28-getting-started-with-moodle
tags:
 - Moodle
thumb: /post-images/2015/10/moodle-logo-thumb.png
banner: /post-images/2015/10/moodle-logo-banner.png
alt: Moodle logo
img-credit: Moodle.org
---
[This post is a copy of a response made to a query on the <a href="http://learningandskillsgroup.ning.com/forum/topics/moodle-advice" target="_blank">Learning &amp; Skills group forum</a>]

If you&rsquo;re looking for help on setting up a Moodle site, you&rsquo;re going to be spoilt for choice...

Much depends on the level of ownership you&rsquo;re going to take for the site. At each level you will have the option of outsourcing it if you need to:

- Level 1: Infrastructure
- Level 2: Installation
- Level 3: Configuration
- Level 4: Administration
- Level 5: Course design

So, here are few resources that may help guide you at each level.

#### Level 1: Infrastructure

We&rsquo;ve split this into small and large setups.

##### Small setup

(Low user numbers, low bandwidth requirements)

This will work on a single server, running a Linux, Apache, MySQL and PHP software stack. These will need to be configured appropriately for security and performance.

There are guidelines on Moodle docs:

<a href="https://docs.moodle.org/29/en/Installing_Moodle#Requirements" target="_blank">https://docs.moodle.org/29/en/Installing_Moodle#Requirements</a>

<a href="https://docs.moodle.org/29/en/Installing_AMP" target="_blank">https://docs.moodle.org/29/en/Installing_AMP</a>

A lot has also been written about optimizing Moodle servers:

<a href="http://www.iteachwithmoodle.com/2014/01/20/optimizing-a-moodle-server-step-1-fine-tune-apache/" target="_blank">http://www.iteachwithmoodle.com/2014/01/20/optimizing-a-moodle-serv...</a>

<a href="http://www.iteachwithmoodle.com/2014/01/21/how-to-optimize-a-moodle-server-part-2-mysql/" target="_blank">http://www.iteachwithmoodle.com/2014/01/21/how-to-optimize-a-moodle...</a>

<a href="http://www.iteachwithmoodle.com/2014/01/22/how-to-optimize-a-moodle-server-part-3-apache-on-a-diet/" target="_blank">http://www.iteachwithmoodle.com/2014/01/22/how-to-optimize-a-moodle...</a>

<a href="http://www.iteachwithmoodle.com/2014/01/23/how-to-optimize-a-moodle-server-part-4-apc/" target="_blank">http://www.iteachwithmoodle.com/2014/01/23/how-to-optimize-a-moodle...</a>

##### Large setup

(High user numbers accessing a lot of resources and activities)

This can get very complicated very quickly, as you&rsquo;ll need multiple servers, network infrastructure, and security systems.

At this point, you will need to bring in professional system architects... Some will recommend Linux as the base operating system, others Windows. Either will work, but don&rsquo;t try to mix and match software (ie. with Windows use IIS as the web server software, and with Linux use Apache or nginx.

You will find this document useful at this stage:

<a href="https://docs.moodle.org/29/en/Performance_recommendations" target="_blank">https://docs.moodle.org/29/en/Performance_recommendations</a>

#### Level 2: Installation

Moodle is actually very simple to install, once you have the server hardware and software setup correctly.

Follow the instructions at: <a href="https://docs.moodle.org/29/en/Installing_Moodle" target="_blank">https://docs.moodle.org/29/en/Installing_Moodle</a>

You will usually find help in the <a href="https://moodle.org/mod/forum/view.php?id=28" target="_blank">Moodle Installation forum</a>

Some hosting providers offer an automated Moodle installation service, but be aware that many shared hosting setups will not cope with anything more than a very small number of users.

Don&rsquo;t forget that you will need to perform regular maintenance upgrades on your Moodle site in order to remain secure.

#### Level 3: Configuration

This is where it starts to get complicated, as Moodle can be configured to operate in so many different ways.

The best source of advice on this is Alex Buchner&rsquo;s book: Moodle 2 Administration (<a href="http://www.amazon.co.uk/Moodle-2-Administration-Alex-B%C3%BCchner/dp/1849516049" target="_blank">Amazon</a>). The book is probably a little out-of-date, and will need to be supplemented by frequent visits to <a href="https://docs.moodle.org/" target="_blank">https://docs.moodle.org/</a>

The main things to consider are:

<ul>
<li>How will I get users into the system?</li>
<li>How will I organise the courses?</li>
<li>What functions do I need to make available to course designers?</li>
<li>How will users navigate into and within the courses?</li>
<li>How do you wish your Moodle site to look?</li>
<li>What data do I need to collect about the learning activity that has taken place?</li>
<li>What roles will people have within Moodle, and what does each role need to be able to do?</li>
</ul>

#### Level 4: Administration

Actually, once a Moodle site is setup, there&rsquo;s little ongoing administration to do, apart from adding new users and assigning the right users to the right courses and groups, with the right permissions. It is possible to automate much of that, which will be considered during Configuration.

Again, Moodle docs is a good source of info: <a href="https://docs.moodle.org/29/en/Guide_for_new_administrators" target="_blank">https://docs.moodle.org/29/en/Guide_for_new_administrators</a>

#### Level 5: Course design

At this point, there is a huge amount of guidance and support <a href="https://www.google.co.uk/webhp?sourceid=chrome-instant&amp;ion=1&amp;espv=2&amp;ie=UTF-8#q=moodle%20course%20design" target="_blank">dotted around the web</a>. The <a href="https://moodle.org/mod/forum/view.php?id=41" target="_blank">Teaching with Moodle forum</a> is a particularly good source of help.

It is worth reading Moodle&rsquo;s paper on pedagogy: <a href="https://docs.moodle.org/29/en/Pedagogy" target="_blank">https://docs.moodle.org/29/en/Pedagogy</a> as it will give a very good idea of why Moodle works the way it does.

Other useful resources:

<a href="https://docs.moodle.org/29/en/Moodle_key_terms" target="_blank">https://docs.moodle.org/29/en/Moodle_key_terms</a>

<a href="https://docs.moodle.org/29/en/Managing_a_Moodle_course" target="_blank">https://docs.moodle.org/29/en/Managing_a_Moodle_course</a>

If you need independent support or advice to get you up and running with Moodle, please <a href="/contact.html">get in touch</a>.
