---
title: API
layout: default
nav_order: 4
---

# Key registration
---

Registration API Key.  

{: .code}
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