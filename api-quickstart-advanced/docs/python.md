---
hide:
  - toc
---
Use Python's requests library to fetch APOD data in scripts or apps, automating what Postman tests.

```python

import requests

# Basic GET for today's APOD

url = "https://api.nasa.gov/planetary/apod"

params = {"api_key": "DEMO_KEY"}  # Replace with your key

response = requests.get(url, params=params)

if response.status_code == 200:

    data = response.json()

    # For count>1, data is a list—loop over data (e.g., for item in data: print(item["title"]))

    print(data["title"])

    print(data["url"])

else:

    try:

        error_data = response.json()

        msg = error_data.get('msg', 'Unknown error')

    except:

        msg = 'Non-JSON error response'

    print(f"Error: {response.status_code} - {msg}")

# Advanced: Random or specific date

params_random = {"api_key": "DEMO_KEY", "count": 5}

params_date = {"api_key": "DEMO_KEY", "date": "2025-10-01"}

```

The response is a dict with keys like 'title' (image name), 'url' (standard res), 'hdurl' (high res if available), 'explanation' (description).

![python output](images/python-run.png)
