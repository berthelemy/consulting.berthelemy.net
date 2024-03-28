---
title: 'A service oriented architecture for corporate learning'
author: Mark Berthelemy
excerpt:
 I discuss a model for corporate learning and the principles behind it.
permalink: /2015/12/05/service-architecture-corporate-learning
layout: post
tags:
 - Learning design
 - Coaching
 - Solutions architecture
thumb: /post-images/2015/12/pixabay-blueprint-964630-thumb.png
banner: /post-images/2015/12/pixabay-blueprint-964630-banner.png
alt: Architectural blueprint
img-credit: <a href="https://pixabay.com/en/blueprint-ruler-architecture-964630" target="_blank">Pixabay</a>
---
The modern corporate learning environment is diverse and complex. As well as the &lsquo;traditional&rsquo; face-to-face courses, there is a whole range of different learning methodologies to be supported.

When designing a technology architecture to underpin this environment, I would recommend building on a few, key learning design principles (see references below):

1. Learning is a process of making connections with existing knowledge, ideas and concepts - tagged with an emotional context, or significance, which is used to help access those connections at a later date
2. People who are novices in any field are best served by a carefully structured sequence of practice activities to help get them to a stage at which they can be self-sufficient learners in that field
3. Knowledge, skills and behaviours can be helped to stay in long term memory through a process of spaced repetition
4. Self-sufficient learners need ready access to up-to-date resources - whether physical, digital or human, in order to solve problems and make decisions during the course of their work
5. Decisions about course or resource requirements should be underpinned by evidence

As a thought-experiment, I would like to propose an architecture as shown in the diagram below:

<a class="example-image-link" data-lightbox="service-architecture" href="/post-images/2015/12/learning-architecture.png"><img width="100%" class="aligncenter" src="/post-images/2015/12/learning-architecture.png" alt=""/></a>

Each component within the architecture is a designed as a service which can be called upon by any of the other components. That service could be realised through people, through a website, through a mobile app, or any combination of these.

#### Identity Management

A single identity management service, which contains all the personal profile and authentication information for any particular user makes it much simpler to plug in additional services which need that information.

Just as a student ID card gives access to any number of services within a university, so corporate identity management can allow people to use multiple services without having to continually provide credentials and personal data.

#### Search

An enterprise Search service should be able to:

- index all the information sources available to people within the corporate network
- display results to the user that are appropriate to their access levels

The latter is probably one of the hardest problems to solve within enterprise information networks. And so many organisations end up with a plethora of search engines - each for a different information resource.

The two simple answers are to either:

1. aggregate all the information sources into one system, or
2. rationalise access levels across multiple information sources, so that the data provided by the Identity Management service can be used to identify what information should be displayed to the user

Neither are actually that simple!

However, with search being the primary route to learning materials for people outside of work, it makes sense to try to replicate this as much as possible within work.

#### Personalisation

The personalisation service provides the means by which people get, as quickly as possible, to the learning resources and activities that they need.

What the user is directed to should be based on:

- what the organisation is trying to &ldquo;market&rdquo; at any point in time
- what the organisation considers mandatory for that particular user
- information supplied by the user, including:
    - preferences
    - interests
    - job title
    - diagnostic results
    - summative assessment results
    - what they've looked for in the past
    - content accessed
    - actions of people who are similar (eg. similar job titles) to the user

The latter set of data will come from other services within the learning architecture.

The Search service will provide data to the Learning Records service, such as:

    [UserID] searched for [search term] on [date]

#### Community

The Community service provides the ability to add human interaction capabilities at any point within the user's journey.

Sometimes you may need to have two, separate Community services. One to use within a closed, time-bound group - such as a course. And one for more general discussion and feedback.

However, the more the two can work in the same way, the better. Communities are notoriously difficult to start and maintain - particularly online ones. By keeping the way they work consistent (and simple), I reduce the inherent barriers to participation.

Note that the Community provides data for the Search service - thus providing a way to capture and reuse the tacit information held within the organisation.

The Community will also provide data to the Learning Records service, such as:

    [UserID] responded to [forum post] on [date]

#### Content

The Content service could actually be many services. Each one will provide data for the Search service, so that the content it contains can be found.

Content could be any form of digital materials:

- video
- text articles
- books
- audio
- animations
- tutorials

Or any combination of the above.

As with all content management, there is a balance to be kept between making materials as granular as possible and as integrated as possible.

Granular items can be reused in multiple contexts, and users can be taken to specific places to meet a specific need. An example would be an encylopaedia entry.

Integrated items provide a coherent package of information, which takes a user on a self-contained journey. An example would be a documentary film.

The ideal is to have both extremes at the same time - where content is built in integrated packages, but with the ability to use the Search service to look inside those packages, and jump to specific sections within them.

The Content service will also provide data to the Learning Records service, such as:

    [UserID] watched [x%] of [video] on [date]

#### Courses

The course service is important in any learning architecture - particularly for those people who are novices in a field. They require structured introductions to the field, and to the language used within it.

A course has boundaries - usually in terms of time and people. It will have a known time commitment from the user, and there will be expectations on the user and perhaps on tutors or peers to support the learning process. There is also a start and an end.

A course usually comprises a mix of resources and activities. The resources, in this architecture, will be provided by the Content service. The activities would be provided by:

- The Community service - for discussions, comments and conversation.
- The Assessment service - for diagnostic and summative assessments
- The Course service itself - for elements which cannot be delivered in any other means (eg. administration of events and groups of people)

The Course service will also provide data for the Learning Records service, such as:

    [UserID] completed [Course] on [date]

#### Assessment

The Assessment service provides the ability to supply:

- diagnostic assessments (to help the learner know what to do next)
- summative assessment (to provide evidence of capability)

Assessments can be in many forms; multiple choice, essays, observation etc.

The more there is at stake after the assessment, the more the Assessment service will need to be able to supply in terms of:

- validity - the extent to which an assessment measures what it's supposed to measure
- reliability - the extent to which the assessment gives the same result no matter when or where it is taken
- integrity - the extent to which users are unable to cheat the system

As each of those requirements increases, so will the necessary complexity of the Assessment service - particularly with regard to security and analysis of learner response data.

The Assessment service will also provide data to the Learning Records service, such as:

    [UserID] passed [Assessment] with a score of [x%] on [date]

    [UserID] answered [Question] in [Assessment] with [Answer], scoring [n]

#### Learning records

The Learning Records service collects and stores all the data sent to it from the other services.

This data can also be used by the other services - particularly the Personalisation service. For example, if a user has started to look at a resource, then that information will be in the Learning Records, and can be retrieved by the Personalisation service when the user next needs to be notified of what they could do next.

The Learning Records service will make its data available to the Analytics service.

#### Analytics

The Analytics service is designed to:

1. help service managers to make decisions about the future direction of their particular service
2. help the Personalisation service provide better guidance to individual users

It will help answer questions such as:

- What Content resources do I need to provide to answer user's questions to the Search service?
- Which Content resources are being underused?
- Where can I find an expert on topic &ldquo;x&rdquo;?
- How good are my assessments at differentiating accurately between people?

The Analytics service can be used in support of A-B testing, where a slight tweak is made to a service to see the impact of the change.

Note that, if the Analytics service also has access to performance data, then even more useful analysis can be made to answer questions such as:

- Does my &ldquo;x&rdquo; course have an impact on performance?
- How do high-achieving people use the learning services?

#### References

Caple, C. (1996) &ldquo;The Effects of Spaced Practice and Spaced Review on Recall and Retention Using Computer Assisted Instruction&rdquo;, available from: [http://eric.ed.gov/?id=ED427772](http://eric.ed.gov/?id=ED427772)

Siemens, G. (2005) &ldquo;Connectivism: A Learning Theory for the Digital Age&rdquo;, available from: [http://www.itdl.org/journal/jan_05/article01.htm](http://www.itdl.org/journal/jan_05/article01.htm)

Shackleton-Jones, N. (2010) &ldquo;Towards a working theory of learning: the affective context model&rdquo;, available from: [http://www.aconventional.com/2010/05/towards-working-theory-of-learning.html](http://www.aconventional.com/2010/05/towards-working-theory-of-learning.html)

Medina, J. (2014) &ldquo;Brain rules&rdquo;, available from: [http://www.brainrules.net/about-brain-rules](http://www.brainrules.net/about-brain-rules)
