---
title: Error Code
layout: default
nav_order: 5
---

{: .important }
> {: .opaque }
> <div markdown="block">
> {: .highlight }
> When you call an API, you receive the API processing results as an HTTP status code.
> The response value is received as an HTTP response body. The response value format can be JSON.
> Therefore, when processing API responses, first check whether the processing was successful using the HTTP status code, then parse the results according to the response format for use in your service.
> </div>

{: .note }
> * Normal call: The HTTP status code is ‘2xx’, and you will receive the specified format of results for each API.
> * Abnormal calls: HTTP status codes are in the 4xx and 500, and you will receive error codes and error messages specified for each API.


| HTTP STATUS CODE(ERROR TYPE) | Reasons For Errors |
|:-------------|:------------------|
| 400           | If there are no required request variables or the request variable names are incorrect |
| 401 | Authentication failed |
| 404           | If the API request URL is incorrect |
| 429           | When calling the API, if the daily allowance is exceeded |
| 500           | The API call was successful, but an error occurred due to API server maintenance or a system error |