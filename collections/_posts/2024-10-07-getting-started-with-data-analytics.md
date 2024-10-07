---
title: 'Data analytics'
author: Mark Berthelemy
excerpt: How to get started
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/10/07/data-analytics
img: 2024/10/chart-8305514_1280-853.jpg
imgalt: Generated image of charts and graphs
imgcredit: u_3u3n7wt5sr on Pixabay
imgurl: https://pixabay.com/illustrations/chart-technology-graph-future-8305514/
tags:
  - Solution design
  - Information architecture
  - Open source
---
If you've got a background in database design, data modelling or data visualisation then this article is not for you. Instead it's for the people who want to understand their data, but don't know where to start.

By the time you get to the end, you may decide that the learning curve is too steep and not for you. But at least you will have some of the language to use with a professional data analyst.

Let's begin by considering some of the main parts of any data analysis setup:

1. Data source(s)
3. Models
4. Questions
5. Visualisations
7. Dashboards

We'll look at this from the perspective of a typical learning & development team within a training company. With that, you can then recontextualize it to a large corporate, or to many other scenarios.

## Data source(s)

Now, our training company, will have lots of information about its operation. Often this is scattered across multiple systems. You might have a marketing campaigns system (like Mailchimp), a booking system (like Administrate), a delivery system (like Moodle), and an evaluation system (like SurveyMonkey). Some companies use all-in-one systems, like Learnworlds, Thinkific, Teachable, Kajabi or Circle.

In either case, there's a lot of data flying around about your marketing, booking, delivery and evaluation operations.

Depending on your level of access to the system(s) involved, you might be able to reach directly into the database, or you might be reliant on exported spreadsheets or CSV files.

The former will give you more control and access to up-to-date information, but it won't come easy! The latter is often easier to work with, but each time you want to analyse the data, you'll need to re-export all the files.

Let's take the example of a list of customers. I've taken the list of 1,000 sample customers provided by [Datablist](https://www.datablist.com/learn/csv/download-sample-csv-files) and imported that into the open-source analytics tool, [Metabase](https://metabase.com).

<div class="grid">
<div markdown="1">
![Screenshot of a CSV file](/post-images/2024/10/screenshot1.png)
</div>
<div>
<article>
<p>Note the personal information contained within this data extract.</p>
<p>To stay within the law, you need to ensure that your CSV files have the same levels of security as the data within your database. Or avoid extracting personal data into the CSV files in the first place.</p>
</article>
</div>
</div>

## Models

So, now we have a single data source. If we were being even more sophisticated, we'd join this up with other data sources, to make a "Model". For example, combining the list of customers with a list of purchases.

That starts to get really complex - often involving a tool using Structured Query Language ([W3 Schools - Introduction to SQL](https://www.w3schools.com/sql/sql_intro.asp))

Models are at the heart of most data analytics projects. Defining them so they're useful and efficient is quite an art - but there's a lot of science involved too - often called Dimensional Data Modelling (see article from ThoughtSpot: [A complete overview of dimensional data modelling](https://www.thoughtspot.com/data-trends/data-modeling/dimensional-data-modeling))

In our case, we'll just simplify the model we're using by removing some of the fields people won't need to use.

![The simplified model](/post-images/2024/10/screenshot2.png)

## Questions

<div class="grid">
<div markdown="1">
It's helpful to have an idea of the sorts of questions that people will want answered before you even start collecting data. Often that's not possible. Especially if using off-the-shelf software. But at least think about the questions when designing your model.

In our case, let's consider the questions people might want to answer about your customers. For example:

- How many customers do we have?
- Where do our customers come from?
- What events cause customers to subscribe?

When you're considering the questions, also consider why you need them answered. Don't raise a question just because the data is available - make sure it is meaningful and useful.
</div>
<div markdown="1">
![Answering a question](/post-images/2024/10/screenshot3.png)
</div>
</div>


## Visualisations

Once you know what people want answered, then you can start thinking about how to present the data. It's not always obvious...

For example, you might think that a map is the best way to show how many people are coming from each country. In our case, though, Leichtenstein is our top country, and there's no way you'll see that on this map!

![Visualising countries](/post-images/2024/10/screenshot4.png)

Perhaps a simple table would have been best?

## Dashboards

Dashboards are collections of visualisations designed for a specific audience. They give a snapshot view of the data, and, ideally, allow the user to drill down into the source data model if they wish.

Analytics software will give you the tools to help you understand the data. For example, in this dashboard, you'll see from the trend line that the number of new customers is gradually going down. That's not a problem, as long as your business model can handle a plateau in new customers.

![Dashboard](/post-images/2024/10/screenshot5.png)






