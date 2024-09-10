---
title: Joining up your systems
author: Wyver Solutions Admin
excerpt: "As your needs change, you'll need to bring in new software tools for specific functions. I discuss four ways in which you can present a unified system to your users: through identity and authentication management; through consistent design; through cross-application reporting; and through cross-application data use."
layout: post
permalink: /2013/06/03/joining-up-your-systems/
tags:
 - Supplier selection
 - Project management
 - Technology reviews

---
Finding the one application that will do everything is the &#8220;holy grail&#8221; of most learning technologists. That&#8217;s where companies like [SAP][1] and [Saba][2] position themselves &#8211; as a one-stop-shop to support all your formal and informal learning needs. These systems are very fully featured and configurable, so, as well as a large license cost, they also require a significant investment in implementation to make sure you&#8217;re getting full value from them.

Don&#8217;t get me wrong. There&#8217;s a place for these massive, multi-purpose, integrated application suites. Particularly in larger organisations, where processes and practices change relatively slowly, and software can have a lifespan of many years, if not decades.

But, often, you&#8217;ll be looking for best of breed applications, each supporting a specific purpose, such as video-sharing, social networking, shared documents, course booking, elearning delivery and content management.

The problem with this is that these applications don&#8217;t usually talk to each other out of the box, so there&#8217;s no data sharing, which means you miss getting the full benefit of the applications as a whole. Each one becomes its own silo of information.

There are four ways that you might want to consider joining these best of breed systems together. Each one can be considered separately, but, implemented together, would help you to build a powerful integrated system. Obviously the more complex your application landscape, the more complex (and expensive) this integration process can become &#8211; which may then tend you towards looking at one of the all-in-one systems, with best of breed tacked on where necessary.

  1. Identity and authentication management
  2. Consistent design
  3. Cross-application reporting
  4. Cross-application data use

## Identity and authentication management

In the outside world, many applications are using Twitter, LinkedIn, Google and Facebook for authentication. This makes it easier for end-users, who don&#8217;t have to worry about creating yet another username and password. It also allows those applications to have a shared set of user identities from which they can start sharing data.

The same is true for for organisations running multiple applications. By putting in place an identity management system (like [LDAP][3]) alongside a standardised authentication mechanism (such as [SAML][4] or [Shibboleth][5]), you immediately make those systems more usable, and therefore more likely to be used. It will mean that personal details only have to be entered once, and then can be used across all the software tied in to the ID management system.

ID management can get pretty complex, so, in many cases it&#8217;s better to work with an expert in the field when you&#8217;re setting out, or when you&#8217;re adding in new applications. This is particularly the case when working in a mixed economy of Microsoft and other platforms&#8230;

## Consistent design

There are two reasons why it&#8217;s important to have consistent design across all your applications:

  * <span style="line-height: 13px;">It helps to build a common identity (or brand) for the services you&#8217;re offering &#8211; which then helps to transfer trust when you introduce new services</span>
  * It helps users of your services to know where they are, and how to get from one service to another.

Visual design is important to achieve this consistency, but so also is a common navigation structure. A great example of this is the BBC website, where the common top menu is always present, with just its colour changing to reflect the service below.

## Cross-application reporting

Reports that contain useful and accurate information are vital tools for any manager. Most applications will provide reporting capabilities for their specific functional area. But sometimes you&#8217;ll want to try to correlate data from across multiple applications &#8211; for example, to see if the people accessing a particular page in your content management system are the people who go on to enrol on a course in your learning management system.

You could use tools like Google Analytics, which track page views and provide sophisticated reports on user behaviour. Or, for more complex reporting, you&#8217;ll need to implement some sort of analytics tool that will take the data from the disparate systems, join them together and produce the reports. Something like [Activ8][6], [Cognos][7], or [Microsoft Reporting Services][8] would all be good places to start.

## Cross-application data use

Using data from one application inside another is often the best compromise between multiple, separate applications and one, monolithic application.

This *can* be achieved by building custom integrations between the software. But this is usually bespoke and therefore not easily replicable. It&#8217;s also difficult if the software is operating on different foundations, eg. PHP or .NET

A better approach is for the software providers to build a route into their systems that can be used by other applications. These routes are known as [Application Programming Interfaces][9] (APIs).

An API provides a standard way for other applications to read data from, and write data to a third-party application. Usually they work as [web service][10], which means that the underlying platform is irrelevant, as long as the service has a web address.

I'll look at APIs in more detail later this month, when I'll examine:

  * <span style="line-height: 13px;">How APIs actually work (in as non-technical language as possible!)</span>
  * Some examples of APIs in Learning &amp;Development applications
  * How APIs can be used to build a content-focussed intranet portal that&#8217;s integrated with your learning management system

&nbsp;

 [1]: http://www54.sap.com/training-education/learning-software-svc/learn/solutions/enterprise/index.html
 [2]: http://www.saba.com/
 [3]: http://en.wikipedia.org/wiki/Lightweight_Directory_Access_Protocol
 [4]: http://en.wikipedia.org/wiki/Security_Assertion_Markup_Language
 [5]: http://shibboleth.net/
 [6]: http://www.a8i.co.uk/
 [7]: http://www-01.ibm.com/software/analytics/cognos/
 [8]: http://msdn.microsoft.com/en-us/library/ms159106.aspx
 [9]: https://en.wikipedia.org/wiki/Application_programming_interface
 [10]: https://en.wikipedia.org/wiki/Web_service
