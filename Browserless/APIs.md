# Browserless APIs Overview

Browserless offers a suite of APIs to simplify headless browser automation. These APIs cater to different use cases, from simple HTTP requests to full browser control.

## 1. REST APIs
Stateless HTTP endpoints for common tasks. Ideal for quick integrations and one-off operations without managing browser instances.

*   **`/scrape`**: Extracts structured JSON data or HTML content from web pages.
*   **`/pdf`**: Generates PDF documents from web pages.
*   **`/screenshot`**: Captures screenshots (PNG/JPG) of web pages.
*   **`/unblock`**: Fetches HTML content after executing JavaScript, specifically designed to bypass bot detection.
*   **`/function`**: Executes custom Puppeteer scripts sent in the request body.
*   **`/download`**: Facilitates file downloads from remote URLs.
*   **`/export`**: Exports session data.
*   **`/performance`**: Provides performance metrics related to browser operations.

## 2. Browsers as a Service (BaaS)
Allows you to connect to Browserless using standard automation libraries like Puppeteer and Playwright.
*   **Connection**: Connect via WebSocket (`wss://...`).
*   **Compatibility**: Works with existing scripts with minimal changes (just update the connection URL).
*   **Use Case**: Scaling existing automation scripts, complex workflows requiring state management.

## 3. BrowserQL (BQL)
A GraphQL-based API focused on stealth and efficiency.
*   **Stealth-First**: Built-in features to bypass bot detection and solve CAPTCHAs.
*   **Structured Queries**: Use GraphQL syntax to define browser interactions (navigation, clicking, typing, extracting).
*   **Efficiency**: Reduces bandwidth and latency by handling logic on the server side.

## 4. Chrome DevTools Protocol (CDP) API
Enhances open-source libraries with additional capabilities.
*   **Features**: Generate live URLs for hybrid automation, solve CAPTCHAs, and retrieve unique page identifiers.
*   **Language Agnostic**: Can be used with any library that supports CDP.