---
title: Device
parent: Things to prepare in advance
layout: default
nav_order: 36
nav_enabled: true
---

# OverView
---

Devices (or apps) are used to track assets operating on a floor. There are two main methods:
1. Tracker devices attached directly to assets
2. Mobile apps that collect and transmit location data
These devices/apps scan the surrounding environment to determine position.
- If pre-trained data is available: The device predicts the location locally and sends the calculated coordinates via API.
- If pre-trained data is not available: The device sends scan data to the API, which then calculates and returns the coordinates.


# Coordinate transmission
---

Transmits location coordinates predicted by the trained model directly to the API.


# Predict Positioning
---

When the device cannot predict its own location, it can request a positioning prediction from the API by sending surrounding scan data.

{: .note}
>
> bssid: Unique identifier of the tracker (typically a MAC address).
> rssi: A key-value map where each entry contains a nearby Wi-Fi network’s MAC address (key) and its signal strength (value).
> 
> ```js
> {
>   bssid:"string",
>   rssi: "Map<string, int>"
> }
> ```
>
