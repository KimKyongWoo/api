---
title: Access Token Issuance
parent: Getting Started
layout: default
nav_order: 33
nav_enabled: true
---

# Issuing Access Tokens with API Keys
---

An API key is required to use the Ipinlabs API, but the API key is only needed for authentication. A separate access token is required to call other functions.
Therefore, you must go through the process of issuing an access token to call other Ipinlabs APIs with your registered API key.

{: .note}
> Once you obtain an access token with your API key, you will see the following results.
>
> ```js
> {
>    result: 
>    {
>        key_expired: "long",
>        access_token: "string",
>    }
> }
> ```
>
> Now you can access other APIs using the access token you have been issued.  
> The Access Token expires after the Unix timestamp key_expired, so you must renew the token through the Refresh Token API before that time.

{: .warning }
> As a rule, one Access Token is issued for each API key, and if a duplicate issuance request is received, the previous token is invalidated and a new token is issued.