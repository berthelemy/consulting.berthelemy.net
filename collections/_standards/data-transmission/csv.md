---
title: CSV
aka: Comma Separated Variables
standard_id: RFC4180
type: data transmission
last_updated: 2005
purpose: "CSV files provide a way to transfer simple tabular data between systems, for example between <strong>operations</strong> and <strong>analytics</strong>"
strengths:
    - Simple structure
    - Human readable data
limitations:
    - Cannot describe the relationships between different types of data, without the use of multiple CSV files.
    - Best for scheduled data transfers. Not appropriate for real-time use.
license: Copyright &copy; 2005 Internet Society
owner: Internet Engineering Task Force (IETF)
standard_url: https://datatracker.ietf.org/doc/html/rfc4180
---
CSV files have, for many years, been the workhorse for moving data between systems.

Each file would look something like this:

```
id,name,department
1,Micky Mouse,Sales
2,Donald Duck,Marketing
3,Yogi Bear,Engineering
```