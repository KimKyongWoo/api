---
title: API
layout: default
nav_order: 4
---

---

* [Key Registration](#key-registration)
* [Key Details](#key-details)
* [AccessToken Issuance](#accesstoken-issuance)
* [Refresh Token](#refresh-token)
* [Building List](#building-list)
* [Floor List In Building](#floor-list-in-building)
* [Floor Info](#floor-info)
* [Create Coordinates In Floor](#create-coordinates-in-floor)
* [Get Floor Coordinates](#get-floor-coordinates)

---

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

# Building List
---

Print only the basic information of all buildings under management.

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/building/list</dd>
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
[
    {
        building_id:"string",
        building_name:"string"
    }
]
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

# Floor List In Building
---

A function that prints only the basic information of all floors belonging to a specific building.

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/building/floor/list</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>Access Token</dd>
>   <dt>Query</dt>
>   <dd>building_id</dd>
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
[
    {
        floor_id:"string",
        floor_name:"string"
    }
]
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


# Floor Info
---

Function to output detailed information on a specific layer

{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/floor/info</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>Access Token</dd>
>   <dt>Query</dt>
>   <dd>floor_id</dd>
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
    floor_id:"string",
    floor_name:"string"
    floor_img:"string",
    floor_x_by_meter:"float",
    floor_y_by_meter:"float",
    floor_number:"int",
    floor_is_basement:"boolean",
    floor_created:"string"
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

# Create Coordinates In Floor
---


{: .post}
> <dl>
>   <dt>POST</dt>
>   <dd>/v1/floor/coordinates</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>Access Token</dd>
>   <dt>Request Body Schema</dt>
>   <dd>application/json</dd>
> </dl>
> 
> | field | type | desc |
> |:----|:-------|:--------------------------|
> | floor_id | string | target floor's Unique ID |
> | x | float | Drawing image reference pixel x coordinate |
> | y | float | Drawing image reference pixel y coordinate |
> | time | long | Unix time when coordinates were transmitted |


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
        susess: "Coordinates Created"
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
        error: "Coordinates failed: {Error Message}"
    }
}
```

# Get Floor Coordinates
---


{: .get}
> <dl>
>   <dt>GET</dt>
>   <dd>/v1/floor/coordinates</dd>
>   <dt>AUTHORIZATIONS</dt>
>   <dd>Access Token</dd>
>   <dt>Query</dt>
>   <dd>floor_id</dd>
>   <dd>time</dd>
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
[
    {
        time: "long",
        x: "float",
        y: "float"
    }
]
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