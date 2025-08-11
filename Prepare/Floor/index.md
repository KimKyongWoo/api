---
title: Floor
parent: Things to prepare in advance
layout: default
nav_order: 35
nav_enabled: true
---

# Over View
---

This system provides a basic function to track the real-time location of assets on each floor of buildings managed by the organization.
In simple terms, it’s a core API that lets you instantly know which floor an item is on and where exactly it is inside the building.

## Floor Info
---

{: .note}
>
> This function displays detailed information about a specific floor, including the floor number, floor name, and drawing information.
>
> ```js
> {
>	floor_id:"string"
>	floor_name:"string"
>	floor_img:"string",
>	floor_x_by_meter:"float",
>	floor_y_by_meter:"float",
>	floor_number:"int",
>	floor_is_basement:"boolean"
> }
> ```

## Search for asset locations on Floor

{: .note}
> A function that queries the location of assets on a specific floor on the drawing in terms of X and Y plane pixels, providing the X and Y location of the asset as well as the time (Unix timestamp) when it existed at that location.
>
> ```js
> [
>   {
>       asset_id: "string",
>       asset_name: "string",
>       asset_x: "double",
>       asset_y: "double",
>       timestamp: "long",
>   }   
> ]
> ```