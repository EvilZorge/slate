# Errors

The OptimizePlayer API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is wrong
401 | Unauthorized -- Your API key is wrong or you tried to access unavailable entity.
406 | Not Acceptable -- You requested a format that isn't json.
422 | Unprocessable entity -- You tried to access method with an invalid parameters.
429 | Too Many Requests -- You're sending too many requests! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
