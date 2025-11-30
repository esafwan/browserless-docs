# Introduction to Browserless Offerings

Browserless is a cloud-based service for running headless browsers at scale. It provides multiple offerings for different use cases, all using the same cloud infrastructure but accessed in various ways. This overview introduces the three main Browserless offerings (excluding legacy v1, which is deprecated) and when to use each:

- BrowserQL (BQL) – A GraphQL-based API for browser automation. BQL is a first-class, stealth-focused solution ideal for bypassing CAPTCHAs and bot detectors. It comes with a fully-featured web IDE and uses a minimalistic, scriptable query language instead of traditional code.
- Browsers as a Service (BaaS) v2 – A direct browser-as-a-service API that you can connect to using standard libraries like Puppeteer or Playwright. BaaS v2 closely mimics running a browser locally, allowing you to use familiar code by simply changing the connection URL to point at Browserless.
- RESTful APIs – A set of ready-made HTTP endpoints for common browser tasks (such as generating PDFs or screenshots, scraping content, etc.). These endpoints let you perform automation via simple HTTP(S) requests without writing a full script. They are great for quick integrations or one-off tasks, although not as flexible for complex flows.
- AI Integrations – Pre-built integrations with popular AI platforms and automation tools. Connect Browserless with n8n, Browser Use, Vercel AI SDK, and Langchain, for powerful automation capabilities to your AI applications and workflows.
- Enterprise – Self-hosted browser automation infrastructure for organizations requiring complete control, data sovereignty, and production-grade scale. Deploy via Docker or private deployment with real-time monitoring, session watching, live debugging, and enterprise-grade security and compliance.

## API Tokens and Authentication​

All Browserless cloud offerings require an API token for authentication. When you sign up, you'll get a unique token associated with your account. Include this token in every request, usually as a query parameter `?token=<YOUR_API_TOKEN_HERE>`. (The token can also be provided via headers in some cases, but using the token in query strings is most reliable.) [Get your API token](https://account.browserless.io/).

## Getting Started Checklist​

To quickly get started with Browserless:

1. Get your API token
2. Choose an API (BrowserQL, BaaS v2, or REST APIs)
3. Follow the respective Quick Start guide for your chosen API

# Comparison of BQL, BaaS v2, and REST APIs

To choose the right Browserless offering, it helps to understand their differences. The table below summarizes key features and capabilities of BrowserQL (BQL) vs Browserless BaaS v2 vs RESTful APIs:

| Feature/Capability | BrowserQL (BQL) | Browsers as a Service (v2) | REST APIs |
| --- | --- | --- | --- |
| Usage Paradigm | GraphQL mutations and queries (run via a cloud IDE or GraphQL endpoint) | Connect via WebSocket using Puppeteer/Playwright libraries | HTTP/HTTPS requests to specific endpoints |
| Primary Use-Case | Stealth web automation, bypassing bot detection and CAPTCHAs | Running custom automation scripts with familiar libraries | One-off tasks (PDF, screenshot, data extraction) via simple calls |
| Stealth Capabilities | Advanced (human-like behavior, CAPTCHA solving) | Basic (stealth mode parameter) | Basic (stealth parameter) |
| Flexibility | High (specialized automation language) | Highest (full browser control) | Limited (predefined endpoints) |
| Ease of Use | Medium (requires learning BQL) | Medium (requires knowledge of browser automation libraries) | Simplest (HTTP requests only) |
| Connection Method | HTTPS | WebSocket | HTTPS |
| Proxy Support | Advanced (built-in residential) | Yes (via parameters) | Yes (via parameters) |
| Session Management | Yes (reconnect mutation) | Yes (with proper setup) | No (stateless) |

## When to Use Each API​

### BrowserQL​

Best for scenarios requiring advanced bot detection bypass, such as:

- Sites with sophisticated bot detection systems
- When CAPTCHA solving is required
- When you need human-like browser behavior
- For stealth-first web automation

### BaaS v2​

Ideal for general-purpose browser automation:

- When you have existing Puppeteer or Playwright code
- For scenarios where you need full browser control
- For complex multi-step workflows
- When you're comfortable with browser automation libraries

### REST APIs​

Perfect for simple, stateless operations:

- Taking screenshots
- Generating PDFs
- Basic content extraction
- When integration simplicity is the priority
- For one-off tasks that don't require maintaining state


# Steps:

### 1) Run the free/FOSS Browserless Docker container

```bash
docker run --rm -p 3000:3000 \
  -e "CONCURRENT=5" \
  -e "TOKEN=mytoken123" \
  ghcr.io/browserless/chromium
```

This is the official open-source quick start (Chromium) and Browserless expects a token. ([Browserless][1])

Quick sanity check (optional):

```bash
curl -s http://localhost:3000/ | head
```

---

### 2) Basic automation: open google.com and search “tridz” (Node.js + puppeteer-core)

#### Install deps

```bash
mkdir bl-demo && cd bl-demo
npm init -y
npm i puppeteer-core
```

#### Create `google-search.js`

```js
const puppeteer = require("puppeteer-core");

async function maybeAcceptConsent(page) {
  // Google consent varies by region; try a few common buttons and ignore if not found.
  const candidates = [
    "button#L2AGLb",                 // "I agree" (common)
    "button[aria-label='Accept all']",
    "button:has-text('Accept all')",
    "button:has-text('I agree')",
  ];

  for (const sel of candidates) {
    try {
      const el = await page.$(sel);
      if (el) {
        await el.click();
        await page.waitForTimeout(500);
        return;
      }
    } catch (_) {}
  }
}

(async () => {
  const token = "mytoken123";
  const browser = await puppeteer.connect({
    browserWSEndpoint: `ws://localhost:3000?token=${token}`,
  }); // Browserless uses token in the WS URL :contentReference[oaicite:1]{index=1}

  try {
    const page = await browser.newPage();

    await page.goto("https://www.google.com/", { waitUntil: "domcontentloaded" });
    await maybeAcceptConsent(page);

    await page.waitForSelector("textarea[name='q'], input[name='q']", { timeout: 15000 });
    const q = (await page.$("textarea[name='q']")) || (await page.$("input[name='q']"));

    await q.click({ clickCount: 3 });
    await q.type("tridz");
    await page.keyboard.press("Enter");

    await page.waitForNavigation({ waitUntil: "domcontentloaded" });

    console.log("Title:", await page.title());
    // Optional proof:
    // await page.screenshot({ path: "results.png", fullPage: true });

  } finally {
    await browser.close();
  }
})().catch((e) => {
  console.error(e);
  process.exit(1);
});
```

#### Run it

```bash
node google-search.js
```

If Google shows a CAPTCHA in headless/remote mode, that’s normal for automated traffic. The script still demonstrates that your Docker Browserless endpoint + automation connection is working.

[1]: https://docs.browserless.io/enterprise/open-source "Open Source Deployment | Browserless.io"
