---
title: XML
aka: eXtensible Markup Language
standard_id: XML
type: data transmission
last_updated: 2008
purpose: "XML files provide a way to transfer complex, related data between systems."
strengths:
    - Self-describing - completely flexible
    - Hierarchical structure
    - Can be used for real-time data transfers (although less often these days)
limitations:
    - For interoperability, a Document Type Definition is required. It sets the rules for how a particular XML file should be structured
    - Can be cumbersome for developers to work with
    - Quite bulky and verbose
license: Copyright &copy; 2008 W3C
owner: World Wide Web Consortium (W3C)
standard_url: https://www.w3.org/TR/xml/
---
XML (eXtensible Markup Language) is a markup language for storing and transporting data. Unlike HTML, which uses a fixed set of tags to display content, XML uses a flexible, user-defined structure to describe the data itself. This makes it a self-describing language.

The core purpose of XML is to make data readable by both humans and machines, promoting interoperability between different systems.

It relies on a tree-like structure of elements and attributes. For example, a document might have a `<book>` element containing `<title>`, `<author>`, and `<price>` elements:

```
<book>
    <title>War of the Worlds</title>
    <author>HG Wells</author>
    <price>£15</price
</book>
```
