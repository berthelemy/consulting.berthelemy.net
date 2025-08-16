---
title: Oauth 2
aka:  Open Authorization
standard_id: Oauth 2.0
type: single-sign-on
last_updated: 2012
status: Active standard
purpose: "OAuth 2.0 is a security framework that lets you give a third-party app access to your information on another website without sharing your password.  "
strengths:
   - The user is in control of their data
   - The external tool never sees your password
   - The user experience is smooth, similar to when you "Sign-in with Facebook"
limitations:
   - Oauth 2.0 requires an additional layer called Open ID Connect to handle user authentication
   - Its flexibility means there are many ways to implement Oauth 2.0, sometimes leading to inconsistencies or less secure practices
   - It relies on a chain of trust. If part of that chain is compromised, the whole system could be at risk
license: Copyright (c) 2012 IETF Trust and the persons identified as the
   document authors.
owner: Internet Engineering Task Force (IETF)
standard_url: https://oauth.net/2/
---
OAuth 2.0 is a security framework that allows an application to access a user's information from another service (like Google, Facebook, or Spotify) without ever getting their password.

Imagine you want to use a new learning tool that needs to access your name from your corporate user management system. You don't want to give the app your corporate password because then it could access your email, documents, and everything else.

Instead, OAuth 2.0 lets you give the learning tool a special, limited-access token. Here's how it works:

1.  **Requesting Permission**: The learning tool says, "Hey, can I get access to your name?"
2.  **Redirect to the Service**: Your user management system sends you (the user) to a corporate login page. You log in directly with your corporate system, so the external tool never sees your password.
3.  **Granting Permission**: The corporate systems asks you, "This app wants to access your name. Is that okay?" You click "Yes" or "Allow."
4.  **Issuing a Token**: After you approve, your corporate system gives the learning tool a special **access token**. This token only works for your name, and only for a limited time.
5.  **Accessing Data**: The external tool uses this token to access your name from the corporate system. If the tool tries to access your email, the token won't work.

The whole process is about delegating authority. You are the owner of the data, and you're giving a third-party tool permission to use some of that data on your behalf, without ever compromising your primary password. 