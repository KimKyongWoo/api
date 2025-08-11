---
title: Building
parent: Things to prepare in advance
layout: default
nav_order: 34
nav_enabled: true
---

# Over View
---

These functions allow you to view information related to buildings managed by the organisation of the API. You can view a list of buildings managed within the organisation, as well as information about the floors belonging to each building.

## Building List
---

A function that allows users to view basic information about all buildings managed by the organisation in list form.
The results of the search are as follows.

{: .note}
> 
>
> ```js
> [
>   {
>       building_id: "string",
>       building_name: "string",
>       building_img: "string"
>   }
> ]
> ```
>

## Floor inquiry within the building
---

A function to view basic information about registered floors in each building.
The results of the search are as follows.

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