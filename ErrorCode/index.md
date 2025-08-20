---
title: Error Codes
layout: default
nav_order: 5
---

# Error Codes
---

{: .important }
> {: .opaque }
> <div markdown="block">
> {: .highlight }
> - The response body is formatted as JSON.
> - Always check the status code first to determine whether the request succeeded, then parse the response body accordingly.
> - Success (2xx): The request was processed successfully, and the response body will contain the expected data.
> - Error (4xx, 5xx): The request failed, and the response body will contain an error code and message.
> </div>


| HTTP STATUS CODE(ERROR TYPE) | Reasons Errors |
|:-------------|:------------------|
| 400           | Missing required parameters, or incorrect parameter names |
| 401 | Authentication failed |
| 404           | API request URL is incorrect |
| 429           | Daily request limit exceeded |
| 500           | Request reached the server, but failed due to maintenance or system error |