# Browsers as a Service (BaaS) Example

**Browsers as a Service (BaaS)** allows you to run your existing Puppeteer or Playwright scripts on Browserless's cloud infrastructure. This mimics running a browser locally but offloads the execution to the cloud, enabling easy scaling and management.

## Key Benefits
*   **Scalability**: Run hundreds of browsers concurrently without managing infrastructure.
*   **Compatibility**: Works with standard Puppeteer, Playwright, and Selenium libraries.
*   **Stealth**: Access to Browserless's stealth features and proxy networks.

## Python Example (Pyppeteer)

This example demonstrates how to connect to Browserless using `pyppeteer`. The only major change from a local script is using `pyppeteer.connect` with the Browserless WebSocket URL.

```python
import pyppeteer
import asyncio
import os

# Ensure you have your API token set in your environment
TOKEN = os.getenv("BROWSERLESS_TOKEN", "YOUR_API_TOKEN")

async def main():
    print("Connecting to Browserless...")
    # Connect to the Browserless WebSocket endpoint
    browser = await pyppeteer.connect(
        browserWSEndpoint=f"wss://production-sfo.browserless.io?token={TOKEN}"
    )
    
    page = await browser.newPage()
    
    print("Navigating to example.com...")
    await page.goto("https://example.com")

    # Perform actions as usual
    screenshot = await page.screenshot()
    print(f"Screenshot taken! Size: {len(screenshot)} bytes")

    await browser.close()
    print("Browser closed.")

if __name__ == "__main__":
    asyncio.get_event_loop().run_until_complete(main())
```

## Connection URL Format
The WebSocket URL typically follows this format:
`wss://production-sfo.browserless.io?token=YOUR_TOKEN`

You can add additional parameters for configuration, such as:
*   `&stealth=true`: Enable stealth mode.
*   `&headless=false`: Run in headful mode (useful for debugging with LiveURL).
*   `&--proxy-server=...`: Set a proxy server.