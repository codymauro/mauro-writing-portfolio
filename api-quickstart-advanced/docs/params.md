---
hide:
  - toc
---
Enhance requests with params for flexible in-app integration.
### Randomize Astronomy Photos of the Day: 
1. Add param key=count, value=1-100 (e.g., count=5 for 5 unique random entries).
2. URL becomes: https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&count=5.  
3. Send. Response is a JSON array of entries.
### Pull APOD from specific date: 
1. Add param key=date, value=YYYY-MM-DD (e.g., date=[current date]; must be after 1995-06-16; no future dates).  
2. URL: https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=[current date].  
3. Send. Response is single JSON for that date.

![additional parameters added to GET](images/dev-mult-param.png)

Combine params as needed (e.g., date with thumbs=true to include 'thumbnail_url' for videos if media_type='video'). Note: The 'hd' param is deprecated and ignored; 'hdurl' appears automatically if a high-resolution image is available.

For additional params, see the table below: 

| Parameter | Type | Default | Description |
| :---- | :---- | :---- | :---- |
| date | YYYY-MM-DD |today | The date of the APOD image to retrieve. |
| start_date | YYYY-MM-DD | none | The start of a date range, when requesting date for a range of dates. Cannot be used with *date*. |
| end_date | YYYY-MM-DD | today | The end of the date range, when used with *start_date*. |
| count | int | none | if this is specified then *count* randomly chosen images will be returned. Cannoy be used with *date* or *start_date* and *end_date*. |
| thumbs | bool | False | Return the URL of video thumbnail. If an APOD is not a video, this parameter is ignored. |

Once tested in Postman, integrate the API programmatically with code examples on the next pages.
