---
title: 'Skills framework starter kit'
author: Mark Berthelemy
excerpt: An open-source kit to help you design and publish your own human and AI-readable skills framework
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2026/06/27-skills-framework-starter-kit
img: 2026/06/skills-framework.png
imgalt: Screenshot of the starter kit
imgcredit: Mark Berthelemy
imgurl:
tags:
  - Solution design
  - Content management
  - Skills
---
Whilst at [CABI](https://cabi.org){:target="_blank"}, one of my major projects was their [Skills for Agriculture framework](https://agricultureskills.org/){:target="_blank"}. This was an important foundational step to help the organisation and its partners assess priorities for training and development.

We built a website to hold the framework, along with links to associated courses. It was pretty complicated - especially the process to manage the connections between skills and courses.

Since then, of course, AI has come in, with two effects:

1. Every website now needs to have some way for the AI scrapers to read it effectively
2. We can now tell the AI to make changes to a website, and manage its data - making it much easier to make the connections

So, I've done a completely fresh build of a [generic skills framework website with associated courses](https://skills-framework.berthelemy.net/){:target="_blank"}. This reference site is designed to be a starter pack for an individual with a modicum of technical capability, but also for organisations with more experienced development teams.

Key features:

- Based on the widely used [SFIA Foundation framework](https://sfia-online.org/){:target="_blank"} approach: Category > Skill > Level descriptor 
- Human and AI readable website
- Easy to modify the data
- Branding configuration file controls colours, logo and key text elements
- Built in automatic glossary linking to key words or phrases
- Site wide search
- Automatic build and hosting on GitHub Pages 
- Layout and design based on Bootstrap
- Built using Jekyll
- Fully documented for a non-technical user
- Sample prompts for your AI agent
- Make your own copy and start editing

I've released this with an MIT license.  Basically that means you can do anything you want with it, as long as you provide some sort of attribution and don't expect any sort of warranty... 🙂 

All the data is stored in user-editable markdown files, with full documentation on how to make the changes and how to brand it to your own organisation. There are even some sample prompts to help you use it to build your own framework.

I've also provided full step-by-step technical documentation so you can get your own copy, run it on your computer and deploy it to a live website. It does look a little daunting at first, but you only have to do the bulk of the setup once.

[Visit the skills framework starter kit](https://skills-framework.berthelemy.net/)