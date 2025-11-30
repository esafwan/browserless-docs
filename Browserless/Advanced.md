# Browserless Advanced Documentation

This document covers advanced configurations, specialized APIs, and features for robust browser automation.

## 1. Advanced Configurations

### Puppeteer and Playwright Configurations
Browserless allows fine-grained control over browser behavior when using libraries like Puppeteer and Playwright. You can configure launch options to optimize for performance, stealth, or specific environments.

### Hybrid Automation
Hybrid automation combines the ease of Browserless cloud infrastructure with your existing local workflows. It involves connecting your local scripts to the Browserless cloud using the WebSocket endpoint, allowing you to offload execution while maintaining local control.

### Proxy Configuration
To enhance privacy and achieve geographic targeting, Browserless supports proxy configurations. You can use built-in residential proxies or connect to third-party proxy providers by passing proxy details in the connection parameters.

## 2. Specialized APIs

### `/function` API
Execute custom JavaScript or Puppeteer code directly on the Browserless infrastructure. This API is powerful for serverless-style execution where you send the code to be run, and Browserless handles the environment. It supports returning various file types (PDFs, screenshots) and includes features like Live Debugger.

### `/scrape` API
A dedicated endpoint for extracting data from websites. It simplifies the process of navigating to a page and retrieving content, often supporting arbitrary JavaScript execution via `page.evaluate` to handle dynamic content.

### Screencast API
Generate high-quality WebM video files of your automation sessions. This is useful for debugging, auditing, or creating visual records of browser interactions.

## 3. Specialized Features

### Recording Sessions (LiveURL)
Capture complete browser sessions as video files. You can enable this by setting the `record=true` query parameter. It's particularly useful for debugging headless sessions or reviewing automated interactions.

### Bot Detection and CAPTCHA Solving
Browserless provides advanced mechanisms to bypass bot detection systems and solve CAPTCHAs. This includes stealth modes and integration with solving services, ensuring your automations can access protected content.

### AI Integrations
Browserless integrates with AI platforms like Vercel AI SDK, n8n, and Langchain. This allows you to build powerful AI agents that can browse the web, extract data, and interact with pages as part of larger AI workflows.