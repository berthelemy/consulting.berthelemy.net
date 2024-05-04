---
title: Introduction to APIs
published: false
author: Wyver Solutions Admin
excerpt: I look at Application Programming Interfaces (APIs) and how they can help to join up systems by sharing data using a standardized, documented interface.
layout: post
permalink: /2013/06/12/introduction-to-apis/
tags:
 - System implementation

---
<p style="border: 1px solid gray; width: 33%; padding: 4px; text-align: left;">
  Read this in conjunction with my previous post on &#8220;<a title="Joining up your systems" href="{{ site.url }}/2013/06/03/joining-up-your-systems/">Joining up your systems</a>&#8220;
</p>

Some people describe APIs (Application Programming Interfaces) as the glue holding different software systems together.

A better analogy would be that of a plug and a socket.

Let&#8217;s say you want to join up two systems: a product catalogue (www.ProdCat.com) and a social media system (www.SocMed.com). The product catalogue can hold a range of different types of products, such as courses, books, videos. In fact, anything that has a title, a description, maybe a picture, and some categorizing information, like topics or &#8220;tags&#8221;.

The social media system simply allows users to post ideas and then tag them with topics.

The providers of the product catalog publish a description of their API. This will be a document that describes the locations of the different connection points, the purpose of each connection and how it should be used. Some of those connectors are designed to enable data to be retrieved, and some allow data to be sent.

The provider of the social media system then has to create a &#8220;plug&#8221; that can make use of those connectors; sending and receiving data to and from the product catalogue.

## Show me everything&#8230;

At its simplest, the social media system can send a request to the product catalogue which asks for the whole catalogue. Something like:

`http://www.ProdCat.com/<span style="color: red;">GetCatalogue</span>`

In this case, the product catalogue, assuming it has a connection called GetCatalogue, would respond with file containing all the information about all the products.

<p style="border: 1px solid gray; padding: 4px;">
  NB. The process of checking that a third party system actually has permission to get and put data is beyond the scope of this article &#8211; but it should be central to any API-based development.
</p>

The file sent by the product catalogue will be in a set format, as described in the API documentation. Most APIs use either XML or JSON to structure the data. This means that developers will know exactly where to find each piece of data, and can thus write programmes to work through the file and process it.

With the catalogue file, a developer working on the social media system can create a page within her system that displays product information from the product catalogue system.

Exactly how that information is displayed, sorted and filtered is entirely up to the social media system developer. Once they&#8217;ve got the catalogue data, they can do with it what they wish.

Remember that this isn&#8217;t a one-off process. The catalogue information can be retrieved as often as you like. However, many systems with published APIs will set a limit on how many retrievals can be made in a certain time. This is why it&#8217;s often good practice, when building a connector to an API, to &#8220;cache&#8221; (temporarily store) data when it&#8217;s retrieved.

## Show me some things&#8230;

Usually you wouldn&#8217;t want to download all the data provided by an API, but just a much smaller subset. For example, you might want to only display the products that have categories that are similar to the tags on a particular social media posts. End users would then see a list of relevant products alongside the posts.

If I was to retrieve the whole catalogue every time, I'd be using, and wasting, a lot of bandwidth. So most APIs will allow you to filter the data at source.

If I had a post tagged &#8220;leadership&#8221;, then I only want to retrieve products categorised under &#8220;leadership&#8221;. In this case, the call to the product catalogue might look like:

`http://www.ProdCat.com/GetCatalogue?<span style="color: red;">category=leadership</span>`

Multiple conditions can be set in the same call just by joining them together with &#8220;&&#8221;. For example:

`http://www.ProdCat.com/GetCatalogue?category=leadership<span style="color: red;">&image=true</span>`

Assuming the API understands the query, this would hopefully return a file containing all the products in the leadership category which have an image.

## Changing data in the other system

So, I've explored how I get data out of a system and display it to your end users. What if I want my users to be able to interact with the data; like buy a product or write a comment against it?

<p style="border: 1px solid gray; padding: 4px;">
  NB. This capability is often a sign of a mature, well-developed API. Without it, users will need to be sent to the other system to interact with it. Care must be taken to help users move between the systems smoothly. See my recent post on ### Joining systems together ###.
</p>

Assuming you&#8217;re working with an API that can receive data as well as send it, you&#8217;ll probably use a connector something like:

`http://www.ProdCat.com/PutComment?productid=abc1234&userfirstname="Mark"&comment="Great product"`

Breaking this down, I have a connector called PutComment, which can accept the following types of information:

  * productid
  * userfirstname
  * comment

So, in this case, the user (called Mark) has entered a comment (&#8220;Great product&#8221;) in a form on the social networking system, which was displaying details about a particular product (with the id: abc1234).

This information was passed back to the product catalogue as a set of parameters for the PutComment connector.

## Keep it simple

Obviously, sending data between applications can get pretty complex pretty quickly as the two systems become more and more tightly integrated.

It&#8217;s always a good idea to map out which system holds which data, and the &#8220;triggers&#8221; that will prompt data being moved between them. Without careful preparation and definition it can easily become very muddled.

My advice is to start as simple as possible, and plan to make incremental enhancements based on user feedback.

## Making APIs work

To get the best out of an API you need three things:

  1. Good API documentation with lots of examples
  2. Great planning, requirements gathering and solution design
  3. A developer who understands the capabilities, constraints and programming conventions of the system that the end users will be working in

Although I am not a developer myself, I can help you to understand and document your requirements, talk to your system providers, design solutions for developers to take forward, then source the developers and manage the project from start to finish.

Although these can often be complex projects, I will work on your behalf to simplify the process and translate your requirements into finished products with real benefits for your end-users.

[Contact me to discuss your requirements][1]

 [1]: {{ site.url }}/contact/ "Contact me"
