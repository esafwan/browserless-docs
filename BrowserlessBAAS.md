Browserless Snippets
Best for rapidly scaling existing, stable Puppeteer or Playwright scripts without changing your code.


```
import pyppeteer
import asyncio

async def main():
    browser = await pyppeteer.connect(
        browserWSEndpoint=f"wss://production-sfo.browserless.io?token=${TOKEN}"
    )
    page = await browser.newPage()
    await page.goto("https://example.com")

    screenshot = await page.screenshot()
    print(f"Screenshot taken! Size: {len(screenshot)} bytes")

    await browser.close()

asyncio.get_event_loop().run_until_complete(main())


```