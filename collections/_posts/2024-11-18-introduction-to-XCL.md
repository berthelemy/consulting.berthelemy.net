---
title: 'Is XCL an alternative to the LMS?'
author: Mark Berthelemy
excerpt: A dive into this new technology
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/11/18/introduction-to-XCL
img: 2024/11/xcl-blog.png
imgalt: Laptop showing the XCL home page
imgcredit: Stocksnap on Pixabay
imgurl: https://pixabay.com/photos/laptop-apple-keyboard-technology-2592316/
tags:
  - Solution design
---
I've been experimenting with the new beta version of <a href="https://www.buildcapable.com/xcl/" target="_blank">XCL</a> from <a href="https://www.buildcapable.com/" target="_blank">Build Capable</a>. It's a new tool to help organisations deliver online learning without an LMS.

It looks like it has a lot of potential...

As I say in the video clip below, I'm really quite excited about what XCL can do. It opens up new possibilities.

Here's what is does, and what it doesn't (yet) do:

## Plus points

- It allows you to turn any digital resource into a trackable learning object (with caveats - see below)
- If your resource is a SCORM or xAPI package, you can extract all the data that they provide (eg. completion status, scores etc)
- If you upload files into XCL, like PDF, ppt, mp4 etc, you get much richer data than if you just link out to them
- It works through this process: You provide a link to the user -> User clicks the link -> User enters their name & email -> Resource opens -> Data is sent back to XCL
- You can capture the data in XCL's internal learning record store, or your own LRS.

## Things to work on

- Resources provided via a URL just capture whether someone has launched them
- In the beta version there is no way to inform people about your privacy policy, at the point of collecting their name and email address.
- It currently struggles to display and play Youtube videos
- You can only keep content secure if you either use the Enterprise Version with Single Sign On (coming soon) or put the content somewhere you control (thus losing a lot of the built in tracking)
- I'm not sure I completely trust the Dashboard data. It recorded two completions of a SCORM package, when I'd only done it once. 
- There's no way currently to perform additional analytics on the data stored in the internal learning record store 
- There's not yet a way to capture a tick/check for the user to say that they have read and understood something (essential for compliance)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Xn65_MhyqOE?si=EUd6MBDv-vpLwWOC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>