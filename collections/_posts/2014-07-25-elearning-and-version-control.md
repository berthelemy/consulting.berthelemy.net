---
title: Elearning and version control
author: Wyver Solutions Admin
excerpt: Using a version control system, like Git, can help ensure you release the right version of materials to your client, and minimise confusion. I provide a brief introduction to Git, and pointers for where to go for good advice.
layout: post
permalink: /2014/07/25/elearning-and-version-control/
tags:
  - Content management
  - Solution design
---
Most of us start out creating documents and other materials without any system of version control in place.

But, very soon, we realise that we need to keep regular backups (usually just after something has gone horribly wrong). So we start saving things with filenames like xyzclient-elearning\2014-7-10\v13.docx. Being human though, we tend to forget things like the precise format to use, or whether we have overwritten a particular file with the current version. It can get very messy very quickly.

Things become even more complicated when we're working with a team, or trying out new ideas whilst still maintaining the main set of materials. It&#8217;s so easy to make mistakes and end up publishing the wrong version to the client.

This is where a version control system, like <a href="http://git-scm.com/" target="_blank">Git™</a> can help, by:

  1. Managing the naming conventions automatically
  2. Identifying changes between files (if they&#8217;re in a suitable format, see below)
  3. Merging input from different team members
  4. Managing different development &#8220;branches&#8221;

I prefer Git to other systems (such as <a title="Apache Subversion" href="http://subversion.apache.org/" target="_blank">SVN</a>), mainly because of its speed, the fact that I can work locally, but also with a team, and because managing changes in different development branches is very easy.

Git works by taking a snapshot of all your files in a project every time you tell Git to do so. It stores a copy of any file that has changed, and a reference to the previous identical file for files that haven&#8217;t changed.

If your files are in a plain text format, like HTML, CSS &amp;Javascript, then Git can show you, very easily, the changes that have occurred between two versions.

If you&#8217;re working with documents in proprietary formats (as used by most of the Rapid Elearning tools), then Git just treats them as &#8220;blobs&#8221;, and saves a new copy of the whole file each time. This might be exactly what you want, as you don&#8217;t need to worry about fancy naming conventions.

In fact, I use Git quite often just to support version control of Word documents and project plans.

But, for best results with Git (and any version control system), I would recommend working as much as possible with plain text files eg. Markdown (for text), HTML, CSS &amp;Javascript. How you do that, whilst still creating quality materials at speed is a topic for another post!

## Resources

<a href="http://git-scm.com/downloads/guis" target="_blank">Graphical interfaces for Git</a> (I prefer <a href="http://www.sourcetreeapp.com/" target="_blank">SourceTree</a> from Atlassian)

### Git tutorials:

It&#8217;s a good idea to understand the concepts behind Git, and a smattering of commands before using one of the graphical interfaces, otherwise you&#8217;ll get lost quite quickly.

  * <a href="http://git-scm.com/book/en/Getting-Started-Git-Basics" target="_blank">Getting started &#8211; Git basics</a> &#8211; a great introduction from the people behind Git
  * <a style="font-style: normal;" href="http://tom.preston-werner.com/2009/05/19/the-git-parable.html" target="_blank">The Git Parable</a> &#8211; an easy to digest description of how Git works
  * <a style="font-style: normal;" href="https://try.github.io/levels/1/challenges/1" target="_blank">15 minutes to learn Git</a>
  * <a style="font-style: normal;" href="http://www.git-tower.com/learn/ebook/command-line/introduction" target="_blank">Learn version control with Git</a> &#8211; a good introduction, and then some focussing on the command line
  * <a style="font-style: normal;" href="http://rogerdudler.github.io/git-guide/" target="_blank">Git &#8211; the simple guide</a> &#8211; focusses on the command line from the outset

<p class="p1">
  Inspired by: <a href="http://sixrevisions.com/web-development/git-myths/" target="_blank">6 Myths Preventing Developers from Using Git</a>
</p>

 [1]: http://git-scm.com/
