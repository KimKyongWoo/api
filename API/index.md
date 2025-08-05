---
title: API
layout: default
nav_order: 4
---

* [Key Registration](#key-registration)
* [Key Details](#key-details)
* [AccessToken Issuance](#accesstoken-issuance)
* [Refresh Token](#refresh-token)

# Key Registration
---

Registration API Key.  

{: .post}
> <dl>
>   <dt>POST</dt>
>   <dd>/v1/key/regist</dd>
>   <dt>Request Body Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
> | field | type | desc |
> |:----|:-------|:--------------------------|
> | key | string | API Key value to register |

## Response
---

{: .new}
> <dl>
>   <dt>Code</dt>
>   <dd>200</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        key_expired: long,        
        max_total_usage: int        
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>400</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Bad request"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>404</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Not found"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>500</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Internal server error"
    }
}
```

# Key Details
---

API Key Details Status.  

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/key/detail</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>API Key</dd>
> </dl>


## Response
---

{: .new}
> <dl>
>   <dt>Code</dt>
>   <dd>200</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        key_expired: long,
        remaining_total_usage: int,
        max_total_usage: int,
        scope: array<string>
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>400</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Bad request"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>404</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Not found"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>500</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Internal server error"
    }
}
```


# AccessToken Issuance
---

Issuing Access Tokens Using API Keys.  

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/auth/token</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>API Key</dd>
> </dl>


## Response
---

{: .new}
> <dl>
>   <dt>Code</dt>
>   <dd>200</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        key_expired: long,
        access_token: string,
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>400</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Bad request"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>404</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Not found"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>429</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "This token is not authenticated."
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>500</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Internal server error"
    }
}
```

# Refresh Token
---

Renewing AccessToken

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/auth/refresh</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>Access Token</dd>
> </dl>


## Response
---

{: .new}
> <dl>
>   <dt>Code</dt>
>   <dd>200</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        key_expired: long,
        access_token: string,
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>400</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Bad request"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>404</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Not found"
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>429</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "This token is not authenticated."
    }
}
```

{: .warning}
> <dl>
>   <dt>Code</dt>
>   <dd>500</dd>
>   <dt>Response Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
```js
{
    result: 
    {
        error: "Internal server error"
    }
}
```