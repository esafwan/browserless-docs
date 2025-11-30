Use straightforward REST endpoints for taking screenshots, generating PDFs, and extracting content. Great for integration with any programming language.

```
import requests

headers = {
    "Cache-Control": "no-cache",
    "Content-Type": "application/json"
}

data = {
    "url": "https://example.com/",
    "options": {
        "type": "png"
    }
}

response = requests.post(
    f"https://production-sfo.browserless.io/screenshot?token=${TOKEN}",
    headers=headers,
    json=data
)

print("Screenshot received! Size:", len(response.content))



```