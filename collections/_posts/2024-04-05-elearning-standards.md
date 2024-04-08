---
title: 'Introduction to elearning standards'
author: Mark Berthelemy
excerpt: 
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/04/05/elearning-standards
img: 2024/p-usb-1281034_1280.jpg
imgalt: USB C plug
imgcredit: Pixabay
imgurl: https://pixabay.com/photos/usb-type-c-cable-guy-two-1281034/
tags:
  - Standards
  - Supplier selection
  - Solutions architecture
---
It wasn't that long ago when each manufacturer had its own way of plugging in devices to charge. Standards help us to reuse chargers and cables, and to connect devices from different manufacturers.

It's the same with software. Standards allow software from different suppliers to work together. At least, that's the theory!

In this article, I'll provide a brief description of the key standards that apply in the elearning world. For each one you'll also find links if you want to dig further. Or give me a call.

But first, let's sort out one or two definitions. You'll see mention of <mark>standards</mark> and <mark>specifications</mark>. A standard is something that has been agreed by a recognised standard setting body, like the IEEE, ISO or even British Standards. A specification sets out how something should work, but it's not yet been formally agreed by a standards setting organisation. For the purposes of this article I'm going to use them interchangeably.

See: [Standards and specifications - what exactly are they? (USGS.gov)](https://www.usgs.gov/ngp-standards-and-specifications/standards-and-specifications-what-exactly-are-they){:target="_blank"}

## A note on versions

Just as there are different versions of USB plugs (USB A, USB C etc), the same is true of software standards. Often newer versions are "backwards compatible" with earlier versions. But not always. Sometimes things are changed so much the newer versions become incompatible. So, whenever you're talking to multiple vendors and want to rely on standards, make sure the versions they're using are compatible with each other.

The key standards and specifications you might come across within the elearning world are an alphabet soup:

AICC, CMI5, CSS, HTML, LDAP, LTI, Oauth, Open badges, Open Graph, RSD, QTI, SAML, SCORM, xAPI, XLIFF

There are many others - particularly those focussed on higher education. I won't be looking at those here, but you can find out more at [https://www.1edtech.org/](https://www.1edtech.org/){:target="_blank"}.

Let's group the standards together. For each group, I've listed the target audience - people who really should have at least a basic idea of what the standards help to achieve.

- [Learning specific standards](#learning-specific-standards): System selectors, solution architects, integrators, learning system administrators, project managers
- [Web standards](#web-standards): Learning designers, instructional designers, content developers, editors, learning system administrators
- [Translation standards](#translation-standards): Learning system administrators, system selectors, solution architects, project managers

Read on for more information about each standard, along with some links to help you become better acquainted.

## Learning-specific standards

### AICC (Aviation Industry Computer-Based Training Committee)

AICC is an early ancestor of all the current standards that allow learning content to work across multiple systems. Even though it was last updated in 1999, you'll still find systems that support it. Some people even prefer it as it allows content to be hosted separately from the learning management system.

[AICC (Wikipedia)](https://en.wikipedia.org/wiki/Aviation_Industry_Computer-Based_Training_Committee){:target="_blank"}

[AICC document archive (Github)](https://github.com/ADL-AICC/AICC-Document-Archive/){:target="_blank"}

### SCORM (Shareable Content Object Reference Model)

SCORM was developed by Advanced Distributed Learning (ADL), a branch of the US Department of Defence. It contains three elements: 

- Content packaging - including a "manifest" file to describe the structure of the content and the specification for how the content should be "zipped"
- Learning object metadata - a comprehensive list of pre-defined fields that authors can use, and systems should be able to read (I say should, because most corporate learning management systems fail to read and display almost everything except title and description)
- Run-time environment - the mechanism by which data from the host system and data from the content can pass from one to the other.

SCORM was last updated in 2004, leading to the version known as SCORM 2004. For most purposes, the more commonly seen SCORM 1.2 is sufficient. Yet, whilst SCORM has become ubiquitous, it has many critics - not least regarding the way content inside a SCORM package becomes a "black box", not readable by anything outside it ([Is your elearning broken? (Mark Berthelemy)](https://www.linkedin.com/pulse/your-elearning-broken-mark-berthelemy/){:target="_blank"})

[What is SCORM and how it works (scorm.com from Rustici)](https://scorm.com/){:target="_blank"}

[SCORM project (ADL)](https://adlnet.gov/past-projects/scorm/){:target="_blank"}

### xAPI (eXperience API)

xAPI provides a standard way to capture people's experiences for later analysis. At it's most simple an experience is a statement something like: [Person] [Verb] [Activity]. For example: Mark watched a video called "About xAPI".

These statements are captured in software known as a Learning Record Store (LRS). The xAPI standard specifies exactly how an LRS should work.

Unlike SCORM, xAPI statements can be sent from any system, not just a package of learning content. In theory, you could have a scenario where a sales system sends statements about a salesperson's closed deals. At the same time the learning management system could send statements about the sales training taken by the sales team. Then you could analyse the data to provide evidence (or not) that the sales training is making a difference.

In reality, xAPI has, to date, only gained traction in organisations with mature and joined-up approaches to performance and learning. It requires a change in thinking that focusses on data and analytics first.

[xAPI solved and explained (xapi.com from Rustici)](https://xapi.com/){:target="_blank"}

[xAPI profiles (statement templates and patterns)](https://profiles.adlnet.gov/){:target="_blank"}

### cmi5 (Computer Managed Instruction)

cmi5 is a set of rules for using xAPI to launch and track online courses from a learning management system. 

It's the modern equivalent of SCORM, and has been developed by the AICC team to supercede AICC.

Many authoring tools support exporting a cmi5 content package. To use it you will need an xAPI Learning Record Store (LRS) to receive the tracking data, and a cmi5-compatible system to launch the package. 

[cmi5 specification (AICC)](https://aicc.github.io/CMI-5_Spec_Current/){:target="_blank"}

[cmi5 explained (xapi.com by Rustici)](https://xapi.com/cmi5/){:target="_blank"}

### LTI (Learning Tools Interoperability)

LTI is mostly found in the education sector, but I'll mention it here as it is sadly missing from many corporate systems.

It allows a user, who is logged into their learning management system (the "consumer" system), to access content or tools that sit in another system (the "provider"). The experience is mostly seamless, with automatic single sign-on and data flowing from the provider to the consumer.

[LTI fundamentals (1EdTech)](https://www.imsglobal.org/lti-fundamentals-faq){:target="_blank"}

### QTI (Question Test Interoperability)

QTI is another one of those standards that has been around for a while. Unlike SCORM, though, it's still being maintained and developed.

It's designed primarily to allow the free movement of questions and results data between authoring tools, question banks and assessment delivery systems - allowing you to use specialist systems for each part of the assessment creation workflow. It supports a range of different question types.

[QTI specification (IMS Global)](https://www.imsglobal.org/question/index.html){:target="_blank"}

### RSD (Rich Skills Descriptors)

RSD has been around since about 2022. It's not yet a standard, nor even an agreed specification (as at April 2024). But it's worth keeping an eye on.

RSD provides a common way to describe skills and competencies. It means that talent management, learning management and credentialing systems can work together using the same definition of a skill.

It comes with an open source tool (the [Open Skills Management Tool (OSMT)](https://www.openskillsnetwork.org/osmt){:target="_blank"})to help create and manage the skills descriptors. 

[Rich Skill Descriptors (Open Skills Network)](https://rsd.openskillsnetwork.org/){:target="_blank"}

[Decentralising the description of skills with OSMT (Doug Belshaw)](https://dougbelshaw.com/blog/2022/02/03/skills-osmt/){:target="_blank"}

### Open Badges

Open Badges link closely to Rich Skill Descriptors. They provide the means for skills to be recognised and verified.

Interestingly the machine-readable data about the skill is held within the image of the badge itself, along with data about who the badge was awarded to and how to verify it with the awarding system.

The idea has been around for a while. It's only recently that it's becoming mainstream, with companies like [Pearson (using Credly)](https://info.credly.com/){:target="_blank"} adopting it fully for their assessment centres.

[Open Badges (1EdTech)](https://openbadges.org/){:target="_blank"}

[5 platforms for issuing Open Badges (We Are Open cooperative)](https://blog.weareopen.coop/5-platforms-for-issuing-open-badges-44364e44821){:target="_blank"}

## Web standards

If you've been around elearning for any length of time you will have come across HTML and CSS. These technologies are defined by several organisations all working together to ensure that web browsers interpret the code in the same way.

### HTML (Hyper Text Markup Language)

HTML is used to create the **structure** of a web page. With it you define elements such as headers, footers, sections, paragraphs, lists, links and headings.

[HTML tutorial (W3Schools)](https://www.w3schools.com/html/){:target="_blank"}

[HTML reference (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/HTML){:target="_blank"}

### CSS (Cascading Style Sheets)

CSS is used to define how the elements in a web page **appear** to the end user.

You can use it to set up, for example, the font, size and colour of text in every paragraph.

Using CSS allows you to create a single "style sheet" that applies to every web page in one or more projects, without needing to define the appearance in each page.

[CSS tutorial (W3Schools)](https://www.w3schools.com/css/){:target="_blank"}

[CSS reference (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/CSS){:target="_blank"}

### Open Graph

The Open Graph Protocol is what allows you to post a link on LinkedIn etc and that link turns into a picture with a title and description.

It's simply a defined way of creating metadata (data about data) that sits inside your web pages. If you're at all interested in getting public visibility for your content, then you need to be aware of Open Graph.

[Open Graph Protocol](https://ogp.me/){:target="_blank"}

[Preview and generate open graph metadata](https://www.opengraph.xyz/){:target="_blank"}

## Translation standards

### XLIFF (XML Localization Interchange File Format)

Translation is different world all on its own. XLIFF is the means by which many systems connect into that world.

It's a file format, like .odt or .docx. Within the file there are places for your source content (broken down into chunks, called segments) and for the translated versions of those segments.

XLIFF files are used to pass content from your source system to a translation management system (used by translation teams to manage the translation process). 

Any good content creation tool should allow you to export and import XLIFF files.

[XML in Localisation: Use XLIFF to Translate Documents (Maxprograms)](https://www.maxprograms.com/articles/xliff.html){:target="_blank"}

[Standards in the Evolution of Translation Technologies (Qabiria)](https://qabiria.com/en/resources/blog/standards-evolution-translation-technologies){:target="_blank"}

## Authentication and authorization standards

These include: LDAP, Oauth and SAML

This set of standards allows systems to work together to offer simpler sign-in and registration processes to end users.

They rely on an Identity Provider to authenticate that the person is known. Some also include data that allows the system to check what the person is allowed to do (authorization).

### LDAP (Lightweight Directory Access Protocol)

LDAP is a way to store information about people in a central place - to be used by multiple systems. It can be used for both authentication and authorisation.

It was first developed in 1993, and is most commonly seen when working with Microsoft-based systems. It's the basis of Microsoft's Active Directory.

[LDAP basic concepts (LDAP.com)](https://ldap.com/basic-ldap-concepts/){:target="_blank"}

### Oauth

Oauth is only used for authentication, not authorisation. You'll see it in use very often when you might choose to login with your Google or Facebook account on a website.

[Oauth website](https://oauth.net/2/){:target="_blank"}

### SAML (Security Assertion Markup Language)

SAML is often seen when working with large enterprises, to allow 3rd party systems to authenticate users. For example when signing into Zoom via SSO (Single Sign On).

The requesting system asks the SAML server to check whether a person is logged into the organisation's systems.

[Demystifying SAML (Oracle)](https://www.oracle.com/technical-resources/articles/enterprise-architecture/saml.html){:target="_blank"}
