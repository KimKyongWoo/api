---
title: Building
parent: Getting Started
layout: default
nav_order: 34
nav_enabled: true
---

# OverView
---

These functions provide access to information about buildings managed by your organization.
- Retrieve a list of all buildings registered under the organizatio
- Retrieve floor information for each building.

# Get Building List
---

Returns basic information for all buildings managed by the organization.
Response example:

{: .note}
> 
>
> ```js
> [
>   {
>       building_id: "string",
>       building_name: "string"
>   }
> ]
> ```
>

# Get Floors in a Building
---

Returns basic information for all registered floors within a specific building.

{: .note}
> 
>
> ```js
> [
>   {
>       floor_id: "string",
>       floor_name: "string"
>   }
> ]
> ```
>