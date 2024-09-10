---
title: 'Learning technology implementation planning &dash; 2'
author: Wyver Solutions Admin
excerpt: |
  This is the second in a short series of articles exploring my current state of thinking around implementing learning technology solutions.

  In the first post, I looked at the scoping &amp; kick-off stages - the essential foundations for a successful project.

  This time I'll focus on the "Project setup" stage.
layout: post
permalink: /2015/04/17/learning-technology-implementation-planning-2/
tags:
  - Project management

---
This is the second in a short series of articles exploring my current state of thinking around implementing learning technology solutions.

In the [first post][1], I looked at the scoping &amp; kick-off stages &#8211; the essential foundations for a successful project.

This time I'll focus on the &#8220;Project setup&#8221; stage. This is a piece of housekeeping that is often forgotten in the rush to get started building something. It includes:

  * Agreeing the quality standards
  * Setting up the project infrastructure infrastructure
  * Defining what will be done first

I'm using terms that come from <a href="http://guide.agilealliance.org/" target="_blank">Agile development</a> practices, but don&#8217;t let that put you off&#8230; Even if you&#8217;re using other project management methodologies these ideas should still be applicable.

# Agree definition of user story ready

Whether you&#8217;re defining **all** the software requirements up front, as per the typical &#8220;waterfall&#8221; project, or defining them as you go in an agile project, you will still need to document how what needs to be done.

These are your user stories.

Ideally they would contain an overview of what should be created from the user&#8217;s perspective, and then some detail which provides enough information to be able to do acceptance tests.

For example, the overview statement might be:

> As an administrator, I need to be able to allocate users into groups so that I can efficiently manage who is doing which course.

And the subsequent detail might then be:

> GIVEN that I am logged in as an administrator
>
> AND some users exist
>
> AND a group exists
>
> WHEN I add a user to a group
>
> THEN the group records the new user without errors

This (highly stylised) example is an illustration of the <a href="http://guide.agilealliance.org/guide/gwt.html" target="_blank">Given-When-Then</a> pattern, which is designed to help write requirements that can be easily tested against.

User stories like this often benefit from screen designs or mockups to help the developers.

The key thing at this point is to agree what quality will be expected for the user stories. What level of detail will be required?

# Agree definition of task done

In a similar way to defining how you know a user story is ready, you&#8217;ll need to agree how you know a task has been completed, the <a href="https://www.scrumalliance.org/community/articles/2008/september/what-is-definition-of-done-(dod)" target="_blank">definition of done</a>. It&#8217;s not just about saying something is finished, it&#8217;s about making a statement that the task has been finished to a certain standard.

The definition of done sets that quality standard and should be published and known by all team members.

# Agree definition of ready for release

Often this is called the <a href="http://www.codeproject.com/Articles/357697/Done-Done-Done-When-is-a-feature-really-done" target="_blank">definition of done done</a>. It means that all the functionality is in place, the user interface has been fully built, it&#8217;s been through [unit, integration, accessibility and systems testing][3], there are no blocking bugs, the documentation is complete etc.

Again, those quality standards should be published and accepted up front.

# Setup visual management board

OK, not everyone will use visual management boards to run their projects. In traditional environments, you&#8217;ll most likely still find the project managers use Gantt charting software like <a href="https://products.office.com/en-us/project/project-and-portfolio-management-software" target="_blank">MS Project</a> or <a href="http://projectwizards.net/en/products/merlin-project" target="_blank">Merlin</a>. These are incredibly powerful pieces of software, that do far more than just the basic visualisation of a project. They also help manage resourcing and budgets.

However, in a fast moving environment, you&#8217;ll often find that a visual approach to management works best:

>   * **Save time by simplifying the complex** &#8211; Visual management helps people understand complex information at a glance, like what work items should be prioritized and why.
>   * **Reduce waste by communicating effectively** &#8211; Take the guesswork out of teamwork by letting people see their work.
>   * **Overcome impediments** &#8211; See where work has slowed or stopped and take steps to fix it.
>   * **Collaborate and improve** &#8211; Visual management encourages collaboration among a team because everyone can see what everyone else is working on.
>
> <p style="text-align: right;">
>   <a href="http://leankit.com/project-management/visual-task-management/" target="_blank">LeanKit.com</a>
> </p>

The best example I've seen of visual management in practice is when the Swedish Police needed to completely rebuild their case management software. The book <a href="http://www.amazon.co.uk/Lean-Trenches-Managing-Large-Scale-Projects/dp/1934356859" target="_blank">Lean from the Trenches</a> is an easy, but challenging read as may totally change your perceptions on how projects should be run.

For a flavour, take a look at the author&#8217;s presentation to a developer&#8217;s conference a few years ago:



# Setup development environment

If you&#8217;re going to have multiple people creating code for your project, then you&#8217;ll need them to have the identical environments in which to do their developing. Otherwise you run the risk of the code working for one developer, but not for another.

<a href="http://docs.vagrantup.com/v2/why-vagrant/" target="_blank">Vagrant</a> is one of a number of tools that may help.

> Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize the productivity and flexibility of you and your team.

Of course, if you&#8217;re just configuring <a href="http://en.wikipedia.org/wiki/Software_as_a_service" target="_blank">SAAS</a> software then you don&#8217;t need to worry about this!

# Setup development servers

Apart from the small, low budget projects, it&#8217;s very rare that you&#8217;ll find a software implementation project that just puts the software on a live server and does all the development, configuration and testing on there.

Normally you would want to have three server environments at a minimum. These are in addition to the developers&#8217; local installations where they do the basic functional unit testing.

  1. **Development** &#8211; the place where all the code that the developers release is tested against the other parts of the system &#8211; particularly relevant if you are integrating with other applications
  2. **Staging** &#8211; a mirror of the production environment, where you place code just before it gets released to production, for final testing
  3. **Production** &#8211; where the real users are

# Agree code frameworks to be used

Again, if you&#8217;re not developing code, this may be irrelevant.

If you are, then it&#8217;s important to decide from the outset how you&#8217;re going to be building the project.Most languages have a range of frameworks which are designed to get you started quickly and avoid re-inventing the wheel. For example, if it&#8217;s a Javascript app, then will you be using <a href="https://www.meteor.com/" target="_blank">Meteor</a>, <a href="https://angularjs.org/" target="_blank">Angular</a> or <a href="https://facebook.github.io/react/" target="_blank">React</a> (or one of many others)?

Developers often have strong preferences, so it&#8217;s good to air these at the beginning&#8230;

# Agree software architecture

Even if you&#8217;re not developing code this is still important. In most implementations you&#8217;ll be wanting a number of software components to talk to each other. For example, you might have an HR system, a Learning Management System and a content repository.

Software architecture looks at:

  * Which system holds which data
  * How and when data will be transferred between systems
  * Where there may be gaps in functionality that need to be filled

It normally starts at a very high-level, focussing on the things that are going to be difficult or expensive to change later, and then moving into requirements analysis &#8211; the lower level of detail that developers and configurators will work with.

# Define user stories for the first iteration

Your developers and configurators will need something to do when the project starts, so this is the point at which you define those first tasks &#8211; following the quality standards you&#8217;ve already set out.

Each user story should have a rough size attached to it. I use the <a href="http://sanjaal.com/java/961/agile-development/why-is-fibonacci-series-numbers-used-in-agile-planning-and-estimations/" target="_blank">Fibonacci method for sizing</a>,  as it helps to show the relative sizes very easily. Anything that is an 8 or above should really then be broken down into smaller user stories, to make it more manageable. This is especially true if you&#8217;re working in 2 week sprints; aiming to complete a number of user stories within each sprint.

# Prioritise tasks for the first iteration

Prioritization is a bit of an art form. You&#8217;ll be guided by:

  1. What will show off new functionality most quickly
  2. Any dependencies on other pieces
  3. What you can fit within the iteration

The aim is to build something that works and is usable. It might not have all the bells and whistles, but it gives the customer enough to get going with.

Note that there are caveats to this &#8220;incremental development&#8221; approach. See: <a href="http://herdingcats.typepad.com/my_weblog/2014/07/the-myth-of-incremental-development.html" target="_blank">The myth of incremental development</a>

It might be that you can build something suitable in a 2 week sprint, or the first iteration may take 6 months. However, the shorter you can make the iterations the more easy it is to respond to changes in the the requirements.

 [1]: {{ site.url }}/2015/03/04/learning-technology-implementation-planning-1/ "Learning Technology Implementation Planning &dash; 1"
 [3]: {{ site.url }}/2013/08/10/managing-testing/ "Managing testing"
