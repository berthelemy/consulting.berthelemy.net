---
title: 'How to integrate systems'
author: Mark Berthelemy
excerpt: There will come a point in everyone's software journey when they'll want two or more systems to "talk" to each other. 
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/04/21/how-to-integrate-systems
img: 2024/f-14452760238_36ff533723_k.jpg
imgalt: Tangled cables 
imgcredit: Cory Doctorow (Creative Commons)
imgurl: https://www.flickr.com/photos/doctorow/14452760238
tags:
  - Standards
  - Solutions architecture
  - Open source
---
There will come a point in everyone's software journey when they'll want two or more systems to "talk" to each other.

This article will explore several ways to do this. But first, let's think about what we mean by software talking to each other - also known as "integration".

Generally, this involves <mark>data</mark> flowing from one system to another, so it can be processed or used within the recipient software. The data flow happens at a certain point in time, based on a <mark>trigger</mark>.

For example, one of the most common integrations is email. The data that you create in your email tool, when you click "Send", passes through a sequence of stages to eventually arrive at the tool used by the person receiving the email.

To make this happen seamlessly and robustly is way more complicated than you might think!

## Integration examples

- Posting an entry into your accounts system when someone makes a card payment using your payment processor
- Enrolling a user into a learning platform when the person purchases a course from your website
- Posting a message in your organisation's collaboration platform when someone leaves a support request in your helpdesk tool
- Raising a support request with IT when a new starter is added to your HR system
- Posting a message in your collaboration platform when a project task is overdue

The possibilities are endless...

## Mapping things out

Generally, integrations between two systems can be reasonably easily mapped and unpicked. Introduce a third, and the problem increases exponentially. The likelihood of getting into a complete tangle is huge.

This is because many integrations are done as a point solution. Someone decides they need a particular system to send some data to another system, without taking into account what is already there or what might be needed in the future.

To do integrations well, you need to define:

1. Which system is the <mark>system of record</mark> for a particular type of data
2. The format of the data to be sent and received
3. Any processing that should take place to convert from one format to the other
4. What will trigger each movement of data
5. The checks that will take place to know the integration is working
6. What happens when things go wrong
7. What records should be kept about each data transfer for troubleshooting purposes

## Swivel chair integrations

OK, this is a little tongue-in-cheek, but it's the starting point for many integration journeys. You have two systems, and a person literally taking data from one, and putting it in the other.

Of course, the person needs to know the trigger - is it every day at a certain time? When something happens in the source system? Or when the receiving system needs a certain piece of data?

Do they take all the available data? Or just what's changed since last time?

Sometimes the person might need to manipulate the data as it moves across. They might need to change a field name, or check that the data is clean (eg. no duplicates).

And then they'll need to ensure that the data has arrived safely and in the right places.

Already, you're starting to see the sort of things that need to be taken into account as you automate.

## File-based integrations

Most commonly, you'll see CSV files exported from one system, transformed and then imported into the receiving system.

For a full automation, the process needs to be able to handle errors gracefully.

One project I worked on, the sending system created a CSV file every night, each with a timestamp in the file name. The files were stored in a particular folder.

Later that night, the receiving system looked in the folder for a new file. If there was no file, or if it encountered an error in the data, the software logged the issue and sent an email to the system administrator to fix in the morning.

To create this sort of integration, you need to carefully define the data format, the timings, the locations, the filenames and the types of errors that you will handle.

## API-based point to point integrations

API's (Application Programme Interfaces) are the next stage on the integration journey. Instead of files being transferred via a third-party storage location, the two systems talk directly.

They usually rely on one of the systems making an <mark>endpoint</mark> available. This is like a doorway to the software. That endpoint has an address, and it accepts certain messages. Those messages can be used to ask for data, to send data, or to make changes to data.

The other end of the API relationship has to talk the same language. Often, with point solutions, this requires the software developers to write special code using documentation from the other system's developers.

## Middleware-based integrations

Middleware is a piece of software that acts as a "go-between". It speaks the language of each API, and translates messages from one system to the other.

For popular software, with published API documentation, there are a number of off-the-shelf middleware solutions, such as [IFTTT](https://ifttt.com/){:target="_blank"} and [Zapier](https://zapier.com/){:target="_blank"} and Microsoft's [Power Automate](https://www.microsoft.com/en-us/power-platform/products/power-automate){:target="_blank"}.

If you want an open-source middleware system, you should look at [Myddleware](https://www.myddleware.com/){:target="_blank"} - it's highly capable and adaptable.

At the high (and very complex) end, you might look at [Boomi](https://boomi.com/platform/integration/){:target="_blank"} and [IBM Websphere](https://www.ibm.com/products/websphere-application-server){:target="_blank"}

## Standards

Life is so much easier when you don't have to reinvent the wheel each time. It's a clich&eacute;, I know. But it applies so much in this context.

Wherever possible, seek out systems that use standards-based APIs or file formats. They can form a reusable set of building blocks to solve your integration problems.

We're starting to see this approach in a number of sectors - in health ([US Health IT](https://www.healthit.gov/isa/understanding-emerging-api-based-standards){:target="_blank"}), in communications ([NetworkComputing.com](https://www.networkcomputing.com/networking/how-standards-based-apis-are-revolutionizing-communications-industry){:target="_blank"}) and even in Human Resources ([HR Open Standards](https://www.hropenstandards.org/){:target="_blank"}).

The more we ask for them as customers, the more likely the vendors will start to support them - even though they don't really want to. Open standards make it much easier for customers to change suppliers...