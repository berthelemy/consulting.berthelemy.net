---
title: 'Do we still need elearning authoring tools?'
author: Mark Berthelemy
excerpt: With the rise of the AI content creation tools, do we still need elearning authoring software?
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
img: 2026/04/scorm-screenshot.png
imgalt: SCORM package to teach people the imperfect tense in French
imgcredit: Mark Berthelemy
imgurl: https://berthelemy.github.io/html-elearning-sample/
tags:
  - Solution design
  - Content management
---
Can your AI agent replace authoring tools like Articulate Storyline, Adobe Captivate, or iSpring? 

Recently I set myself a challenge to see how far I could go in creating a SCORM package using only AI tools. I wanted to see if I could create a simple elearning module without using any traditional authoring software.

It took about 30 minutes to set up the project, set the boundaries, define the skills the agent would need and to think about what I wanted to teach through the module.

I then set the agent running. About 20 minutes later, I had a fully functional SCORM package that I could test on SCORM Cloud or any LMS. The package included a simple quiz, some interactive elements, and a friendly, accessible and responsive design. The agent itself did not have any prior knowledge of SCORM or elearning development, but it was able to learn and apply the necessary skills to create the package. I'd even asked it to create a custom design for the module, and it was able to do so without any issues.

## The result

You can see the result on this demo site: [https://berthelemy.github.io/html-elearning-sample/](https://berthelemy.github.io/html-elearning-sample/){:target="_blank" rel="noopener"}.

If you want to go behind the scenes, you can check out the [Github repository](https://github.com/berthelemy/html-elearning-sample){:target="_blank" rel="noopener"} where I have documented the process and shared the code. The final SCORM package is in the dist/ folder. You can try it in your own LMS or on SCORM Cloud.

The learning design is simple: I wanted to create a module to teach people the imperfect tense in French. The agent was able to understand the topic and create content that was relevant and engaging for learners. That would probably be the only thing I would suggest needed more input from me. I'd left the instructions quite open - just referring it to the topic and the CEFR standards for level A2.

One of the great benefits of this approach is that the code produced by the AI agent is clean and well-structured. It follows best practices for web development and is easy to understand and modify if needed. This is a significant advantage over some traditional authoring tools, which can produce bloated and hard-to-maintain code.

The AI agent was able to create a SCORM package that met my requirements, and it did so with minimal human intervention. So this raises the question: do we still need traditional elearning authoring tools?

## Limitations

The answer is not straightforward. Yes, we can use the AI tools to build very quickly. With the right instructions and parameters, we can create a functional SCORM package in a fraction of the time it would take with traditional authoring software. However, there are still some limitations to consider.

Firstly, the AI tools are not yet perfect. They can make mistakes, and they may not always produce the exact results you want. You may need to spend some time tweaking the instructions or fixing any issues that arise.

They are like an eager and very skilled intern; needing a lot of guidance and supervision to get the job done right.

If you're just in the business of producing a lot of content quickly, these tools on their own might be enough.

The problems come when you want to make edits yourself or involve multiple stakeholders in the review process.

## Editing

For me to make changes to the content, I have two options: I can either go back to the AI agent and ask it to make the changes, or I can edit the code directly. The first option may not always yield the desired results immediately, and the second option requires some technical knowledge - even though the code is clean and well-structured.

With a traditional authoring tool, I could easily make the changes myself (assuming I have a license for the tool, have the original source files and know how to use the software).

## Collaboration

If I want to involve subject matter experts, instructional designers, or other team members in the review process, it can be challenging to get their feedback on the content.

When you're working with a team of developers, this might not be a problem, since you can use their common tools and processes (eg. version control tools, pull requests and code reviews). But if you're working with a more diverse team, it can be difficult to get everyone on the same page.

Many of the authoring tools have built-in collaboration features that allow multiple stakeholders to review and provide feedback on the content. They hide the technical complexity and provide a user-friendly interface for working together.

## Conclusion

The AI agents are remarkably capable of creating functional SCORM packages quickly and efficiently. However, they are not yet a complete replacement for traditional elearning authoring tools, especially when it comes to editing and collaboration.

In the future this may change. If we find a way to separate the content from the code, that would make it easier to make edits to the content.

And,through an interface like Bugherd's website review tool, we could provide a way for non-technical stakeholders to submit feedback directly on the content, which (following triage) then feeds issues into the codebase which the AI agent can then address. That would make it easier to involve multiple stakeholders in the review process.


