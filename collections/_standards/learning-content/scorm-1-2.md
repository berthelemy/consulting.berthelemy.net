---
title: SCORM 1.2
aka: Shareable Content Object Reference Model 1.2
standard_id: SCORM 1.2
type: learning content
last_updated: 2001
purpose: SCORM 1.2 provides basic capabilities to allow content authored in one system to work within a separate delivery system.
strengths:
    - Widespread adoption
    - Reduces vendor lock-in
limitations:
    - Passes very limited data about user behaviours to the host system
    - Rigid, linear structure by default
    - Relies on the user being online
    - Updating published SCORM packages can be difficult
    - Aging technology which can lead to challenges with modern development practices and browser security
rationale: "Included for completeness even though it's not really a standard, and is a legacy specification. SCORM 1.2 is the most widely used of the available content packaging methods."
purpose: "Allows packages of content to be used in delivery systems, and their usage tracked by the host system."
license: Copyright &copy; 2001 Advanced Distributed Learning
owner: Advanced Digital Learning (ADL)
standard_url: https://www.adlnet.gov/past-projects/scorm/#scorm-versions-and-resources
---
SCORM 1.2 is a widely adopted set of technical standards that allows online learning content and Learning Management Systems (LMSs) to **"talk to each other."** 

It covers three main aspects:

1. How content is structured (packaging)
2. How content is described (metadata) <mark>although most corporate platforms and content authoring tools don't support this, other than a simple title and description</mark>
3. How content exchanges data with the LMS (runtime)

SCORM 1.2 was instrumental in standardizing early elearning interoperability.

Some companies have developed workarounds for some of the limitations:

- **Limited data**: By adding custom data, although this relies on both the authoring tool and the hosting LMS knowing how to parse that data.
- **Rigid, linear structure**: Authoring tools overcome the rigid, linear structure limitation by ignoring much of the content packaging specification. Instead, all their content is placed into a single SCO.
- **Online only**: Some LMSs have built mobile apps which cache the tracking data and send it when the device is next online.
- **Republishing process**: Some authoring tools and third parties keep the content on their platform, while the LMS hosts a 'stub' file. Updates to the content can then happen in the background.