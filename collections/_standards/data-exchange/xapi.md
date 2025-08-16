---
title: xAPI
aka: eXperience API
standard_id: IEEE 9274.1.1-2023
type: data exchange
status: Active standard
last_updated: 2023
purpose: "xAPI captures the data describing diverse learning experiences, enabling detailed tracking beyond traditional courses."
strengths:
    - "Tracks everything, everywhere - whether online, offline, in a game, a simulation, or even real-world activities"
    - "Granular data collection - as rich as you need it"
    - "Highly flexible, with each implementation able to define its own verbs and objects"
    - "Able to collect data from multiple data sources"
    - "Some standardisation of data structures is taking place, through contextualised 'profiles', such as cmi5"
limitations:
    - "Implementation can be highly complex, requiring considerable pre-work on defining the data structures required"
    - "Organisations can end up with vast amounts of data that's hard to interpret"
    - "The xAPI ecosystem is developing, but has a while to go before xAPI becomes mainstream"
license: Copyright © 2022 XAPI Authors © 2022 IEEE
owner: IEEE
standard_url: https://standards.ieee.org/ieee/9274.1.1/7321/
---

Note that there is an open-source version of the IEEE xAPI standard, which does not require payment to access.

The Experience API (xAPI), sometimes called Tin Can API, is a modern elearning specification designed to track a wide range of learning experiences, beyond traditional courses.

Unlike SCORM, which focuses on LMS-centric course completion, xAPI can record virtually any learning activity, whether it happens online, offline, in simulations, or even in real-world scenarios.

It can also record job performance, eg. John closed a case, or Jenny sold a product - allowing data analysts to begin correlating learning with performance.

At its core, xAPI captures learning as "statements" in the format of "Actor Verb Object" (e.g., "John completed the safety checklist" or "Mary practiced CPR on the dummy"). These statements are sent to a Learning Record Store (LRS), which acts as a central repository for all learning data.

![Illustration showing the path of xAPI statements from applications through to the LMS]({{ site.baseurl }}/assets/img/standards/xapi.png)

xAPI's flexibility allows for richer analytics, personalized learning paths, and a comprehensive view of an individual's development across various platforms and activities.

Here's a simple xAPI statement, describing that **John practiced CPR on a dummy on 15th August 2025**.

```
{
  "actor": {
    "mbox": "mailto:john@example.com",
    "name": "John Smith"
  },
  "verb": {
    "id": "http://adlnet.gov/expapi/verbs/practiced",
    "display": {
      "en-US": "practiced"
    }
  },
  "object": {
    "id": "http://example.com/activities/cpr-dummy-practice",
    "definition": {
      "name": {
        "en-US": "CPR Practice on Dummy"
      },
      "description": {
        "en-US": "Practiced Cardiopulmonary Resuscitation (CPR) techniques on a training dummy."
      },
      "type": "http://adlnet.gov/expapi/activities/simulation"
    }
  },
  "timestamp": "2025-08-15T10:00:00Z"
}
```