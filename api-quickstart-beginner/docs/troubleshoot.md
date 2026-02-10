---
hide:
  - toc
---
You might run into the following common issues when testing NASA’s APOD API. Here’s how to address them.
### 400 Bad Request (Missing or Invalid API Key)
This happens if you forget to include the **api_key** Param or mistype your key (including DEMO_KEY). You tried to grab a table, but the hostess turned you away because your reservation wasn’t in the system. 

**The Fix**: Double-check the **Params** tab. Ensure "api_key" is the key, and the value matches exactly what NASA emailed (or use DEMO_KEY for testing). Resend the request.
### 429 Too Many Requests
This hits if you exceed rate limits (30/hour for DEMO_KEY, 1,000/hour for your key) and submit too many GET requests too fast. The restaurant's packed. Your wait time is one hour.

**The Fix**: Wait an hour. Use fewer requests or switch to a personal key for higher limits.
### Other Errors (e.g., Server Issues)

For rare problems like NASA server outages (e.g., during maintenance or a government shutdown), you might see 500 Internal Server Error or 503 Service Unavailable. If the endpoint URL is wrong (e.g., /apodd instead of /apod), expect a 404 Not Found, possibly as an HTML page instead of JSON. The kitchen's closed unexpectedly, or you knocked on the wrong door.

**The Fix**: Check NASA's API status (search "NASA API status" online). For 404, verify the endpoint URL matches https://api.nasa.gov/planetary/apod. If it's a shutdown or outage, wait.
