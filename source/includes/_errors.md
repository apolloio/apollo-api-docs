# Errors

A valid API Key is required for processing API requests. 

<!-- 
The Kittn API uses the following error codes: -->


<!-- Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The kitten requested is hidden for administrators only
404 | Not Found -- The specified kitten could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The kitten requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later. -->


> Sample response:

```json
{
    "status": 401,
    "message": "Invalid access credentials."
}
```


`status`    | Example `message`                                               | Reason
------------|  -------------------------------                                |----------
401         |  Invalid access credentials.                                    | The API key is not valid
403         |  This endpoint is only available to Apollo users on paid plans. | The API key is not authorized to perform the action
429         | The maximum number of api calls allowed for `endpoint`  is `x` times per `t`. Please upgrade your plan from https://app.apollo.io/#/settings/plans/upgrade.   | The team with the API key has been rate-limited. We also send the usage in the headers in this


