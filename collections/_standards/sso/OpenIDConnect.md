---
title: OpenID Connect
aka:  OIDC
standard_id: OpenID Connect
type: single-sign-on
last_updated: 2023
status: Active standard
purpose: "OpenID Connect provides a way to verify a user's identity"
strengths:
   - OIDC enables users to sign-in to multiple services without needing to create and remember a new username and password
   - It provides a robust and standardised way to verify a user's identity
   - The ID token can include basic user information without needing additional API calls to collect them
limitations:
   - It must be used alongside Oauth 2.0 to ensure users are **authorized** as well as **authenticated**
   - It can be complex to implement. A single error could compromise the entire system
   - It relies on a chain of trust. If part of that chain is compromised, the whole system could be at risk
license: Copyright (c) 2012 IETF Trust and the persons identified as the
   document authors.
owner: OpenID Foundation
standard_url: https://openid.net/developers/how-connect-works/
---
Whilst OAuth 2.0 is about granting permission to access resources, OpenID Connect (OIDC) is about verifying a user's identity.

OpenID Connect is an identity layer built on top of the OAuth 2.0 framework. It uses OAuth 2.0's features to solve the problem of user authentication. It answers the question: **"Who is this user?"**

* **Core Purpose:** **Authentication**. It's about confirming a user's identity. It allows you to use a single login (like your Google or Microsoft account) to sign in to multiple websites.

* **How it works:** It uses an **ID Token**. This is a special type of JSON Web Token (JWT) that contains information about the user, such as their name, email, and a unique identifier. Once the user is authenticated, the ID Token is sent to the application, which can then confirm the user's identity.

In practice, a modern "Sign in with Microsoft" button uses **both**. OAuth 2.0 handles the permissions (e.g., to access your name and email), while OIDC handles the authentication (confirming that you are indeed the user you claim to be).