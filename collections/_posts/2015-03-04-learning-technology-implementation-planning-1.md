---
title: 'Learning Technology Implementation Planning &dash; 1'
author: Wyver Solutions Admin
excerpt: The beginning of a short series of articles exploring what I have learnt about implementing learning technology solutions. In this article I look at how to get things started.
layout: post
permalink: /2015/03/04/learning-technology-implementation-planning-1/
tags:
  - Project management

---
I'm often asked to support organisations who are implementing new learning technology solutions. my approach to this is constantly being refined, based on lessons learned from previous projects.

This article is the beginning of a short series which describes the current state of my thinking. But readers should be aware that this is not a template to be followed religiously. It will need to be contextualised and adapted depending on what you&#8217;re implementing and where.

# Scoping and kick-off

If you get this stage right &#8211; and spend a good amount of time and effort on it &#8211; then your implementation project is far more likely to be a success. Ideally, much of the scoping element will be done before any contracts have been signed for particular technologies. The best technology companies will offer this as a paid-for consultancy service. But remember that it&#8217;s difficult to be truly objective when you&#8217;re trying to sell a particular solution!

It&#8217;s important to do this stage face-to-face. Consider that a lesson learned from too many occasions when I've tried to shortcut the process with virtual meetings, and then stuttered to a halt during delivery when I realised that there was no real, shared vision for the project.

As you&#8217;ll see, there&#8217;s a lot to cover &#8211; but not everything will need to include everyone.

I&#8217;ve described each of the elements below. They don&#8217;t have to be done in a fixed order, apart from defining the problem statements &#8211; which really needs to be the first thing you work on.

## Define the problem(s) to be solved

My work on Lean Learning has highlighted the importance of clearly defining the problem(s) that you need to solve.

> The problem statement is a clear and concise statement that describes the symptoms of the problem to be addressed. Defining the problem statement provides three benefits for the team:
>
>   1. **creates** a sense of ownership for the team
>   2. **focuses** the team on an accepted problem
>   3. **describes** the symptoms in measurable terms
>
> <p style="text-align: right;">
>   from: <a href="http://www.aleanjourney.com/2009/11/defining-problem-statement.html" target="_blank">Defining the problem statement &#8211; Tim McMahon</a>
> </p>

<p style="text-align: left;">
  With a clear set of problems to solve, you then have something against which you can measure the success of the technology implementation, and also have a way of defining your technology requirements in a way that is much more useful than a simple list of functional requirements.
</p>

## Create a shared vision

Companies that are creating products and services often use the creation of an <a href="http://www.elevatorpitchessentials.com/essays/CrossingTheChasmElevatorPitchTemplate.html" target="_blank">Elevator Pitch</a> as a means of clearing up confusion within the team about what the product is, who it is for, and why it should exist.

If you&#8217;re just looking for a solution to your own problems, then you can use the same process to bring together a shared understanding of what you&#8217;re aiming for.

The aim of the exercise is to come up with a final statement of the form:

  * For: [who is the primary beneficiary of the solution]
  * Who: [what do the primary beneficiaries want to get out of the solution]
  * The: [name of the product or service]
  * Is an: [what is this product or service]
  * That: [what does the product or service do]
  * Unlike: [competitor products or services]
  * my product: [the unique selling point of the product or service]

For example &#8211; **For** new starters **who** want to get up and running quickly, **the** KnowledgeBase **is a **source of information about their jobs **that** is able to provide support at the point of need. U**nlike** the current intranet, **our product **will be integrated tightly with the operational management system.

## Explore stakeholder expectations

To be able to dig into the stakeholder expectations, you first need to know your stakeholders. These are the &#8220;people, groups or organisations that have an interest in or might be affected by the outcome of a project.&#8221; (<a href="https://www.prince2.com/blog/how-identify-stakeholders" target="_blank">Prince2.com</a>)

Each of these people or groups will have expectations about what your new technology will offer. It&#8217;s important to explore these expectations explicitly and up front. You may find it useful to get the group to prioritise them in the light of the problem statement(s) written earlier. If there are conflicts, it gives a good opportunity to look at what is going to provide most value to most people.

Consider:

  * Who are the people who will be impacted by the solution?
  * What do they need?
  * What quality do they expect?
  * Branding
  * Browser and device compatibility
  * Speed
  * Usability
  * Accessibility

## Explore high-level user journeys

A user journey can be used as the first stage in understanding how the solution needs to work. At this point, unless you&#8217;re developing something from scratch, it&#8217;s probably better to have the solution providers in the room &#8211; having already introduced them to the problem statements. As you talk through your ideals, they will be able to consider different approaches that would work with their particular technologies.

Start as early in the process as you can &#8211; from the very first point at which your users will come across your solution, and think through their whole journey through the system. Particularly identify key points where they will need to carry out an action or use data. This will start to produce a list of things that you will need to configure or develop.

## Define the testing approach

In many situations, particularly when you&#8217;re aiming for an agile project management methodology you might want to adopt a <a href="http://en.wikipedia.org/wiki/Behavior-driven_development" target="_blank">Behaviour-Driven Development</a> approach.

It builds on the problem statements and on the stakeholder expectations, which can be used to test the whole solution, by defining acceptance criteria for each small piece of the solution (particularly those pieces where you&#8217;ve had to configure or develop something). It might seem like a lot of work to do up-front (it is!) but working in this way means that you&#8217;re less likely to have defects that only get picked up at the last minute, and make it a lot simpler to develop or build the solution.

Such criteria can include:

  * unit tests (on each piece in isolation)
  * integration tests (where there are integration points between systems)
  * system tests (on the system as a whole)
  * performance and load tests
  * security tests
  * accessibility tests

## Define the reporting requirements

When you know what data needs to come out of the system, then you will have a specification for what data needs to be stored in the system. This is true of any IT solution, but especially so for xAPI implementations, where you can define, in a very flexible way, what data you want to store and how.

When collecting the reporting requirements consider:

  1. Who needs to see the report
  2. What will they use the report for
  3. What information should be presented in the report (eg. averages, graphs, aggregates)
  4. What data is required to produce that information
  5. Where that data will be supplied from

## Identify software platforms to be used

By this time, you will have a good idea of what you&#8217;re trying to achieve. You could use all the information above to pull together an <a href="http://en.wikipedia.org/wiki/Request_for_proposal" target="_blank">RFP</a> for a software vendor, or, if you&#8217;re already past that stage, you should be working with your supplier to identify how what they are supplying is going to meet your particular needs.

Often, you will be working with multiple applications and databases, such as <a href="http://en.wikipedia.org/wiki/Customer_relationship_management" target="_blank">CRM</a> systems, content management systems, learning management systems, <a href="http://en.wikipedia.org/wiki/Learning_Record_Store" target="_blank">learning record stores</a>, and <a href="http://whatis.techtarget.com/definition/front-end" target="_blank">front-end web applications</a>. Choosing which application will do which job is often more of an art than a science, as there is usually considerable overlap.

For example, should you use Moodle to store content, or should you use a content management system? Much depends on how you expect people to use the whole system and on your priorities. In this example, if you wanted to handle different versions of content you wouldn&#8217;t use Moodle, but then you may need to find some way of displaying the content as part of a user&#8217;s learning pathway inside Moodle.

## Define the data flows

This flows out from the application choice, the reporting requirements and the user journeys. You should be able to produce a diagram that shows:

  * Each piece of data that needs to be used
  * The data source
  * The data recipient
  * What triggers the data to flow between the source and recipient

This is starting to get into quite a deep level of detail, and may be better done as a separate technical session.

## Agree roles and responsibilities

It&#8217;s vital that the whole team understand who is going to be responsible for what.

In the table below, I've listed a set of typical tasks in an agile project (although you could easily rewrite the terminology for other project management practices) along with the generic role that would be responsible for doing that task.

As you can see, the Product Owner role is key. In my experience, when you have someone, who really understands what the product is trying to achieve, working closely with the delivery team, then you are much more likely to create something that provides enduring value.

The Product Owner will be involved on a regular basis, specifying what needs to be done next, testing what has been done so far, and generally keeping the product on track.

Critically, the Product Owner must be empowered to make decisions.

[table id=1 /]

## Agree project management approach

I like the <a href="http://en.wikipedia.org/wiki/Agile_management" target="_blank">Agile</a> approach, as it keeps timelines short and focussed and allows for iteration. But a lot of people are more comfortable with a <a href="http://en.wikipedia.org/wiki/Waterfall_model" target="_blank">Waterfall</a>/<a href="http://en.wikipedia.org/wiki/PRINCE2" target="_blank">Prince2</a>™ way of running projects, where all the requirements are written up front, then the development is done, and then it&#8217;s all tested.

> Agile projects are variable scope and fixed time. You deliver some new value with every release, even if you don&#8217;t always know in advance exactly what you can deliver in the allotted time. There are many benefits to this approach. You eliminate the risk that you will never deliver anything. You show your work after every iteration, so that everyone who works with you can see the status of the project. You get regular feedback on new features so you can improve them.
>
> <p style="text-align: right;">
>   from: <a href="http://www.continuousagile.com/unblock/iteration.html" target="_blank">Continuous Agile: iterations, releases and milestones</a>
> </p>

Whichever approach, or <a href="http://software.ac.uk/blog/2012-04-16-marrying-prince2-agile-development" target="_blank">combination of approaches</a>, you choose, you will need to agree that approach with all parties. This is especially true for new teams, so that you create a shared understanding of how the project will work. It can be really difficult to move from a predominantly waterfall culture to using agile techniques, or to pull together people from different cultures. To change cultures, it&#8217;s good to be very explicit at the beginning and to keep reinforcing the message throughout the whole process.

## Agree key dates

Milestones are usually good to aim for (although <a href="http://blog.michaelhamrah.com/2012/01/agile-its-a-war-on-dates/" target="_blank">some people disagree</a>!). These might be fixed while the scope flexes (<a href="http://en.wikipedia.org/wiki/Timeboxing" target="_blank">time-boxing</a>), or might vary while the scope remains constant. That depends on your preferred project management approach. But a set of dates will often help to provide impetus to the project.

## Identify risks

At the beginning of the project, the risks you identify will probably be quite general &#8211; around key team member absences for example. But get them down anyhow. Alongside each risk, its likelihood of occurring and its impact if it occurred, you should also detail what you are going to do to mitigate it (eg. have deputies for key roles).

As the project proceeds, keep the risk log up-to-date and encourage the team to submit new risks. As soon as a risk is identified, it can then be managed so it becomes less of a risk.

Many project managers use a RAID log, which is generally a simple spreadsheet, with separate tabs for Risks, Assumptions, Issues and Decisions. Note that some people use A for Actions. if you do that I would suggest having a RAAID log, as it&#8217;s still important to track any assumptions you&#8217;re making!

<a href="https://docs.google.com/spreadsheets/d/1PwTCx9pu5RkbvYHicAmc1Yv8Q5xy4gW2QhFO7hwHf-I/edit?usp=sharing" target="_blank">View Wyver Solutions RAID template</a>

## Identify workstreams and dependencies

In all but the simplest project, there will be multiple workstreams needing to happen at once. I will discuss in a later article the different workstreams in a typical learning technology implementation.

At this early stage in the project, you&#8217;ll need to map out roughly how each workstream is related to the others. In particular note the points where a workstream would be blocked from delivering if they don&#8217;t have the products from another workstream.

## Identify high-level tasks within the workstreams

Already, as you&#8217;ve worked through the requirements, expectations and data flows, you will have started to map out the work that needs to be done.

This will often form the basis of a scoping document against which a supplier can price up the work required. Obviously the more detail that you can go into the better, but, at this stage, you&#8217;ll probably just be chunking up the work into bundles of work that make sense for the context of the project. A typical content project, for example might be broken down into modules, whilst a learning management system implementation project could be broken down into functional elements, integration points and infrastructure setup. (Please note that these breakdown examples are far too simplistic for real-life!)

## Identify priorities

Whilst everything seems to be important at the beginning of a project, there will be some things that need to be ready first. Much of this will come out of the dependency mapping exercise. But it&#8217;s also useful to be able to release early versions of the end product to stakeholders in order to gain further buy-in from them.

For these reasons, part of the planning process is to identify the order in which things should be done.

The sample, much simplified, dependency map shown below might give some idea of how this could work. Each step builds on the next. The ideal is that at each review or release stage there is enough for reviewers/users to have something useful that works.

## Identify assumptions

Alongside the Risks log, keep track of any assumptions you have made. Ensure that these are explicit and tested with as many stakeholders as possible. And be aware of what the implications would be if these assumptions turned out not to be true.

The <a href="https://docs.google.com/spreadsheets/d/1PwTCx9pu5RkbvYHicAmc1Yv8Q5xy4gW2QhFO7hwHf-I/edit?usp=sharing" target="_blank">Wyver Solutions RAID template</a> has a tab dedicated to Assumptions tracking.

* * *

Look out for the second instalment of this series, in which I will be exploring what happens after the kick-off: Project setup
