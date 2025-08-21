---
title: Floor
parent: Getting Started
layout: default
nav_order: 35
nav_enabled: true
---

# Overview
---

These functions provide real-time location data for assets on each floor of your organization’s buildings.
In simple terms, it is a core API that lets you identify:
- Which floor an asset is on
- The asset’s exact position on that floor


# Get Floor Information
---

Returns detailed information about a specific floor, including the floor number, floor name, and drawing information.

{: .note}
>
> ```js
> {
>	floor_id:"string",
>	floor_name:"string",
>	floor_img:"string",
>	floor_x_by_meter:"float",
>	floor_y_by_meter:"float",
>	floor_number:"int",
>	floor_is_basement:"boolean"
> }
> ```

# Get Asset Locations on a Floor
---

Queries the real-time location of assets within a specific floor.
Positions are expressed in (X, Y) pixel coordinates on the floor map, along with the timestamp of the last update.

{: .note}
>
> ```js
> [
>   {
>       asset_id: "string",
>       asset_name: "string",
>       asset_x: "double",
>       asset_y: "double",
>       timestamp: "long"
>   }   
> ]
> ```