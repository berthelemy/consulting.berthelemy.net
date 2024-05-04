---
title: 'Review of CourseCRM : integrating Moodle and SugarCRM'
author: Wyver Solutions Admin
excerpt: 'Combining Moodle with a Customer Relationship Management system should solve many of the problems faced by Learning &amp; Development organisations. I look at how this might work, and how CourseCRM has approached the integration.'
layout: post
permalink: /2014/11/14/review-of-coursecrm-integrating-moodle-and-sugarcrm/
tags:
  - Moodle
thumb: /post-images/2014/11/cm_logo-thumb.png
banner: /post-images/2014/11/cm_logo-banner.png
alt: CourseCRM logo
img-credit: <a href="http://www.coursecrm.com/" target="_blank">CourseCRM</a>
---
Generally, I would advise not to use Moodle for either content management or student administration.

Leaving the content management piece aside for now (as I&#8217;m sure that will produce some howls of protest&#8230;), let&#8217;s consider what a typical training or learning &amp; development organisation needs to do.

<img class="aligncenter" src="/post-images/2014/11/building-blocks.png" alt="Building blocks of a typical L&amp;D organisation" />

#### Building blocks

##### Customer Relationship Management

Any organisation needs to know who their customers are and what they are buying or using. Clever analytics will help the organisation to match new &amp;existing customers to new &amp; existing products in order to grow further.

##### Student Administration

Administration is the process of ensuring the right people get the right information at the right time, with the minimal amount of wasted activity for all involved.

##### Learning Delivery

At the heart of any L&amp;Dorganisation is the &#8220;delivery&#8221; of learning, whether that&#8217;s events, materials or activities.

##### Support Tickets

People will often need support, especially when there are complex administration processes, assessments or technology involved. It&#8217;s important to ensure that those support requests are met efficiently and effectively, and then to learn from them to improve communication and processes in the future.

##### Reports

By pulling together data from across the different parts of the organisation it&#8217;s possible to provide up-to-date information to both the learner and the organisation&#8217;s teams &#8211; to help them make decisions and improvements.

#### Processes

When you look in more detail at how these building blocks work together, it shows some fairly complex process flows:

<img class="aligncenter" src="/post-images/2014/11/processes.png" alt="Typical L&amp;D processes" />

Moodle is great at the Learning Delivery part of the puzzle. But ask anyone who&#8217;s tried to use Moodle on its own to run an L&amp;Dorganisation and they&#8217;ll tell you horror stories of multiple spreadsheets, CSV files and complex mail merges.

In schools and colleges there are a few, high-powered Student Information Systems, like <a href="http://www.capita-fhe.co.uk/products/pages/unite_landing_page.aspx" target="_blank">Capita&#8217;s Unit-E</a>, and <a href="http://www.tribalgroup.com/technology/sitsvision/Pages/default.aspx" target="_blank">Tribal&#8217;s SITS</a>, but these will be overkill for many of the adult learning contexts where Moodle is found.

<a href="http://www.coursecrm.com/" target="_blank">CourseCRM</a> connects Moodle with its equivalent in the Customer Relationship Management world: <a href="http://www.sugarcrm.com/" target="_blank">SugarCRM</a> (you might want to use <a href="https://suitecrm.com/" target="_blank">SuiteCRM</a> instead &#8211; which is SugarCRM with a lot of additional functionality, especially around reporting, in a neat, easily upgradeable package).

<img class="aligncenter" src="/post-images/2014/11/moodleint.png" alt="Data flows" />

It pulls as much data as it can out of Moodle (using a clever web-service, with a built in queuing system &#8211; which is important to ensure no data is missed) and aggregates it into SugarCRM.

This allows the admin team to easily find out what is happening with their learners.

This data can then be used alongside SugarCRM&#8217;s ticketing and sales process systems in order to provide an all-round picture of your communications with your students.

<img class="aligncenter" width="100%" src="/post-images/2014/11/course-attendance-query.png" alt="Course attendance query" />

From within the CRM, an administrator could:

  * query, search or browse for specific learners
  * query, search or browse for learners who meet specific criteria
  * drill down into a course and view attendance summary data
  * drill down into an assessment activity and view performance summary data
  * Send an email to all students who meet a particular set of criteria

Using data available in the CRM, the administrator can now build reports, such as:

  * all learners who have never accessed a course
  * all learners who have not accessed a course within the past month
  * all learners who have scored below a particular grade on a specific assessment activity
  * all learners who have passed a course and who you could be marketing the next course to

The bit that&#8217;s missing, at the moment, is the administration piece, where you organise student into courses, manage joining instructions, sort out tutors etc, and then push all that data into Moodle. With small student numbers that&#8217;s not a problem. But once you start getting into complex scenarios or large student numbers, that can become quite a major headache.

In a recent project, where I had to organise dozens of students into groups within multiple courses, I ended up writing a Python script to merge the list of students with the list of groups to create a massive CSV file for importing into Moodle. This wasn&#8217;t ideal, especially as it needed to be done for every intake. And just moving a student from one group to another involved many operations &#8211; in multiple courses.

What CourseCRM does, it does extremely well. So, if you&#8217;re looking for a way to efficiently support and track students and their courses, then you should consider CourseCRM.

My hope is that they&#8217;ll extend the functionality so that SugarCRM can also be the place where the administration can happen.
