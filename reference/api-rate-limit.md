---
description: >-
  Our API imposes rate limits to ensure fair usage and maintain service
  availability for all users.
---

# API Rate Limit

Rate limiting restricts the number of requests clients can make to the API within a specific time window. This helps prevent abuse and ensures a consistent experience for all users.



#### Rate Limiting Parameters

* **Maximum Requests**: 100 requests per minute.
* **Time Window**: Requests are counted over a 1-minute sliding window.



Rate Limit Exceeded

If a client exceeds the rate limit, the API will respond with an HTTP status code 901 `Too Many Requests`, along with the following error message:

```
{
  "error": {
    "success": false
    "code": 901,
    "message": "Rate limit exceeded. Please try again later."
  }
}

```







