---
title: AccessToken Issuance
parent: Things to prepare in advance
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
>        key_expired: long,
>        access_token: string,
>    }
> }
> ```
>
> Now you can access other APIs using the access token you have been issued.