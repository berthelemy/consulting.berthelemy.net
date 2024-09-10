---
title: 'Content Conundrum'
author: Mark Berthelemy
excerpt: Considerations on choosing a content authoring strategy
layout: post
permalink: /2020/08/20/content-conundrum
tags:
  - Content management
  - Solution design
  - Supplier selection
thumb: /post-images/2020/08/question-mark-1872665_455.png
banner: /post-images/2020/08/question-mark-1872665_900.png
alt: Question marks
img-credit: <a href="https://pixabay.com/illustrations/question-mark-important-sign-1872665/" target="_blank">Pixabay</a>
---
Earlier this week, I put a post on LinkedIn asking for vendors to get in touch if they could meet the following requirement:

> I want to be able to make changes to content "on the fly".

The normal process for externally authored content is:

1. Create
2. Export from authoring tool
3. Import to LMS
4. Edit
5. Re-export from authoring tool
6. Re-import to LMS

What I'm looking for is:

1. Create
2. Make available in LMS
3. Edit
4. Nothing else - any edits (eg. typos, image changes) would be automatically available to the end-user

There were **lots** of responses to that original post. And a number of people who were watching the thread just to see what came of it.

So, this post is a summary of what I discovered, and my conclusions.

But first, an overview of **all** the requirements:

#### Business requirements

- To produce a large number of online scenarios and reference content
- For use in low or zero bandwidth areas
- In multiple languages

#### Functional requirements

1. Able to create interactive materials (eg. questions, branching) as well as more straightforward text and video content
2. The text content must be searchable from inside the LMS platform (Moodle)
3. The content must work offline in the Moodle Mobile app
4. The content must offer a simple workflow for handling translations
5. I must be able to edit content easily after it has been published
6. The interactive content must pass a grade to the Moodle Gradebook
7. An efficient author, review, edit, publish workflow

#### Most likely solution

Given that we're using Moodle, I also have access to the [Book](https://moodle.org/plugins/mod_book) and [H5P](https://moodle.org/plugins/mod_hvp) plugins.

This meets the functional requirements as follows:

1. I can create interactive exercises, even complex branching scenarios in H5P, and then embed them in a book, which then becomes like a "traditional" elearning module (except without the automatic bookmarking that SCORM offers - but I can live with that)
2. The book content is searchable using Moodle's search engine. I don't need the H5P content to be searchable, as that's just providing the practice activities, not the resources.
3. Both the Book and H5P modules work in the Moodle Mobile app when offline, and synchronise any data back to the server when back online
4. All content within a Moodle course can be translated using the workflow developed by [Quabiria](https://qabiria.com/en/blog/item/552-how-to-translate-a-moodle-course). From experience with the company I know the process works very smoothly (except if the Moodle administrator - me - moves question banks around 😞)
5. All the content built inside Moodle can be edited using Moodle's built-in tools.
6. H5P passes a grade to the Gradebook, and also to an xAPI Learning Record Store if you have one
7. I could use an external tool like [Diigo Premium](https://www.diigo.com/premium) or [PageReview](https://pagereview.io/) to add collaborative comments to pages. And make careful use of Moodle's roles and permissions to give certain people ability to view things prior to publishing.

#### Why not use SCORM?

Again, looking at the functional requirements:

1. Yep - that's OK. All SCORM authoring tools allow interactive exercises in some form or other
2. Nope - SCORM packages are pretty much inaccessible to any external search engine, unless the imsmanifest.xml file is designed to explicitly reference every HTML page
3. Yep - Moodle can download SCORM packages to the App - but **only** if the content is hosted on Moodle. Which conflicts with requirement 5.
4. Sort of - I would require two translation workflows, one for the Moodle course content (eg. quizzes) and one for the externally authored content. Not impossible, but not ideal.
5. Yep - But only if the content is hosted by the authoring tool. Which then conflicts with requirement 3.
6. Yep - SCORM does this very simply. For anything more complex we'd need to move up to xAPI, as with the H5P solution.
7. Yep - Most of the server-based tools are pretty good on the reviewing workflow. That's their real strong point compared to the client-based tools.

#### Package Exchange Notification Services (PENS)

[PENS](https://scorm.com/pens/) is an ancient, standards-based way to publish directly to an LMS. However it seems to be very rarely supported, by either authoring tools or learning management systems. Some people think it's a bit "meh".

#### What about the authoring tools you looked at?

So, back to the original request, for on-the-fly editing... Although I now have a solution, there will be some people that still want a basic SCORM approach, so here are some tools to consider. All of these provide a content hosting solution that allows changes to flow through directly to the user via the LMS:

- [Gomo](https://www.gomolearning.com/what-is-gomo/delivery-analytics/)
- [Rhapsode from Area9Lyceum](https://area9lyceum.com/) - NB. This is far more than just an authoring tool!
- [Thirst.io](https://thirst.io/) - also comes with a Moodle plugin
- [Elucidat](https://www.elucidat.com/)
- [Xyleme](https://xyleme.com/)

#### But what about all the other authoring tools?

Straightaway you can discount any tools that sit on your PC, unless they have a server component.

So, that leaves tools like [Evolve](https://www.evolveauthoring.com/), [Rise](https://articulate.com/360/rise), [Genie](https://www.growthengineering.co.uk/genie-content-authoring-tool/), [Lectora Online](https://www.lectoraonline.com/) and [Courselab](http://www.courselab.com/). All good tools in their own right, but they all seem to offer the traditional export to SCORM deployment route only.

#### Other alternatives

If I wasn't worried about SCORM, then I could just embed content using iframes, from tools such as:

- [Sway](https://sway.office.com/)
- [Grav](https://learn.hibbittsdesign.org/opencoursehub/integrating-grav-with-moodle)
- [H5P.com](https://h5p.com/) - Great if you don't have a platform that directly supports H5P

#### [Edit] All in one platforms

In the original version of this post, I forgot to mention those platforms which, like Moodle, incorporate both the LMS and the content authoring capabilities.

There are a growing number of these, aimed at contexts where usability is more important than content portability.

Examples include:

- [My Learning Hub](https://www.mylearninghub.com/)
- [Thrive LXP](https://www.thrivelearning.com/products/learning-experience-platform)
- [Netex ContentCloud + LearningCloud](https://www.netexlearning.com/en/contentcloud/)
- [Unicorn LMS](https://www.unicorntraining.com/lms)
- [LearnDash](https://www.learndash.com/)

[End edit]

What would you do in my shoes?
