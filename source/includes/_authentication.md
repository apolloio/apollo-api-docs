
# Authentication

To access the Apollo API, you need to authenticate your requests. There are two ways to do this: OAuth 2.0 and API keys.

You should use OAuth 2.0 only if you are an Apollo Partner and want to utilize the Apollo API **on behalf of other Apollo users**. Otherwise, use API keys.

You can register for Oauth 2.0 or API keys [in your API settings](https://app.apollo.io/#/settings/integrations/api).

### OAuth 2.0
All examples on this page use API keys for authentication. If you want to use OAuth 2.0, you should include the `Authorization` header instead of the `X-Api-Key` header to your requests. Learn more about it in [our knowledge base](https://knowledge.apollo.io/hc/en-us/articles/28620185633549).

### API keys
> Sample request:

```shell
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

> If authentication is successful, you should see `{"is_logged_in":true}`

If you want to use API keys for authentication, you should include your API key in your requests as the `X-Api-Key` header value. In all examples on this page, replace `YOUR API KEY HERE` with your real API key. Learn more about it in [our knowledge base](https://knowledge.apollo.io/hc/en-us/articles/4415734629773).
