# Booking.com Automation Example

This document provides a walkthrough of the `main.py` script, which demonstrates a complete automation flow for Booking.com using Playwright and Browserless.

## Overview

The script performs the following actions:
1.  **Connects to Browserless**: Establishes a connection to the Browserless cloud or a local instance.
2.  **Navigates to Booking.com**: Loads the homepage and handles potential popups.
3.  **Performs a Search**:
    *   Enters a destination (e.g., "Dubai").
    *   Selects dates using the date picker.
    *   Clicks the search button.
4.  **Extracts Results**:
    *   Opens the first property in a new tab.
    *   Extracts the rooms table HTML.
    *   Takes screenshots at various stages.

## Code Breakdown

### 1. Connection Setup

The script checks the `CONNECTOR` environment variable to decide whether to connect to the cloud or a local instance.

```python
connector_type = os.getenv("CONNECTOR", "CLOUD").upper()
if connector_type == "LOCAL":
    browser = await p.chromium.launch(headless=False)
else:
    browser = await connect_to_hosted_browserless(p)
```

### 2. Screenshot Handling

A helper function `take_screenshot` ensures screenshots are saved in a dedicated `screenshots/` directory with timestamped filenames to avoid overwrites.

```python
async def take_screenshot(page, name_prefix):
    # ... creates directory if needed ...
    timestamp = datetime.now().strftime("%Y%m%d_%H%M%S")
    filename = f"{name_prefix}_{timestamp}.png"
    # ... saves screenshot ...
```

### 3. Interaction Logic

The script uses Playwright's `click`, `type`, and `wait_for_selector` methods to interact with the UI. It includes logic to handle dynamic elements like autocomplete dropdowns and date pickers.

```python
# Type destination
await page.type("input[name='ss']", "Dubai", delay=120)

# Handle Datepicker
await page.click("[data-date='2025-11-30']")
```

### 4. Data Extraction

Once on a property page, the script extracts the inner HTML of the rooms table for further processing.

```python
rooms_html = await property_page.locator("#hprt-table").inner_html()
with open("rooms_table.html", "w", encoding="utf-8") as f:
    f.write(rooms_html)
```

## Running the Example

To run this example, ensure you have the necessary dependencies installed and your Browserless token configured in `.env`.

```bash
python main.py
```
