---
title: Moodle and eFront side-by-side
published: false
author: Wyver Solutions Admin
excerpt: "With eFront's recent string of awards, I thought it was about time I took a look at this relative newcomer to the open source Learning Management System market."
layout: post
permalink: /2012/10/02/moodle-and-efront-side-by-side/
tags: Technology Moodle

thumb: /post-images/2012/10/moodle_efront_logos-thumb.png
banner: /post-images/2012/10/moodle_efront_logos.png
img-credit: <a href="http://moodle.org" target="_blank">Moodle</a> and <a href="http://www.efrontlearning.net/" target="_blank">eFront</a>
---
With eFront&#8217;s recent [string of awards][1], I thought it was about time I took a look at this relative newcomer to the open source Learning Management System market.

For many years, [Moodle][2] has been most people&#8217;s port of call when looking for an open source LMS (or Virtual Learning Environment in the education sector). Yes, there are many others, such as [Atutor][3], [Dokeos][4] and [Sakai][5], but they just haven&#8217;t had the same impact as Moodle.

Personally, I&#8217;ve developed a love-hate relationship with Moodle. I&#8217;ve used it for many projects, from an elearning delivery platform for a local authority, through to a combined elearning and assessment platform used by nearly 45,000 people over the space of 6 months. It is tremendously capable, extremely robust (mostly!), and has been well tested by millions of users worldwide.

On the downside, though, it has grown to become a little bit of a monster. Each iteration has added further complexity, to meet the needs of different groups, yet without the polish on the user interface that would help to hide that complexity from people that don&#8217;t need it.

By comparison, eFront&#8217;s user interface is a delight. It uses a clear, icon driven design, which, somehow doesn&#8217;t fall into the trap of many such designs where the icons need interpretation. A lot of thought seems to have gone into keeping the interface consistent across the application.

#### Don&#8217;t make me think

That doesn&#8217;t mean it&#8217;s all good. I like to see how far I can get with an application before having to resort to the manual &#8211; to see whether it follows the &#8220;[Don&#8217;t make me think][6]&#8221; principle. This means that the application designers have to second guess what users are going to want to do next, and provide a route to that place. One of my first actions, after logging in as an administrator, was to try to build a lesson &#8211; which, eventually, I discovered, is only possible once you&#8217;ve switched roles to &#8220;professor&#8221;. But, once I got there, the process of designing a lesson was very straightforward, and the division began to make sense.

Here, though, is one significant difference between Moodle and eFront.

Moodle&#8217;s courses are built from a series of &#8220;activities&#8221; (ie. where the student leaves a record of doing something &#8211; usually through some sort of contribution) interspersed with &#8220;resources&#8221; (items that the student uses to complete the activities).

eFront&#8217;s lessons, however, are built along more traditional lines (cf. Blackboard), whereby a the lesson is built from content-based units, perhaps interspersed with tests. Any other tools, like projects (cd. Moodle assignments) or forums sit outside of the lesson structure. I know this would work for many usage scenarios, but I do prefer Moodle&#8217;s flexibility in how to structure the learning experience.

#### Flexibility vs Complexity

In fact, that&#8217;s the key area where Moodle wins out &#8211; its flexibility. But this comes with maturity, and also with a price &#8211; complexity. For example, the roles and permissions structures within Moodle are perhaps the most complete of any application I know. With them you can allow a user to do something in one context, but not in another. But this richness also means that it can become a nightmare trying to work out what has caused a particular behaviour for a particular user. It&#8217;s a little like having an overcomplicated set of Cascading Style Sheets (CSS), when building a website.

By comparison, eFront has a simple set of permissions, which are based on the three apparently unchangeable base user types of administrator, professor and student. I can see that working for most situations &#8211; but would get very limiting in others.

It seems that the eFront designers have taken the [80:20 rule][7] to heart. By focussing on the small amount of functionality that the majority of people will use, they&#8217;ve built an application that is suitable for most situations, without the massive effort required to make it fit the other 20%. eFront&#8217;s focus is on formal, content-centric teacher-directed learning experiences &#8211; and it&#8217;s very good at it.

The provided developer documentation shows that a lot of thought has gone into the architecture and security. (Although it&#8217;s always worth considering whether an independent security assessment should be performed if you&#8217;re going to be storing personal data on any system). The company behind eFront has a clear business model, which is always a plus as it helps to ensure sustainability of the product. And, alongside this, there also appears to be an active user and developer community &#8211; not as large as Moodle&#8217;s yet though!

I&#8217;ve been looking at the open source edition of eFront only, which does not have all the functionality of the commercial editions, and I&#8217;ve also not used eFront yet in a real live situation &#8211; which is where you really start to notice any limitations. But what I&#8217;ve seen so far looks extremely impressive.

There will still be situations where Moodle is the best tool for the job, but I do expect to be seeing a lot more eFront implementations in the near future.

 [1]: http://blog.efrontlearning.net/tag/best-of-elearning-awards
 [2]: http://moodle.org/
 [3]: http://atutor.ca/
 [4]: http://www.dokeos.com/
 [5]: http://www.sakaiproject.org/
 [6]: http://www.sensible.com/dmmt.html
 [7]: http://en.wikipedia.org/wiki/Pareto_principle
