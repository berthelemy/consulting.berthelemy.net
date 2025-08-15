---
title: JSON
aka: JavaScript Object Notation
standard_id: ISO 21778
type: data format
last_updated: 2017
purpose: "JSON provide a way to transfer complex, multi-layerd data between systems."
strengths:
    - Compact and lightweight
    - Human readable data
    - Natively understood by web-browsers
    - Fast to process
    - Widely used for real-time data integrations
limitations:
    - No ways to define the data schema (unlike XML)
    - "Limited data types: strings, numbers, boolean, arrays and objects (dates have to be converted to strings)"
license: Copyright &copy; 2017 ECMA International
owner: ECMA International
standard_url: https://ecma-international.org/publications-and-standards/standards/ecma-404/
---
JSON stands for JavaScript Object Notation. It is a lightweight, human-readable data format used for storing and transporting data. It is the primary alternative to XML for transmitting information between a server and a web application.

JSON's syntax is derived from JavaScript object literal notation, making it familiar to developers.

It uses key-value pairs and ordered lists of values, which are easy for machines to parse and generate. The structure is simple and clean, consisting of curly braces `{}` for objects and square brackets `[]` for arrays. This makes JSON more concise than XML and less prone to errors.

Its simplicity and native compatibility with JavaScript have made it the dominant format for APIs and web services.

A simple JSON file may look like this:

```
{
    "type": "book",
    "title": "War of the Worlds",
    "author": "HG Wells",
    "price": 15,
}
```