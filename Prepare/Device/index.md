---
title: Device
parent: Things to prepare in advance
layout: default
nav_order: 36
nav_enabled: true
---

# Over View
---

{: .note}
> 
> To track assets (such as equipment or devices) operating on a floor, there are two main methods:
> Using a tracker device attached to the asset.
> Using an app to track and send location data.
> These devices or apps scan the surrounding environment to determine their position.
> - If pre-trained data is available → They immediately scan the surroundings, predict the location, and send the coordinates via an API.
> - If no pre-trained data is available → They send the scan data to the API, the API calculates the location, and then generates the coordinates.
>


## Coordinate transmission
---

Information about the coordinates predicted by the learned model is transmitted via API.


## Predict Positioning
---

When it is not possible to predict the location of current assets using the built-in model, this feature requests a prediction by retrieving the surrounding situation via API.

{: .note}
> 
> ```js
> {
>   bssid:"string",
>   rssi: "Map<string, int>"
>   sensorValue:"int",
>   voltage:"float",
>   percentage:"float"
> }
> ```
>
> bssid is the unique ID of the current tracker, mainly using the MAC address value, and rssid is a dictionary-type object with the MAC addresses and signal strength values of nearby Wi-Fi networks as key-value pairs.
