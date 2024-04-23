
# Authentication

> Sample request:

```shell
# With shell, you can just pass the correct header with each request
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -H "X-Api-Key: YOUR API KEY HERE" "https://api.apollo.io/v1/auth/health"
```

```python
import requests

url = "https://api.apollo.io/v1/auth/health"

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json',
    'X-Api-Key': 'YOUR API KEY HERE'
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

> If authentication is successful, you should expect to see {"is_logged_in":true}

Apollo uses API keys to allow access to the API. You may request an API key [here](https://app.apollo.io/#/settings/integrations/api)

Apollo expects the API key to be included in all API requests to the server as a query string parameter. 

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>
