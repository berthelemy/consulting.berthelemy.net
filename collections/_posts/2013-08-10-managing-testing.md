---
title: Managing testing
author: Wyver Solutions Admin
excerpt: Testing is one of those tasks, like writing documentation, that most of me tend to avoid until absolutely necessary. A good test process, however, should help to ensure that you deliver exactly what the client ordered, and allow you to prioritise fixing problems in the your solution.
layout: post
permalink: /2013/08/10/managing-testing/
tags:
  - Project management
---
I often work on large projects where at least some elements of the solution are bespoked for the client, whether it&#8217;s code, application configuration, administration processes or workflows.

Just designing the solution isn&#8217;t enough. As learning solutions **architects**, it&#8217;s my responsibility to make sure the finished product meets the client&#8217;s requirements, is fit for purpose, and won&#8217;t break the first time someone uses it.

Having a rigorous testing process is essential to fulfilling that responsibility. It allows me to document what has been tested, by whom and when, and to map those tests back to the client&#8217;s requirements.

Each part of the solution should really be tested, unless you are using off-the-shelf software, with no special configuration, no customisation, and no client-specific processes. Until your whole system can be called &#8220;tried and tested&#8221; then testing should remain a priority.

## Types of tests

Depending on the size of your project, and the number of interlinked systems or processes, you may have a number of different stages of testing activity, such as:

  * Unit testing &#8211; looking at each component part of one system
  * Unit link testing &#8211; looking at whether the &#8220;units&#8221; fit into their host system OK
  * Systems testing &#8211; looking at the whole of one system
  * Integration testing &#8211; looking at how the different systems join up
  * End-to-end testing &#8211; running the whole process through, from start to finish
  * Regression testing &#8211; making sure that things still work after new features or processes have been added

Each stage will have **Test Plans**, that link back to a **Test Specification** which contains **Test Cases**. In many situations, you will need to relate your test cases to one or more **Requirements Document(s)** which will have resulted from your discussions with the client. The Test Plans are executed for each **Release**, and results collected along with appropriate evidence.

Again, please note that this does not just apply to software &#8211; it applies to any system or process that you have to ensure works in a consistently reproducible way.

## Managing tests

As you can imagine, managing testing across multi-disciplinary teams, with multiple systems and a suite of Requirements Documents, can be pretty complex &#8211; particularly if you need to maintain an audit trail showing what has been done, when, why and by whom.

Spreadsheets are often the first port of call for collecting the information together. However, very quickly, you end up with multiple versions, used in different ways by different teams, with no easy way to track the data through them, and almost impossible to use to provide accurate reports.

The obvious solution is a multi-user, relational database that:

  * allows you to collect and refine requirements
  * contains all the information about the testing on a particular project
  * allows you to track different versions of the requirements and the tests
  * allows allows you to manage the different roles in the testing process
  * provides clear reports against each stage of the process

## Introducting TestLink

TestLink is such a product. It&#8217;s an open-source, PHP-based application. So, quite simple to setup yourself, if you have an available server.

As a TestLink administrator, I can set up multiple projects, and assigned users to each project, with different roles as appropriate.

There are then several main stages after that:

  1. <span style="line-height: 13px;">Draft and validate the requirements (although this is optional)</span>
  2. Create test specifications, containing test suites that will cover each of the requirements
  3. Create test plans for different stages of the project, which might look at particular test suites
  4. Allocate the tests for execution by individual testers
  5. Execute the tests
  6. Rework the tests based on feedback
  7. Rerun the tests
  8. Provide reports on passed or failed tests

The video below introduces a couple of the key features of TestLink: test specification and test execution:

http://youtu.be/7xH1LKQU1TA

If necessary, it&#8217;s also possible to connect TestLink to many of the leading issue tracking software tools like <a href="http://www.mantisbt.org/" target="_blank">Mantis</a> and <a href="https://www.atlassian.com/software/jira" target="_blank">Jira</a>, and also to testing automation tools, like Selenium.

Even on it&#8217;s own, I've found using TestLink to be a great way of ensuring that the whole requirements gathering and testing process is done in a rigorous way.

Of course, that rigour is only as good as the test cases that have been written. It&#8217;s easy to fall into the trap of just writing test cases to prove that the system works as designed, without checking to see how far you can push it before it breaks.

There&#8217;s a bit of an art to writing test cases that try to replicate real user behaviour. Often, it&#8217;s not until you first try the whole system with real people, that you find many of the bugs. At that point, it&#8217;s important to create the process of replicating the bug as a test case so you can make sure it doesn&#8217;t get missed again.

 [1]: http://teamst.org
