---
title: 'The future of SCORM?'
author: Mark Berthelemy
excerpt: Does SCORM even have a future in modern learning architectures?
layout: post
permalink: /2021/07/26/future-of-scorm
img: 2021/gift-4663231_1280.jpg
imgalt: Box covered in wrapping paper
imgcredit: Bellahu123 on Pixabay
imgurl: https://pixabay.com/photos/gift-christmas-birthday-4663231/
tags:
  - Standards
  - Advocacy
  - Moodle
  - Content management
---
Recently I wrote the following [post on LinkedIn](https://www.linkedin.com/posts/markberthelemy_scorm-versions-the-evolution-of-the-elearning-activity-6820236617282797568-QmWc):

> SCORM was designed for one context: military training. They needed to capture whether a trainee had "mastered" a skill. The rest of the world dumbed that down to scoring x% in a recall-based multiple choice test. They needed to be able to deliver content on multiple LMSs across multiple unconnected establishments. The rest of the world forgot that we now have the Internet so don't need to package up content. They designed in a comprehensive metadata schema, so that content could be discovered and found. The rest of the world gives each package a title.

It led to some interesting responses, which I'll try to address here.

## A brief history of scorm

SCORM was created by the Advanced Defence Laboratory, part of the US Department of Defence, in 2000.

It was designed to solve three problems:

1. How to create digital training materials that can be packaged for delivery on multiple learning management systems.
2. How to enable learning system users to discover training materials for different audiences
3. How to enable learning systems to pass data (eg. scores) to the training materials and vice versa

It was designed for a world where data bandwidth was expensive and in short supply, so content needed to be stored on the user's own network wherever possible.

The solution devised brought together three components that had been developed separately:

1. A packaging format (ie. put all the files into a single ZIP file, with an XML manifest file to describe the contents of the package)
2. A set of metadata elements (eg. title, author, language, keywords, version, etc) which describe the packages
3. A means for data to pass between the package and the host system while the training is running

With the release of SCORM 1.2 in 2001, we had a workable version that many organisations signed up to. SCORM was even added to the specifications for school learning platforms in the UK, despite Dan Rehak (the chief architect of SCORM) stating that [SCORM was not appropriate for education](https://www.downes.ca/post/4410). [Side note: I was in the meeting where Dan Rehak said this, at the IMS Conference at Magna, Rotherham. Unfortunately, I can only find the linked indirect record of this statement.]

SCORM 2004 came along a few years later, with some significant enhancements. But, even now, very few providers and their customers have adopted this.

SCORM set in place the two part system that we now find in most organisations: the learning management system (LMS), plus the authoring tool (or tools).

The authoring tool is where the content is created. The LMS is where it's delivered.

## From the end user's perspective

Because SCORM content sits separately to its delivery system, it immediately raises issues for the end user:

### Popups and iframes

The content must be displayed in an iframe or, more commonly, in a popup window. Most browsers now block popups by default, so the user journey, for the first time, will be broken by needing to unblock. That's assuming that you're using a device that hasn't been locked down by your IT department. Iframes bring their own problems, with multiple vertical scrollbars often confusing users.

### Lack of metadata

Very few authoring tools allow you to add more than the bare minimum metadata (usually just title and description).

Even if they did, very few learning management systems know what to do with that metadata.

### Search

If the LMS allows users to search for content, all it will see, and all the users will find, is the metadata that the SCORM packages provide.

I have not yet come across an authoring tool/LMS combination where the user can search the whole text of the SCORM package, and be provided with a direct link to the relevant page or section. Is it impossible? I think so. But I'd be happy to be proved wrong.

## From the administrator's perspective

The split between authoring tool and delivery tool usually means that making even the tiniest change to the content requires a relatively complex workflow: Make the change; export the new version of the SCORM package; and import the SCORM package into the LMS. Version control can become a little bit of a nightmare...

Now, this can be alleviated with some of the [SAAS](https://en.wikipedia.org/wiki/Software_as_a_service) authoring tools, which keep the content on their server, while it's displayed in the LMS. But this still isn't common. And, with some of the older, client-based, authoring tools, not possible at all.

## My current approach

I have, where possible, removed SCORM from my learning architecture.

Instead, I use learning platforms which allow designers to create the content **inside** the platform, and where that content can be indexed and made searchable.

If using an open-source platform, like Moodle or Wordpress, it's then pretty simple to move content from one instance to another if required.

The user experience is contained within, and completely under the control of, the learning platform. So we have no excuse not to get this right.

(And for those who say that Moodle doesn't do version control well, you're right. But there is a very capable [version control plugin](https://www.opensourcelearning.co.uk/moodleversioncontrol) to deal with this issue.)

## The future

I am hopeful that we will come up with a way to move content between authoring tools and delivery platforms, where the content can be integrated tightly into the platform and its user experience. Not sitting in a separate package.

That would require some agreement on the essential [types of activities and resources](https://edtechnow.net/2012/04/03/what-do-we-mean-by-content/) you'd want to use.

I think we need to end up with a standard to describes those activity and resource types. Like [Docbook](https://docbook.org/) for technical documents, [JATS](https://jats.nlm.nih.gov/) for journals, or [RSS](https://en.wikipedia.org/wiki/RSS) for news articles.

Where content is too complex to model in a standard (eg. a game or simulation), then it would be embedded as a SCORM package, and data transferred in the same way as now.

Let's keep the discussion going on [LinkedIn](https://www.linkedin.com/posts/markberthelemy_scorm-versions-the-evolution-of-the-elearning-activity-6820236617282797568-QmWc/).

## Further reading

[Stephen Downes: Dan Rehak: SCORM is not for everyone](https://www.downes.ca/post/4410)

[Crispin Weston: Proposed W3C priorities for education](https://edtechnow.net/2015/02/22/w3c_priorities/)

[Crispin Weston: What do we mean by "content"](https://edtechnow.net/2012/04/03/what-do-we-mean-by-content/)
