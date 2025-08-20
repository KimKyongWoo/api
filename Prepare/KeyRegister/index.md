---
title: Key registration
parent: Things to prepare in advance
layout: default
nav_order: 31
nav_enabled: true
---

# Key Registration
---

The IPINLABS API issues authentication keys to each organization. These keys serve as unique identifiers to ensure that only authorized users can access the API.
- When calling the API, the authentication key must be included as a parameter.
- To use the IPINLABS API, you must first obtain and register an authentication key.

{: .warning }
> Registering a key alone does not grant access.
> You must request an Access Token using the authentication key, and then use the issued token to make API calls.

# Activation
---

When an authentication key is activated, the following information is returned:
- Expiration time of the key (Unix timestamp)
- Maximum number of API calls allowed

{: .warning }
> The maximum number of API calls may vary depending on your service environment.

# Access Token Issuance
---

To use the IPINLABS API, an API key is required for authentication. However, the API key itself cannot be used to call most API functions. Instead, you must first exchange your API key for an access token.

## Issuing an Access Token

When you request an access token with your registered API key, the response includes:
- access_token: The token you will use to call other APIs.
- key_expired: Expiration time of the token, provided as a Unix timestamp.

The access token is only valid until the key_expired timestamp.
You must renew it before expiration by calling the Refresh Token API.

{: .warning }
> Only one access token is active per API key.
> If a new access token is issued, any previously issued token for that key becomes invalid.