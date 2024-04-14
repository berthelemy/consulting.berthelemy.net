---
title: 'Standards based learning content'
author: Mark Berthelemy
excerpt: 
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/04/14/course-design-standards
img: 2024/40635833271_dde1f2506f_k-1200.jpg
imgalt: Representation of Tetris - blocks fitting together 
imgcredit: Gerlos on Flikr (Creative Commons BY ND)
imgurl: https://www.flickr.com/photos/gerlos/40635833271
tags:
  - Standards
  - Content management
  - Solutions architecture
---
Elearning content has, since 1993, been distributed in "packages", whether AICC, SCORM or CMI5 (see [previous article introducing elearning standards](/2024/04/05/elearning-standards)).

This has some important advantages, namely that the package is immutable. It can't (or at least shouldn't) be changed by anyone else. The end user will see it exactly as the original designer intended.

It's similar, in a way, to PDF files. These were designed for graphic designers to be able to distribute their materials in a print-ready format - never to be edited.

Unlike a PDF file, the elearning package model has some serious disadvantages:

- The host platform's view of the content is only what the learning designer has provided in the package metadata
- It cannot be searched in a way that users can be sent directly to the part they need
- It cannot be repurposed and contextualised without the original source file

Scroll forward to 2024, with media and learning platforms such as TikTok, Youtube etc. Video files can be edited, repurposed and searched. Looking for content on how to use XLOOKUP in Excel or Google Sheets? You'll be directed to the specific point in the video which tells you.

## Separate content from presentation

Rather than putting **everything** into the package, I propose that we treat content more like data than a print-ready design.

In this case, a content package would comprise simple text files, along with associated graphics. The text files would be structured data describing the content. For example (using a DITA XML file for illustration [DITA Tutorial](https://www.xmlmind.com/tutorials/DITA/index.html){:target="_blank"}):

```
<task id="make-tea">
  <title>How to Make a Cup of Tea</title>
  <taskbody>
    <context>
      <p>Follow these steps to brew a delicious cup of tea.</p>
    </context>
    <steps>
      <step>
        <cmd>Boil fresh, cold water in a kettle.</cmd>
      </step>
      <step>
        <cmd>Place a tea bag or loose tea leaves in a mug.</cmd>
      </step>
      <step>
        <cmd>Pour the boiling water over the tea.</cmd>
      </step>
      <step>
        <cmd>Steep the tea for 3-5 minutes, depending on the type of tea.</cmd>
      </step>
      <step>
        <cmd>Remove the tea bag or strain out the loose leaves.</cmd>
      </step>
      <step>
        <cmd>Add any desired sweeteners or milk.</cmd>
      </step>
      <step>
        <cmd>Enjoy your freshly brewed cup of tea!</cmd>
      </step>
    </steps>
  </taskbody>
</task>
```

Created by Perplexity.ai ([link to Perplexity prompt and response](https://www.perplexity.ai/search/Please-create-instructions-ALOk.EFcQPSveDApTiQmLA#1){:target="_blank"})

The host system would then **parse** the file to display the data in its own way. For example, in this website, the data might end up looking like:

> ### How to make a cup of tea
> 
> Follow these steps to brew a delicious cup of tea.
>
> 1. Boil fresh, cold water in a kettle.
> 2. Place a tea bag or loose tea leaves in a mug.
> 3. Pour the boiling water over the tea.
> 4. Steep the tea for 3-5 minutes, depending on the type of tea.
> 5. Remove the tea bag or strain out the loose leaves.
> 6. Add any desired sweeteners or milk.
> 7. Enjoy your freshly brewed cup of tea!

Of course, the data structure would be way more complex for things like branching scenarios, and multiple choice questions. But hopefully you can imagine what I'm getting at.

## Why is this important?

Separating data from presentation is a common (and highly recommended) approach, used across the IT world.

It allows you to:

- Create multiple outputs (website, training manual, Powerpoint slides etc) from a single source
- Quickly change the branding across multiple resources simply by changing the theme used by the host system
- Quickly create content that adheres to the design rules set for the whole site. Just like this article. It was created using a YAML data file, which is then processed into HTML via the same template used for every article. It would be crazy to try to recreate the design manually each time.
- Reuse and remix chunks of content easily 

If that data is in a standard format, then there's an added advantage that the content can be edited by any tool adhering to the standard. Just as we do with Word documents, videos etc. You wouldn't be locked in to your authoring tool.

## Existing examples

You can already see this happening in parts of the learning technology world:

### DITA

DITA is a specification for creating structured technical documentation. It's well established in many industries, and includes a "[learning and training specialization](https://www.oxygenxml.com/dita/1.3/specs/archSpec/learningTraining/learning-and-training-specializations.html){:target="_blank"}" with support for a small number of interactions, like multiple choice questions. Unfortunately, the available tools to create structured content like this are generally complex to use, often requiring good knowledge of XML or the DITA specification. And the support for DITA files is sadly lacking across the majority of software seen in the learning technology space.

### H5P

H5P is an open-source content creation tool that can be installed into any Moodle, Wordpress or Drupal platform, or used through the online H5P editor. It includes a [wide range of interaction types](https://h5p.org/content-types-and-applications){:target="_blank"} and creates files that can be imported into sites, and then edited within that site.

The files simply contain data that describes the content and how it should behave. The look and feel of the content is defined within the [H5P specification](https://h5p.org/documentation/developers/h5p-specification){:target="_blank"}, with the ability to be overridden (with care) by the host system. H5P is not yet widely used outside of the platforms listed above

### Adapt

Adapt is also open source, with its authoring tool used by several companies within the UK learning technology sector in particular.

When Adapt was first launched, I had great hopes that its JSON-based description of learning content would become the standard by which we describe and share such materials. Unfortunately this has not proved to be the case. The [Adapt specification documentation](https://github.com/adaptlearning/documentation/tree/master/01_cross_workstream/content_specification){:target="_blank"} seems to have not been updated for 11 years.

Rather than improving and promoting the standard, the focus seems to be on a core toolset which is then extended into proprietary formats for each company involved. The standard then becomes as useful as a four pin plug on a toaster.

### Moodle

Moodle is able to export a whole course as a series of XML files. These describe how the materials should function and include all the contents of the course. The look and feel of the course will depend greatly on the theme pack and course format plugins used in the host system. Of course, this is exclusive to Moodle.

In theory there is nothing stopping anyone taking the data format and using it in their own software. In reality, though, there is little to no documentation describing the structure of the XML files, so it would need a lot of reverse engineering to make this happen.

### Proprietary software

[Xyleme](https://xyleme.com/){:target="_blank"} is a Learning Content Management System (LCMS), based on an XML database. The content is structured, just like DITA, but in a proprietary format.

It's fantastic for single-source publishing to multiple formats, but only within its closed ecosystem. (Full disclosure: I have worked with Xyleme in the past on implementation projects).

[ExactLS](https://www.exactls.com/products/lcms/){:target="_blank"} does something very similar with their LCMS tool.

Neither are likely to ever publish their data formats, so the content will remain only in their environments.

## The future

I would love to see a standards-based data format for rich learning materials.

1. It would improve competition between the authoring tools, as there would be no vendor lock-in. (Just try suggesting to an organisation that they move from Articulate Rise to Evolve Learning for example. The design team will have kittens!)
2. It would mean that host systems will be able to parse content fully and make it available through search engines and AI chat bots.
3. As an industry we could make a common effort towards defining what we do, how it works, and how we should improve things.

Just as the IT industry has gathered around the USB-C standard for interconnections between devices, a learning design standard will be a solid platform for ensuring interoperability and increasing the size of the market.
