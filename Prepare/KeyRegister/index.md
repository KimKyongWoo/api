---
title: Key registration
parent: Things to prepare in advance
layout: default
nav_order: 31
nav_enabled: true
---

# API Authentication Key

Ipinlabs API issues API authentication keys, which are identification tools, to each organisation so that only authorised users can call the API.
These keys are used as parameters for authentication when calling the API.
Therefore, to use Ipinlabs API, you must first obtain an authentication key and register it.

{: .warning }
> However, registration does not grant access to the key.
> You must request an Access Token with the authentication key and use the issued Token to access the Iplinlabs API.

# Key Regist

When you register and activate the key, the expiration time of the authentication key and the maximum usage of API calls are provided as result values, and the expiration time is provided as a Unix timestamp.

{: .warning }
> However, the maximum number of API calls may vary depending on the service environment.