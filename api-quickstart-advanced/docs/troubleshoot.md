---
hide:
  - toc
---
| Error Code | Description | Common Causes | Fix |
| :---- | :---- | :---- | :---- |
| 400 Bad Request | Invalid/missing API key | Mistyped api_key; omitted param | Verify api_key in Params matches your key/DEMO_KEY; resend. |
| 400 Bad Request | Invalid parameters | Unrecognized param; count >100 or invalid date (e.g., future or pre-1995-06-16) | Check params against docs (e.g., count=1-100, date=YYYY-MM-DD valid range); remove extras. |
| 429 Too Many Requests | Rate limit exceeded | Over 30/hour (DEMO_KEY) or 1,000/hour (personal key) | Wait 1 hour; check X-RateLimit-Remaining header; use personal key for higher quota. |
| Other (e.g., 404 Not Found, 500 Internal Server Error) | Endpoint issues or server outage | Wrong endpoint URL; NASA maintenance/shutdown | Verify endpoint https://api.nasa.gov/planetary/apod; check API status online; retry later. |

Errors return JSON with "error" object containing code and message (e.g., {"error": {"code": "OVER_RATE_LIMIT", "message": "Try again later"}}). 

Rarely, invalid endpoints (server issues, government shut downs) may return HTML. 