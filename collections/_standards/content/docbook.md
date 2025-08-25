---
title: DocBook
aka: 
standard_id: DocBook 5.1
type: content
last_updated: 2016
status: OASIS Standard
route: formal
purpose: DocBook is an XML schema for writing technical documents, designed for easy conversion into different formats like PDF, HTML, or EPUB.
strengths:
    - A single DocBook source file can be converted to many different output formats (Eg. PDF, HTML and ePub), ensuring consistency and saving time.
    - As an open standard, DocBook isn't tied to any single software vendor. You can use a variety of tools to author, validate, and publish your content.
limitations:
    - Writing in raw XML can be cumbersome and difficult for non-technical writers. The large number of elements and their specific rules can be confusing.
    - The verbose nature of XML tags makes the source code hard to read and edit manually, especially compared to more lightweight markup languages like Markdown.
    - its effective use often requires a sophisticated toolchain, including an XML editor, XSLT processors, and other utilities. This can be complex to set up and maintain
rationale: "DocBook is widely used in the technical writing community, and its structured approach helps ensure high-quality documentation."
license: Copyright © OASIS Open 2016. All rights reserved.
owner: OASIS
standard_url: https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=docbook
---
DocBook is a **semantic XML schema** designed for creating technical documents. Instead of focusing on how a document will look, authors use a set of descriptive tags, like

```
<chapter>
    <para>Some text</para>
</chapter>
```
to describe the content's meaning and structure. This separation of content from presentation is DocBook's core principle.

The source files, written in XML, don't contain any formatting information. To produce a final document, an **XSLT stylesheet** is applied to transform the DocBook XML into various output formats. This allows a single source file to be easily converted into a variety of outputs, such as a PDF for printing, HTML for a website, a man page, or an EPUB for e-readers. This makes DocBook an ideal solution for projects that require consistent, multi-format publishing from a single source, ensuring content remains structured and reusable across different platforms.