# BrowserQL

BrowserQL (BQL) is a revolutionary GraphQL-based browser automation API that redefines how web automation is done. Built for the modern web and powered by Browserless's cloud-based infrastructure for running headless browsers at scale, BQL uses a minimal, scriptable query language specifically designed for stealth-first automation that bypasses even the most sophisticated bot detection systems.

This robust platform ensures your automation runs reliably with global endpoints, advanced proxy support, and enterprise-grade performance, while BQL's intuitive GraphQL syntax, powerful stealth capabilities, and integrated development environment let you move fast without sacrificing control or effectiveness. No more context switching, no complex setup - just powerful browser automation that works.

### Why Use BrowserQL?​

BrowserQL is the **best solution** when you need to:

- Bypass advanced bot detection systems.
- Automate CAPTCHA-solving flows.
- Mimic human-like interactions reliably.
- Build stealth-first automations at scale.

With decades of research and development behind it, BrowserQL is a production-grade solution designed to succeed where traditional browser automation fails.

### Key Features & Capabilities​

- Advanced Stealth Technology: Human-like interactions, CAPTCHA solving, and fingerprint masking that outperforms traditional automation tools
- GraphQL-Powered: Simple, declarative mutations for complex browser actions - no more wrestling with traditional automation code
- Fully-Featured Web IDE: Live session preview, built-in documentation, and zero-installation development environment
- Production-Ready: Decades of research and development behind a solution designed to succeed where others fail
- Seamless Integration: Export to any language or connect with existing Puppeteer/Playwright scripts

info

If you already have an automation library that works over WebSockets, you can mix-and-match BrowserQL with the library of your choice. To learn how to integrate BQL, check the guides below:

- Connecting with Puppeteer
- Connecting with Playwright

There's a lot more to BQL than just this. Our Editor comes with built-in documentation, a live Viewer and Devtools to get you started. Refer to the following pages to learn more about BQL:

- Mutation Reference

If you already have a Puppeteer script, our AI (which you can find at the top of this page - with the button Ask AI) does a great job of helping you to move from Puppeteer to BQL.

## Next Steps​

Ready to dive deeper into BrowserQL? Explore these key areas to maximize your browser automation capabilities:

[Getting StartedLearn how to get started with BrowserQL and set up your first automation](https://docs.browserless.io/browserql/getting-started)
[Launch Parameters and OptionsConfigure browser launch parameters and options to optimize your automation sessions](https://docs.browserless.io/browserql/launch-parameters)
[Writing BQL QueriesMaster the BrowserQL language basics and learn how to write effective automation queries](https://docs.browserless.io/browserql/writing-bql/language-basics)


# Quick Start

Get started with BrowserQL in minutes by following these steps:

1. Sign UpSign up for a Browserless account (free plan available).
2. Get API KeyGet your API Key from the account dashboard.
3. Access IDEAccess the BQL web editor. Learn more about using the IDE.
4. Run Your First QueryCopy and paste this example query into the IDE to scrape the first headline from Hacker News, and click play:mutation ScrapeHN {  goto(url: "https://news.ycombinator.com", waitUntil: firstMeaningfulPaint) {    status    time  }  firstHeadline: text(selector: ".titleline") {    text  }}Click Run in the IDE to execute this query.Breaking this down, we're:

Defining we want to run a mutation and naming our script as ScrapeHN

Instructing a browser to goto the Hacker News site, and wait for the firstMeaningfulPaint event to fire

Asking to return both the time it took and the HTTP-code's status once the waitUntil has fired

Giving our action an alias, in this case firstHeadline

Extracting the text of a specified selector
5. Check OutputThe result will be a JSON response:{"data": {"viewport": {  "width": 1366,  "height": 768,  "time": 2},"goto": {  "status": 200,  "time": 1467},"firstHeadline": {  "text": "Rust cross-platform GPUI components (github.com/longbridge)"}}}

tip

Don't worry if you're new to GraphQL! BQL's syntax is intuitive, and you can learn as you go. Check out the [Language Basics](https://docs.browserless.io/browserql/writing-bql/language-basics) section to understand GraphQL concepts in BQL.

## Exporting Your Query​

You can export your BrowserQL queries and run them programmatically in your application. [Learn how to export and use queries in your code](https://docs.browserless.io/browserql/using-the-ide/using-api-calls).

## Next Steps​

Ready to start building with BrowserQL? Explore these key areas to maximize your browser automation capabilities:

[Writing BrowserQLMaster GraphQL mutations, aliases, and BQL syntax to create powerful browser automation scripts](https://docs.browserless.io/browserql/writing-bql/language-basics)
[Using the IDEExplore built-in documentation, query history, code export, and keyboard shortcuts in the BQL Editor](https://docs.browserless.io/browserql/using-the-ide/ide-features)
[Launch ParametersConfigure browser launch options and settings to customize your automation environment](https://docs.browserless.io/browserql/launch-parameters)


# Language Basics

Learning a new language can be intimidating, but mastering BQL doesn't have to be difficult. This guide provides a straightforward overview of how to write BQL with clear examples.

## GraphQL Basics for BQL​

BrowserQL uses **GraphQL** as its query language. If you're new to GraphQL, here are the key concepts you need to know:

### Mutations vs Queries​

- Mutations: Actions that change state (like navigating, clicking, typing). In BQL, everything is a mutation because all actions happen inside the browser.
- Queries: Read-only operations (not used in BQL since browser automation requires actions).

### Basic GraphQL Syntax​

Every Graphql script follows this pattern:

```
mutation ScriptName {  actionName(arguments) {    responseFields  }}
```

### Key GraphQL Concepts in BQL​

- Arguments: Parameters you pass to actions (like url: "https://example.com")
- Response Fields: Data you want back (like status, time, text)
- Aliases: Custom names for actions (like firstClick: click(...))

Refer to the following resources for a deeper understanding of GraphQL:

- Official GraphQL Documentation
- GraphQL Query Language Guide
- GraphQL Best Practices

## Understanding BQL Structure​

A BQL script consists of a **mutation** that contains one or more **fields**:

```
mutation ScriptName {  field1(arguments) { responses }  field2(arguments) { responses }}
```

Each field represents a browser action. Let's break down what makes up a field:

### Anatomy of a Mutation Field​

Each field has three components:

1. Field Name: The action to perform (e.g., goto, click, type)
2. Arguments: Parameters that configure the action (e.g., url, selector, text)
3. Response Fields: The data you want returned (e.g., status, time, text)

**Example:**

```
mutation ExampleName {  fieldName(argument: "value") {    responseField  }}
```

Complete Reference

Find all available mutations, arguments, and responses in the [BQL API Reference](https://docs.browserless.io/bql-schema/operations/mutations/back) or the [Built-in Documentation](https://docs.browserless.io/browserql/using-the-ide/ide-features#built-in-documentation) in the IDE.

### Combining Multiple Actions​

BQL's power comes from chaining multiple actions in a single mutation. With core fields like [goto](https://docs.browserless.io/bql-schema/operations/mutations/goto), [text](https://docs.browserless.io/bql-schema/operations/mutations/text), [click](https://docs.browserless.io/bql-schema/operations/mutations/click), [type](https://docs.browserless.io/bql-schema/operations/mutations/type), and [verify](https://docs.browserless.io/bql-schema/operations/mutations/verify), you can build complex automations concisely.

### Using Aliases​

When using the same mutation field multiple times in a query, you must provide **aliases** to distinguish them. GraphQL requires unique field names within the same mutation:

```
mutation LoginForm {  goto(url: "https://example.com/login") {    status  }    click(selector: "#email-field") {    x    y  }    click(selector: "#password-field") {  # ❌ Error: Duplicate field name    x    y  }}
```

The above **mutation will fail** because both `click` operations have the same field name.

**Solution:** Use aliases to make each field unique. Aliases also let you customize how results appear in your JSON response:

```
mutation LoginForm {  goto(url: "https://example.com/login") {    status  }    clickEmail: click(selector: "#email-field") {    x    y  }    clickPassword: click(selector: "#password-field") {    x    y  }    typeEmail: type(    selector: "#email-field"    text: "user@example.com"  ) {    time  }    typePassword: type(    selector: "#password-field"    text: "securepassword"  ) {    time  }    submitLogin: click(selector: "#login-button") {    x    y  }}
```

#### JSON Response with Aliases​

The aliases become the keys in your JSON response, making the data structure clear and meaningful:

```
{  "data": {    "goto": {      "status": 200    },    "clickEmail": {      "x": 150,      "y": 200    },    "clickPassword": {      "x": 150,      "y": 250    },    "typeEmail": {      "time": 245    },    "typePassword": {      "time": 189    },    "submitLogin": {      "x": 200,      "y": 350    }  }}
```

Pro Tip

**Avoid reserved words**: Don't use GraphQL keywords as aliases

## Common BQL Patterns​

Now that you understand the fundamentals, let's explore common patterns for building automation scripts.

### Extracting Data​

Use `text` or `html` mutations to extract information from pages:

- Extract Text
- Extract HTML

```
mutation GetProductInfo {  goto(url: "https://example.com/product") {    status  }  productName: text(selector: "span#productTitle") {    text  }}
```

**Returns:**

```
{  "productName": {    "text": "Coffee and Espresso Maker"  }}
```

tip

Omit the `selector` to retrieve the entire page's text content.

```
mutation GetPageHTML {  goto(url: "https://example.com") {    status  }  pageContent: html(selector: "div.content") {    html  }}
```

**Returns:**

```
{  "pageContent": {    "html": "<h1>Example Domain</h1><p>This domain is for use in illustrative examples...</p>"  }}
```

tip

Omit the `selector` to retrieve the entire page's HTML.

### Interacting with Pages​

BrowserQL automatically waits for elements to be present, visible, and scrolls them into view. Use `click` and `type` mutations to interact with page elements.

#### Clicking Elements​

```
mutation ClickExample {  goto(url: "https://example.com/login") {    status  }  loginButton: click(    selector: "button#login"    visible: true  ) {    x    y  }}
```

**Setting Timeouts:** By default, BQL waits up to 30 seconds for elements. Override with the `timeout` argument (in milliseconds):

```
click(  selector: "button#login"  timeout: 10000  // Wait max 10 seconds) {  x  y}
```

#### Typing Text​

BQL types with human-like randomized delays between keystrokes for natural input patterns.

```
mutation TypeExample {  goto(url: "https://google.com") {    status  }  searchInput: type(    selector: "form textarea"    text: "BrowserQL automation"  ) {    time  }}
```

**Custom Typing Delays:** Control the keystroke delay range with the `delay` argument `[min, max]` in milliseconds:

```
type(  selector: "input#email"  text: "user@example.com"  delay: [50, 150]  // Random delay between 50-150ms per keystroke) {  time}
```

### Solving CAPTCHAs​

The [verify](https://docs.browserless.io/bql-schema/operations/mutations/verify) mutation automatically handles CAPTCHAs, even when hidden in iframes or shadow DOMs:

```
mutation BypassCaptcha {  goto(url: "https://example.com/login") {    status  }  solveCaptcha: verify(type: cloudflare) {    found    solved    time  }}
```

### Hybrid Mode: Connecting Puppeteer/Playwright​

Generate a WebSocket endpoint to connect external libraries like Puppeteer or Playwright to your BQL session:

```
mutation HybridSession {  goto(url: "https://example.com") {    status  }  reconnect(timeout: 30000) {    browserWSEndpoint  }}
```

Use the returned `browserWSEndpoint` to connect your library and continue automation. [Learn more about hybrid mode](https://docs.browserless.io/browserql/hybrid-bql).

## Next Steps​

BrowserQL simplifies web automation with intuitive commands and a structure that's easy to learn. Explore these key areas to build more sophisticated automations:

[Conditional LogicLearn how to create "do A or do B" workflows that adapt to different page conditions](https://docs.browserless.io/browserql/writing-bql/conditional-logic)
[Waiting for ThingsMaster the art of waiting for elements, navigation events, and network responses](https://docs.browserless.io/browserql/writing-bql/waiting-for-things)
[Exporting ScriptsConvert your BQL queries to code in multiple programming languages for integration](https://docs.browserless.io/browserql/using-the-ide/using-api-calls)


# Conditional Logic

One of BrowserQL's most powerful features is its ability to create dynamic, condition-based workflows using `if` and `ifnot` mutations. This allows you to build smart automation that adapts to different scenarios, handles errors gracefully, and creates branching logic based on page conditions.

Conditional logic in BrowserQL allows you to:

- Handle different page states (loaded vs. error)
- Respond to varying content (elements present vs. absent)
- Create fallback behaviors (try method A, fallback to method B)
- Build adaptive scraping (different selectors for different page layouts)

## Basic Conditional Structure​

The basic pattern for conditional logic in BrowserQL uses two key mutations:

- if: Executes nested mutations when a condition is true
- ifnot: Executes nested mutations when a condition is false

```
mutation ConditionalExample {  goto(url: "https://example.com") {    status  }    if(condition) {    // Do A - when condition is true  }    ifnot(condition) {    // Do B - when condition is false  }}
```

### Response Code Conditions​

One of the most common scenarios is handling different HTTP response codes.

- Basic Response Handling
- Multiple Response Codes

```
mutation ResponseHandling {  goto(url: "https://protected-site.com") {    status  }    # If we get a 403 Forbidden - handle bot detection  if(response: {codes: 403}) {    verify(type: cloudflare) {      solved    }        # Try navigation again after verification    goto(url: "https://protected-site.com") {      status    }  }    # If we get a successful response - proceed normally  ifnot(response: {codes: 403}) {    title {      title    }        text(selector: "h1") {      text    }  }}
```

```
mutation MultipleResponseHandling {  goto(url: "https://example.com") {    status  }    # Handle client errors (4xx)  ifError4xx:if(response: {codes: [400, 401, 403, 404]}) {    screenshot {      base64    }        text(selector: "body") {      text    }  }    # Handle server errors (5xx)  ifError5xx:if(response: {codes: [500, 502, 503]}) {    waitForTimeout(time: 5000) {      time    }        # Retry the request    goto(url: "https://example.com") {      status    }  }    # Handle successful responses (2xx)  ifnot(response: {codes: [400, 401, 403, 404, 500, 502, 503]}) {    html(selector: "main") {      html    }  }}
```

### Element Presence Conditions​

Check if elements exist on the page and create different workflows accordingly.

- Cookie Banner Handling
- Different Login Forms

```
mutation CookieBannerHandling {  goto(url: "https://example.com") {    status  }    # If cookie banner exists - accept cookies  if(selector: "#cookie-banner, .cookie-consent, [data-testid='cookie-banner']") {    click(selector: "#cookie-banner .accept, .cookie-consent .accept") {      x      y    }        waitForTimeout(time: 1000) {      time    }  }    # Whether banner existed or not, continue with main content  text(selector: "h1") {    text  }    html(selector: ".main-content") {    html  }}
```

```
mutation AdaptiveLogin {  goto(url: "https://app.example.com/login") {    status  }    # Check for email/password form  if(selector: "input[type='email'], input[name='email']") {    typeEmail:type(selector: "input[type='email'], input[name='email']", text: "user@example.com") {      selector    }        typePassword: type(selector: "input[type='password']", text: "password123") {      selector    }        click(selector: "button[type='submit'], .login-btn") {      x      y    }  }    # Check for username/password form (different structure)  ifnot(selector: "input[type='email'], input[name='email']") {    typeUsername: type(selector: "input[name='username'], #username", text: "myusername") {      selector    }        typePassword: type(selector: "input[type='password']", text: "password123") {      selector    }        click(selector: "button[type='submit'], .submit-btn") {      x      y    }  }}
```

### Content-Based Conditions​

Make decisions based on the actual content of the page.

- Search Results Handling
- Content Variations

```
mutation SearchResultsHandling {  goto(url: "https://example-store.com") {    status  }    # Perform search  type(selector: ".search-input", text: "wireless headphones") {    selector  }    click(selector: ".search-button") {    x    y  }    # Wait for results to load  waitForTimeout(time: 2000) {    time  }    # If results found - extract product data  if(selector: ".product-item, .search-result-item") {    mapSelector(selector: ".product-item") {      name: text(selector: ".product-name")      price: text(selector: ".product-price")       rating: text(selector: ".product-rating")      imageUrl: attribute(selector: ".product-image img", name: "src")    }  }    # If no results found - try alternative search  ifnot(selector: ".product-item, .search-result-item") {    # Clear search and try broader term    clickClear: click(selector: ".search-clear, .clear-button") {      x      y    }        type(selector: ".search-input", text: "headphones") {      selector    }        clickSearch: click(selector: ".search-button") {      x      y    }        waitForTimeout(time: 2000) {      time    }        # Extract whatever results we get    mapSelector(selector: ".product-item, .item") {      name: text(selector: ".product-name, .item-title")      price: text(selector: ".product-price, .price")    }  }}
```

```
mutation ContentVariations {  goto(url: "https://news-site.com") {    status  }    # Check for paywall  if(selector: ".paywall, .subscription-required, [data-paywall]") {    # Try to find free preview content    text(selector: ".article-preview, .free-content") {      text    }        # Look for alternative free articles    mapSelector(selector: ".free-article") {      title: text(selector: ".article-title")      excerpt: text(selector: ".article-excerpt")      link: attribute(selector: "a", name: "href")    }  }    # If no paywall - get full article content  ifnot(selector: ".paywall, .subscription-required, [data-paywall]") {    titleText: text(selector: "h1, .article-title") {      text    }        content: html(selector: ".article-content, .post-content") {      html    }        authorText: text(selector: ".author, .byline") {      text    }        publishDateText: text(selector: ".publish-date, .date") {      text    }  }}
```

## Sequential Conditional Logic​

You can create complex decision trees using sequential conditional logic. Note that `if` and `ifnot` mutations cannot be nested within each other, but you can achieve the same logical outcomes using sequential conditionals with compound selectors:

```
mutation SequentialConditions {  goto(url: "https://e-commerce-site.com/product/123") {    status  }    # Check for product with discount (exists, in stock, on sale)  ifStockDiscounted: if(selector: ".product-details .in-stock .discount, .product-details .available .sale-price") {    mapSelector(selector: ".product-details") {      name: text(selector: ".product-name")      originalPrice: text(selector: ".original-price")       salePrice: text(selector: ".sale-price")      discount: text(selector: ".discount-percent")    }  }    # Check for product in stock without discount  ifStock: if(selector: ".product-details .in-stock:not(.discount), .product-details .available:not(.sale-price)") {    mapSelector(selector: ".product-details") {      name: text(selector: ".product-name")      price: text(selector: ".price")      availability: text(selector: ".stock-status")    }  }    # Check for product out of stock  ifOutOfStock: if(selector: ".product-details:not(:has(.in-stock)):not(:has(.available))") {    mapSelector(selector: ".product-details") {      name: text(selector: ".product-name")      status: text(selector: ".out-of-stock, .unavailable")      restockDate: text(selector: ".restock-date")    }  }    # Product doesn't exist - capture error info  ifnot(selector: ".product-details") {    text(selector: ".error-message, .not-found") {      text    }  }}
```

### Fallback Strategies​

Create robust automation with multiple fallback options using sequential conditionals:

```
mutation FallbackStrategies {  goto(url: "https://dynamic-site.com") {    status  }    # Try primary selector  if(selector: ".primary-selector") {    text(selector: ".primary-selector") {      text    }  }    # Try secondary selector (only if primary doesn't exist)  ifnot1: ifnot(selector: ".primary-selector") {    text(selector: ".secondary-selector") {      text    }  }    # Try tertiary selector (only if primary and secondary don't exist)  ifnot2: ifnot(selector: ".primary-selector, .secondary-selector") {    text(selector: ".tertiary-selector") {      text    }  }    # Last resort fallback (if none of the above exist)  ifnot3: ifnot(selector: ".primary-selector, .secondary-selector, .tertiary-selector") {    text(selector: "body") {      text    }  }}
```

## Next Steps​

Now that you understand conditional logic, explore these related topics to build even more sophisticated automations:

[Waiting for ThingsCombine conditional logic with precise waiting strategies for robust automation](https://docs.browserless.io/browserql/writing-bql/waiting-for-things)
[Exporting ScriptsConvert your conditional BQL queries to code for integration into your applications](https://docs.browserless.io/browserql/using-the-ide/using-api-calls)
[Bot DetectionUse conditional logic to handle complex detection scenarios and CAPTCHA challenges](https://docs.browserless.io/browserql/bot-detection/overview)

# Waiting for Things

BrowserQL offers 5 different ways to wait for preconditions to be met on the page before returning the response. These built-in waiters make your automations more reliable by responding to real page conditions, avoiding the fragility of fixed delays.

- waitForNavigation
- waitForRequest
- waitForResponse
- waitForSelector
- waitForTimeout

BQL Schemas

For more details on BQL mutations, refer to the [BrowserQL Schema](https://docs.browserless.io/bql-schema/schema) reference pages.

## waitForNavigation​

Waits for a navigation event to fire, useful for clicking an element and waiting for a page load.

The object can have any of these values:

- timeout: Float, optional — The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.
- waitUntil: WaitUntilGoto enum, optional — When to consider the page fully-loaded and proceed with further execution

```
mutation waitingForNavigation {  goto(url: "https://example.com/") {    status  }  waitForNavigation(waitUntil: load) {    status  }}
```

## waitForRequest​

Waits for the browser to make a particular request.

The object can have any of these values:

- method: Method, optional — The method of the request to wait for.
- timeout: Float, optional — How long to wait for the request to be made before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.
- url: String, optional — The pattern of the request URL to wait for, using glob-style pattern-matching.

```
mutation waitingForARequest {  goto(url: "https://example.com/") {    status  }  waitForRequest(method: GET) {    time  }}
```

## waitForResponse​

Waits for a particular network response to be made back to the browser.

The object can have any of these values:

- statuses: [int] list, optional — The HTTP Response code(s) of the URL to wait for. Can be a single HTTP code or a list of desired codes.
- url: String, optional — The pattern of the response URL to wait for, using glob-style pattern-matching.

```
mutation waitingForAResponse {  goto(url: "https://example.com/") {    status  }  waitForResponse(codes: [200]) {    time  }}
```

## waitForSelector​

Wait for a selector to appear in page. If at the moment of calling the method the selector already exists, the method will return immediately. If the selector doesn't appear after the timeout milliseconds of waiting, the function will throw.

The object can have any of these values:

- selector: String, required — A valid CSS selector.
- timeout: Number, optional — Maximum number of milliseconds to wait for the selector before failing.
- visible: Boolean, optional — Wait for the selected element to be present in DOM and to be visible, i.e. to not have display: none or visibility: hidden CSS properties.

```
mutation waitingForASelector {  goto(url: "https://example.com/") {    status  }  waitForSelector(selector: "h1" timeout: 5000) {    selector  }}
```

## waitForTimeout​

If all else doesn't work, you can always wait for a predefined number of milliseconds.

The object needs the following value:

- time: Float, required - The amount of time to wait for, in milliseconds.

```
mutation waitingForAHardcodedTimeout {  goto(url: "https://example.com/") {    status  }  waitForTimeout(time: 1000) {    time  }}
```

## Next Steps​

Master the art of waiting in BrowserQL? Explore these advanced topics to build more reliable automations:

[Using ExportsSave and use dynamic data in later actions for better flexibility and reuse](https://docs.browserless.io/browserql/writing-bql/exporting-variables)
[Exporting ScriptsExport your waiting-enabled BQL queries to integrate with your development workflow](https://docs.browserless.io/browserql/using-the-ide/using-api-calls)
[Advanced ConfigurationsExplore advanced BrowserQL features and configurations for complex automation scenarios](https://docs.browserless.io/browserql/advanced-config/scraping-structured-data)


# Exporting Variables

Many queries in BrowserQL produce data that you might want to reuse in subsequent queries or export for use outside of BrowserQL. BrowserQL provides an `@export` feature, called a "directive", that allows you to save query results into variables for later use.

This is especially useful for capturing dynamic data from web pages, such as tokens, IDs, or any other information that needs to be referenced in later steps of your automation. Using this feature can help streamline your workflows and make your automations more efficient without having to run several queries to capture and reuse data.

BQL Schemas

For more details on BQL mutations, refer to the [BrowserQL Schema](https://docs.browserless.io/bql-schema/schema) reference pages.

## Export Directive​

Using the directive is straightforward. You simply append `@export(as: "name")` to the field you want to export. The required `as` argument specifies the name of the variable that will hold the exported value, which you can use in subsequent actions.

Once a variable is exported, you'll need to reference it somewhere where you want to use it. You can do this by using the `${variableName}` syntax in the parameters of other actions. This tells BrowserQL to substitute the value of the exported variable at that point in the query.

Let's use Hacker News as an example. Suppose you want to export the title of the top story on Hacker News and use it in a later action. Your query would look like this:

```
mutation NavigateToTopPost {  # First navigate to HN  goto(url: "https://news.ycombinator.com/") {    status  }  # Next, run some JavaScript on the page to find the first submission link  evaluate(content: "document.querySelector('.athing.submission .title a').href") {    # This is where we both define what value we want to export and give it a name    value @export(as: "topStoryLink")  }  # In order to use this reference you'll need to use a "${variableName}" syntax  # where you want to use the variable, here we use it in the goto action's url param  gotoTopLink: goto(url:"${topStoryLink}") {    status  }  # Finally, let's grab the title of the page!  title {    title  }}
```

For now exports support only scalar values like strings and numbers. Complex objects or arrays cannot be exported directly but may be supported in the future.

If you attempt to use an export that hasn't been defined yet, BrowserQL will treat it as a regular string and simply pass through the raw text itself unaltered.

## Next Steps​

Master the art of waiting in BrowserQL? Explore these advanced topics to build more reliable automations:

[Waiting For ThingsCombine waiting strategies with conditional logic to handle different page states dynamically](https://docs.browserless.io/browserql/writing-bql/waiting-for-things)
[Exporting ScriptsExport your waiting-enabled BQL queries to integrate with your development workflow](https://docs.browserless.io/browserql/using-the-ide/using-api-calls)
[Advanced ConfigurationsExplore advanced BrowserQL features and configurations for complex automation scenarios](https://docs.browserless.io/browserql/advanced-config/scraping-structured-data)


# Launch Parameters and Options

Browserless allows extensive configuration of how browsers are launched and behave during
your sessions. These launch parameters can be provided either via query parameters in the
URL or through a special JSON launch payload. Whether you're using BQL, BaaS v2, or REST, these
options let you tweak the browser environment to fit your needs.

## Passing Launch Options​

Two ways to specify launch options:

1. Individual Query Parameters: Add options directly to URLs (e.g., &headless=false, &proxy=residential). Best for simple boolean options.
2. Combined launch Parameter (JSON): For complex configurations, use a single query param launch with a JSON string as its value. This JSON can include any Chrome flags or Browserless-specific settings in a structured way. It's essentially the equivalent of Puppeteer's launch({ options }) but provided to the cloud service:
&launch={"headless":false,"stealth":true,"args":["--window-size=1920,1080"]}
(URL-encoded) would configure a headful, stealth-enabled browser with a specific window size.

Browserless merges both methods if used together, with individual parameters taking precedence. Use query params for simple toggles and the launch parameter for multiple settings.

## Launch Options (Query Parameters)​

Below is a list of available launch options you can use in query strings. BrowserQL
internally uses some of these, but BQL users typically set these via the IDE session settings
rather than manually in a URL.

| Parameter | Description | Default |
| --- | --- | --- |
| launch | Launch options, which contains Browserless-specific options and Chrome flags inside the args array. You can provide this as a base-64 JSON. | {} |
| token | The authorization token for API access. | none |
| timeout | Maximum session duration in milliseconds. The session will automatically close after this time to prevent overuse. | 60000 |
| headless | Runs the browser in headless mode. Set to false to enable headful mode (with a GUI). While the GUI isn't visible in cloud environments, headful mode may help bypass bot detection. Note: it uses more resources. | true |
| stealth | Enables stealth mode to reduce automation signals (similar to puppeteer-extra's stealth plugin). In BQL, stealth is always on by design and controlled via the humanlike option. In BaaS/REST, set to true to enable stealth techniques. | false (for BaaS/REST) |
| proxy | Routes browser traffic through a proxy. Only supports proxy=residential for Browserless's residential proxy pool. Omit to use the IP of the machine in the cloud running the container, meaning it's a fixed datacenter IP. | none |
| proxyCountry | Used with proxy=residential to specify the exit node's country. Accepts ISO 3166 country codes (e.g., us, gb, de). If omitted, a random location is chosen. | none |
| proxySticky | Used with proxy=residential to maintain the same proxy IP across a session (when possible). Useful for sites that expect consistent IP usage. | false |
| record | Enables session recording functionality for debugging and monitoring purposes. | false |
| humanlike | Simulates human-like behavior such as natural mouse movement, typing, and random delays. In the BQL IDE, this can be toggled in session settings. For direct BQL GraphQL calls, use humanlike: true in the launch payload. Recommended for strict bot detection scenarios. | false |
| blockAds | Enables the built-in ad blocker (powered by uBlock Origin). Helps speed up scripts and reduce noise by blocking ads and trackers. Especially useful for scraping to avoid popups and clutter. | false |
| blockConsentModals | Automatically blocks or dismisses cookie/GDPR consent banners. Available in BQL sessions and the /screenshot and /pdf REST APIs. In BQL, toggle it via the IDE or launch JSON. Useful for cleaner scraping by removing overlays. | false |
| slowMo | Adds delays between browser actions to slow down automation. Useful for debugging or bypassing rate limits. Value in milliseconds. | 0 |
| ignoreDefaultArgs | Controls which default Puppeteer/Playwright arguments to ignore when launching the browser. Can be a boolean or array of specific arguments to ignore. | false |
| acceptInsecureCerts | Accepts insecure certificates during navigation. Useful for testing sites with self-signed certificates or certificate issues. | false |

## API Reference​

For detailed API specifications and additional launch options, refer to the following API reference pages:

- Chrome BQL API: Complete API reference for Chrome BQL endpoints
- Chromium BQL API: Complete API reference for Chromium BQL endpoints

## Next Steps​

Now that you understand launch parameters and options, explore these key areas to maximize your BrowserQL automation capabilities:

[Getting Started with BQLLearn the basics of BrowserQL and how to write your first automation queries](https://docs.browserless.io/browserql/getting-started)
[Writing BQL QueriesMaster the BrowserQL language basics and learn how to write effective automation queries](https://docs.browserless.io/browserql/writing-bql/language-basics)
[Using the IDEExplore the built-in IDE features, live session preview, and development environment](https://docs.browserless.io/browserql/using-the-ide/ide-features)


# Maintaining Sessions with Reconnects

The Session-Reconnect features allow you to maintain continuity across multiple browser sessions or integrate with other automation tools. This section covers how to reconnect to an existing browser session, pass control between BrowserQL and external libraries, and create persistent workflows that can be accessed and controlled across different sessions or systems.

Similar to connecting a 3rd-party library, you can also reconnect back and execute more BrowserQL as well. BQL does this by generating a new unique URL to use for running more queries. You can take this URL, append your API-token to it, and run more query language.

Scraping websites with traditional tools like Puppeteer or Playwright can be inefficient due to repeated session restarts and unnecessary proxy usage. Reconnects maintains browser sessions, preserving cookies, cache, and session data across multiple requests, bringing the following benefits:

- Reduced proxy usage: Save up to 90% of proxy bandwidth.
- Improved efficiency: Avoid repetitive loading of static content.
- Lower detection risk: Maintain consistent session states to avoid bot detection mechanisms like CAPTCHAs.

## Implementing Reconnects with BrowserQL​

This guide will go through the following steps to maintain a sessions using Reconnects:

1. Initiate a session.
2. Scrape data using the reconnect URL.
3. Refresh your session URL regularly to maintain stability.

### Step 1: Initial Setup​

Start by initiating a session with BrowserQL. This first query opens the browser, navigates to your target URL, and provides a reconnect URL to reuse the same session.

API Token Required

The `browserQLEndpoint` returned by the reconnect mutation does not include your API token. You'll need to append `?token=YOUR_API_TOKEN_HERE` to the reconnect URL before using it for subsequent requests.

- Javascript
- Python
- Java
- C#

```
import fetch from 'node-fetch';const API_KEY = "YOUR_API_TOKEN_HERE";const BQL_ENDPOINT = `https://production-sfo.browserless.io/chromium/bql?token=${API_KEY}`;const sessionQuery = `mutation StartSession {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  reconnect(timeout: 60000) { # Keeps session open for 60 seconds    browserQLEndpoint  }}`;async function startSession() {  const response = await fetch(BQL_ENDPOINT, {    method: "POST",    headers: {      "Content-Type": "application/json",    },    body: JSON.stringify({ query: sessionQuery }),  });  const data = await response.json();  console.log("Reconnect URL:", data.data.reconnect.browserQLEndpoint);  return data.data.reconnect.browserQLEndpoint;}startSession();
```

```
import requestsAPI_KEY = "YOUR_API_TOKEN_HERE"BQL_ENDPOINT = f"https://production-sfo.browserless.io/chromium/bql?token={API_KEY}"session_query = """mutation StartSession {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  reconnect(timeout: 60000) {    browserQLEndpoint  }}"""def start_session():    headers = {        "Content-Type": "application/json",    }    payload = {"query": session_query}    response = requests.post(BQL_ENDPOINT, json=payload, headers=headers)    response.raise_for_status()    data = response.json()    endpoint = data['data']['reconnect']['browserQLEndpoint']    print("Reconnect URL:", endpoint)    return endpointstart_session()
```

```
import java.io.IOException;import java.net.URI;import java.net.http.HttpClient;import java.net.http.HttpRequest;import java.net.http.HttpResponse;import com.fasterxml.jackson.databind.JsonNode;import com.fasterxml.jackson.databind.ObjectMapper;public class BrowserlessSession {    private static final String API_KEY = "YOUR_API_TOKEN_HERE";    private static final String BQL_ENDPOINT = "https://production-sfo.browserless.io/chromium/bql?token=" + API_KEY;    private static final String SESSION_QUERY = """        mutation StartSession {          goto(url: "https://example.com", waitUntil: networkIdle) {            status          }          reconnect(timeout: 60000) {            browserQLEndpoint          }        }        """;    public static void main(String[] args) throws IOException, InterruptedException {        HttpClient client = HttpClient.newHttpClient();        String jsonPayload = "{\"query\": " + new ObjectMapper().writeValueAsString(SESSION_QUERY) + "}";        HttpRequest request = HttpRequest.newBuilder()            .uri(URI.create(BQL_ENDPOINT))            .header("Content-Type", "application/json")            .POST(HttpRequest.BodyPublishers.ofString(jsonPayload))            .build();        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());        ObjectMapper mapper = new ObjectMapper();        JsonNode root = mapper.readTree(response.body());        String endpoint = root.path("data")                              .path("reconnect")                              .path("browserQLEndpoint")                              .asText();        System.out.println("Reconnect URL: " + endpoint);    }}
```

```
using System;using System.Net.Http;using System.Text;using System.Text.Json;using System.Threading.Tasks;class Program{    private const string ApiKey = "YOUR_API_TOKEN_HERE";    private static readonly string BqlEndpoint = $"https://production-sfo.browserless.io/chromium/bql?token={ApiKey}";    private const string sessionQuery = @"    mutation StartSession {      goto(url: ""https://example.com"", waitUntil: networkIdle) {        status      }      reconnect(timeout: 60000) {        browserQLEndpoint      }    }";    static async Task Main()    {        using var client = new HttpClient();                var payload = new        {            query = sessionQuery        };        var content = new StringContent(JsonSerializer.Serialize(payload), Encoding.UTF8, "application/json");                var response = await client.PostAsync(BqlEndpoint, content);        response.EnsureSuccessStatusCode();        var responseBody = await response.Content.ReadAsStringAsync();        using var doc = JsonDocument.Parse(responseBody);        var endpoint = doc.RootElement.GetProperty("data")                                    .GetProperty("reconnect")                                    .GetProperty("browserQLEndpoint")                                    .GetString();        Console.WriteLine("Reconnect URL: " + endpoint);    }}
```

### Step 2: Using the Reconnect URL​

Use the reconnect URL provided by the initial session setup to make subsequent queries without starting a new browser instance. In this step, we're adding the API key to the `RECONNECT_BQL_ENDPOINT` since the reconnect URL doesn't include authentication by default.

- Javascript
- Python
- Java
- C#

```
const RECONNECT_BQL_ENDPOINT = "YOUR_RECONNECT_BQL_ENDPOINT" + "?token=YOUR_API_TOKEN_HERE";const scrapeQuery = `mutation FetchData {  text(selector: ".product-title") {    text  }}`;async function fetchData() {  const response = await fetch(RECONNECT_BQL_ENDPOINT, {    method: "POST",    headers: { "Content-Type": "application/json" },    body: JSON.stringify({ query: scrapeQuery }),  });  const data = await response.json();  console.log("Fetched Data:", data.data.text.text);}fetchData();
```

```
import requestsRECONNECT_BQL_ENDPOINT = "YOUR_RECONNECT_BQL_ENDPOINT" + "?token=YOUR_API_TOKEN_HERE"scrape_query = """mutation FetchData {  text(selector: ".product-title") {    text  }}"""def fetch_data():    headers = {"Content-Type": "application/json"}    response = requests.post(        RECONNECT_BQL_ENDPOINT,        json={"query": scrape_query},        headers=headers    )    response.raise_for_status()    data = response.json()    print("Fetched Data:", data['data']['text']['text'])fetch_data()
```

```
import java.io.IOException;import java.net.URI;import java.net.http.HttpClient;import java.net.http.HttpRequest;import java.net.http.HttpResponse;import com.fasterxml.jackson.databind.JsonNode;import com.fasterxml.jackson.databind.ObjectMapper;public class FetchData {        private static final String RECONNECT_BQL_ENDPOINT = "YOUR_RECONNECT_BQL_ENDPOINT" + "?token=YOUR_API_TOKEN_HERE";    private static final String SCRAPE_QUERY = """        mutation FetchData {          text(selector: ".product-title") {            text          }        }        """;    public static void main(String[] args) throws IOException, InterruptedException {        HttpClient client = HttpClient.newHttpClient();        String jsonPayload = "{\"query\": " + new ObjectMapper().writeValueAsString(SCRAPE_QUERY) + "}";        HttpRequest request = HttpRequest.newBuilder()            .uri(URI.create(RECONNECT_BQL_ENDPOINT))            .header("Content-Type", "application/json")            .POST(HttpRequest.BodyPublishers.ofString(jsonPayload))            .build();        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());        ObjectMapper mapper = new ObjectMapper();        JsonNode root = mapper.readTree(response.body());        String fetchedText = root.path("data").path("text").path("text").asText();        System.out.println("Fetched Data: " + fetchedText);    }}
```

```
using System;using System.Net.Http;using System.Text;using System.Text.Json;using System.Threading.Tasks;class Program{    private const string ReconnectBqlEndpoint = "YOUR_RECONNECT_BQL_ENDPOINT" + "?token=YOUR_API_TOKEN_HERE";    private const string scrapeQuery = @"    mutation FetchData {      text(selector: "".product-title"") {        text      }    }";    static async Task Main()    {        using var client = new HttpClient();                var payload = new        {            query = scrapeQuery        };        var content = new StringContent(JsonSerializer.Serialize(payload), Encoding.UTF8, "application/json");                var response = await client.PostAsync(ReconnectBqlEndpoint, content);        response.EnsureSuccessStatusCode();        var responseBody = await response.Content.ReadAsStringAsync();        using var doc = JsonDocument.Parse(responseBody);        var fetchedText = doc.RootElement.GetProperty("data")                                        .GetProperty("text")                                        .GetProperty("text")                                        .GetString();        Console.WriteLine("Fetched Data: " + fetchedText);    }}
```

### Step 3: Refreshing Your Session​

To avoid instability, refresh the reconnect endpoint periodically.

- Javascript
- Python
- Java
- C#

```
const refreshQuery = `mutation RefreshSession {  reconnect(timeout: 60000) { # Extends session timeout    browserQLEndpoint  }}`;async function refreshSession() {  const response = await fetch(BQL_ENDPOINT, {    method: "POST",    headers: {      "Content-Type": "application/json",    },    body: JSON.stringify({ query: refreshQuery }),  });  const data = await response.json();  console.log("New Reconnect URL:", data.data.reconnect.browserQLEndpoint);  return data.data.reconnect.browserQLEndpoint;}
```

```
import requestsAPI_KEY = "YOUR_API_TOKEN_HERE"BQL_ENDPOINT = "https://production-sfo.browserless.io/chromium/bql"refresh_query = """mutation RefreshSession {  reconnect(timeout: 60000) {    browserQLEndpoint  }}"""def refresh_session():    headers = {        "Content-Type": "application/json"    }    response = requests.post(        f"{BQL_ENDPOINT}?token={API_KEY}",        json={"query": refresh_query},        headers=headers    )    response.raise_for_status()    data = response.json()    endpoint = data['data']['reconnect']['browserQLEndpoint']    print("New Reconnect URL:", endpoint)    return endpointrefresh_session()
```

```
import java.io.IOException;import java.net.URI;import java.net.http.HttpClient;import java.net.http.HttpRequest;import java.net.http.HttpResponse;import com.fasterxml.jackson.databind.JsonNode;import com.fasterxml.jackson.databind.ObjectMapper;public class RefreshSession {    private static final String API_KEY = "YOUR_API_TOKEN_HERE";    private static final String BQL_ENDPOINT = "https://production-sfo.browserless.io/chromium/bql?token=" + API_KEY;    private static final String REFRESH_QUERY = """        mutation RefreshSession {          reconnect(timeout: 60000) {            browserQLEndpoint          }        }        """;    public static void main(String[] args) throws IOException, InterruptedException {        HttpClient client = HttpClient.newHttpClient();        String jsonPayload = "{\"query\": " + new ObjectMapper().writeValueAsString(REFRESH_QUERY) + "}";        HttpRequest request = HttpRequest.newBuilder()            .uri(URI.create(BQL_ENDPOINT))            .header("Content-Type", "application/json")            .POST(HttpRequest.BodyPublishers.ofString(jsonPayload))            .build();        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());        ObjectMapper mapper = new ObjectMapper();        JsonNode root = mapper.readTree(response.body());        String endpoint = root.path("data").path("reconnect").path("browserQLEndpoint").asText();        System.out.println("New Reconnect URL: " + endpoint);    }}
```

```
using System;using System.Net.Http;using System.Text;using System.Text.Json;using System.Threading.Tasks;class Program{    private const string ApiKey = "YOUR_API_TOKEN_HERE";    private static readonly string BqlEndpoint = $"https://production-sfo.browserless.io/chromium/bql?token={ApiKey}";    private const string refreshQuery = @"    mutation RefreshSession {      reconnect(timeout: 60000) {        browserQLEndpoint      }    }";    static async Task Main()    {        using var client = new HttpClient();        var payload = new        {            query = refreshQuery        };        var content = new StringContent(JsonSerializer.Serialize(payload), Encoding.UTF8, "application/json");        var response = await client.PostAsync(BqlEndpoint, content);        response.EnsureSuccessStatusCode();        var responseBody = await response.Content.ReadAsStringAsync();        using var doc = JsonDocument.Parse(responseBody);        var endpoint = doc.RootElement.GetProperty("data")                                      .GetProperty("reconnect")                                      .GetProperty("browserQLEndpoint")                                      .GetString();        Console.WriteLine("New Reconnect URL: " + endpoint);    }}
```

### Full Example Code​

Here's a complete example demonstrating all steps together:

- Javascript
- Python
- Java
- C#

```
import fetch from 'node-fetch';const API_KEY = "YOUR_API_TOKEN_HERE";const BQL_ENDPOINT = `https://production-sfo.browserless.io/chromium/bql?token=${API_KEY}`;const sessionQuery = `mutation StartSession {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  reconnect(timeout: 60000) { # Keeps session open for 60 seconds    browserQLEndpoint  }}`;async function startSession() {  const response = await fetch(BQL_ENDPOINT, {    method: "POST",    headers: {      "Content-Type": "application/json",    },    body: JSON.stringify({ query: sessionQuery }),  });  const data = await response.json();  console.log("Reconnect URL:", data.data.reconnect.browserQLEndpoint);  return data.data.reconnect.browserQLEndpoint;}async function fetchData(reconnectUrl) {  const scrapeQuery = `mutation FetchData {  text(selector: ".product-title") {    text  }}`;  const reconnectUrlWithToken = reconnectUrl + "?token=" + API_KEY;  const response = await fetch(reconnectUrlWithToken, {    method: "POST",    headers: { "Content-Type": "application/json" },    body: JSON.stringify({ query: scrapeQuery }),  });  const data = await response.json();  console.log("Fetched Data:", data.data.text.text);}async function refreshSession() {  const refreshQuery = `mutation RefreshSession {  reconnect(timeout: 60000) { # Extends session timeout    browserQLEndpoint  }}`;  const response = await fetch(BQL_ENDPOINT, {    method: "POST",    headers: {      "Content-Type": "application/json",    },    body: JSON.stringify({ query: refreshQuery }),  });  const data = await response.json();  console.log("New Reconnect URL:", data.data.reconnect.browserQLEndpoint);  return data.data.reconnect.browserQLEndpoint;}(async () => {  let reconnectUrl = await startSession();  let pagesScraped = 0;  const PAGE_LIMIT = 20;  for (let i = 0; i < 100; i++) {    if (pagesScraped >= PAGE_LIMIT) {      reconnectUrl = await refreshSession();      pagesScraped = 0;    }    const data = await fetchData(reconnectUrl);    console.log(`Scraped Page ${i + 1}:`, data);    pagesScraped++;  }})();
```

```
import requestsAPI_KEY = "YOUR_API_TOKEN_HERE"BQL_ENDPOINT = "https://production-sfo.browserless.io/chromium/bql"session_query = """mutation StartSession {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  reconnect(timeout: 60000) {    browserQLEndpoint  }}"""refresh_query = """mutation RefreshSession {  reconnect(timeout: 60000) {    browserQLEndpoint  }}"""scrape_query = """mutation FetchData {  text(selector: ".product-title") {    text  }}"""def start_session():    headers = {        "Content-Type": "application/json"    }    response = requests.post(f"{BQL_ENDPOINT}?token={API_KEY}", json={"query": session_query}, headers=headers)    response.raise_for_status()    endpoint = response.json()['data']['reconnect']['browserQLEndpoint']    print("Reconnect URL:", endpoint)    return endpointdef refresh_session():    headers = {        "Content-Type": "application/json"    }    response = requests.post(f"{BQL_ENDPOINT}?token={API_KEY}", json={"query": refresh_query}, headers=headers)    response.raise_for_status()    endpoint = response.json()['data']['reconnect']['browserQLEndpoint']    print("New Reconnect URL:", endpoint)    return endpointdef fetch_data(reconnect_url):    headers = {"Content-Type": "application/json"}    reconnect_url_with_token = f"{reconnect_url}?token={API_KEY}"    response = requests.post(reconnect_url_with_token, json={"query": scrape_query}, headers=headers)    response.raise_for_status()    data = response.json()['data']['text']['text']    print("Fetched Data:", data)    return datadef main():    reconnect_url = start_session()    pages_scraped = 0    PAGE_LIMIT = 20    for i in range(100):        if pages_scraped >= PAGE_LIMIT:            reconnect_url = refresh_session()            pages_scraped = 0        data = fetch_data(reconnect_url)        print(f"Scraped Page {i + 1}:", data)        pages_scraped += 1if __name__ == "__main__":    main()
```

```
import java.net.URI;import java.net.http.HttpClient;import java.net.http.HttpRequest;import java.net.http.HttpResponse;import com.fasterxml.jackson.databind.JsonNode;import com.fasterxml.jackson.databind.ObjectMapper;public class BrowserlessScraper {    static final String API_KEY = "YOUR_API_TOKEN_HERE";    static final String BQL_ENDPOINT = "https://production-sfo.browserless.io/chromium/bql";    static final ObjectMapper mapper = new ObjectMapper();    static final HttpClient client = HttpClient.newHttpClient();    static String executeQuery(String url, String query, boolean auth) throws Exception {        String payload = mapper.writeValueAsString(new Query(query));        var requestBuilder = HttpRequest.newBuilder()            .uri(URI.create(url))            .header("Content-Type", "application/json")            .POST(HttpRequest.BodyPublishers.ofString(payload));        var response = client.send(requestBuilder.build(), HttpResponse.BodyHandlers.ofString());        return response.body();    }    static String startSession() throws Exception {        String sessionQuery = """        mutation StartSession {          goto(url: "https://example.com", waitUntil: networkIdle) { status }          reconnect(timeout: 60000) { browserQLEndpoint }        }""";        String json = executeQuery(BQL_ENDPOINT, sessionQuery, true);        return mapper.readTree(json).path("data").path("reconnect").path("browserQLEndpoint").asText();    }    static String refreshSession() throws Exception {        String refreshQuery = """        mutation RefreshSession {          reconnect(timeout: 60000) { browserQLEndpoint }        }""";        String json = executeQuery(BQL_ENDPOINT, refreshQuery, true);        return mapper.readTree(json).path("data").path("reconnect").path("browserQLEndpoint").asText();    }    static String fetchData(String reconnectUrl) throws Exception {        String scrapeQuery = """        mutation FetchData {          text(selector: ".product-title") { text }        }""";        String reconnectUrlWithToken = reconnectUrl + "?token=" + API_KEY;        String json = executeQuery(reconnectUrlWithToken, scrapeQuery, false);        return mapper.readTree(json).path("data").path("text").path("text").asText();    }    public static void main(String[] args) throws Exception {        String reconnectUrl = startSession();        System.out.println("Reconnect URL: " + reconnectUrl);        int pagesScraped = 0, PAGE_LIMIT = 20;        for (int i = 0; i < 100; i++) {            if (pagesScraped >= PAGE_LIMIT) {                reconnectUrl = refreshSession();                System.out.println("New Reconnect URL: " + reconnectUrl);                pagesScraped = 0;            }            String data = fetchData(reconnectUrl);            System.out.printf("Scraped Page %d: %s%n", i + 1, data);            pagesScraped++;        }    }    static class Query {        public String query;        Query(String q) { this.query = q; }    }}
```

```
using System;using System.Net.Http;using System.Text;using System.Text.Json;using System.Threading.Tasks;class Program{    const string ApiKey = "YOUR_API_TOKEN_HERE";    const string BqlEndpoint = "https://production-sfo.browserless.io/chromium/bql";    const string sessionQuery = @"    mutation StartSession {      goto(url: ""https://example.com"", waitUntil: networkIdle) { status }      reconnect(timeout: 60000) { browserQLEndpoint }    }";    const string refreshQuery = @"    mutation RefreshSession {      reconnect(timeout: 60000) { browserQLEndpoint }    }";    const string scrapeQuery = @"    mutation FetchData {      text(selector: "".product-title"") { text }    }";    static async Task<string> ExecuteQuery(string url, string query, bool auth)    {        using var client = new HttpClient();        var content = new StringContent(JsonSerializer.Serialize(new { query }), Encoding.UTF8, "application/json");        var response = await client.PostAsync(url, content);        response.EnsureSuccessStatusCode();        var json = await response.Content.ReadAsStringAsync();        return json;    }    static async Task Main()    {        var jsonDoc = JsonDocument.Parse(await ExecuteQuery(BqlEndpoint, sessionQuery, true));        var reconnectUrl = jsonDoc.RootElement.GetProperty("data").GetProperty("reconnect").GetProperty("browserQLEndpoint").GetString();        Console.WriteLine("Reconnect URL: " + reconnectUrl);        int pagesScraped = 0, PAGE_LIMIT = 20;        for (int i = 0; i < 100; i++)        {            if (pagesScraped >= PAGE_LIMIT)            {                jsonDoc = JsonDocument.Parse(await ExecuteQuery(BqlEndpoint, refreshQuery, true));                reconnectUrl = jsonDoc.RootElement.GetProperty("data").GetProperty("reconnect").GetProperty("browserQLEndpoint").GetString();                Console.WriteLine("New Reconnect URL: " + reconnectUrl);                pagesScraped = 0;            }            var reconnectUrlWithToken = reconnectUrl + "?token=" + ApiKey;            jsonDoc = JsonDocument.Parse(await ExecuteQuery(reconnectUrlWithToken, scrapeQuery, false));            var data = jsonDoc.RootElement.GetProperty("data").GetProperty("text").GetProperty("text").GetString();            Console.WriteLine($"Scraped Page {i + 1}: {data}");            pagesScraped++;        }    }}
```

## Improving Efficiency with BrowserQL's Reject API​

BrowserQL also lets you reject unnecessary requests (e.g., images, media) to optimize resource usage:

```
mutation OptimizeSession {  setRequestInterception(enabled: true)  reject(patterns: ["*.png", "*.jpg", "*.mp4"])}
```

Use this to further streamline your scraping tasks.

## Common Issues​

### CAPTCHA Challenges​

If you encounter CAPTCHAs, ensure your session maintains human-like interaction patterns by reducing request rates and maintaining stable sessions.

### Session Timeouts​

Session reconnect functionality and timeout limits vary by subscription plan:

#### Plan Limitations​

- Free Plan: Maximum reconnect timeout of 10 seconds (10,000ms)
- Prototyping and Starter Plans: Maximum reconnect timeout of 1 minute (60,000ms)
- Scale Plan: Maximum reconnect timeout of 5 minutes (300,000ms)

Reconnect Timeout vs Session Timeout

The reconnect timeout is **different** from your overall session timeout. Your BrowserQL sessions can run for 15-60 minutes depending on your plan, but the reconnect timeout only controls how long the browser waits for reconnection after you disconnect.

#### Setting Reconnect Timeout​

The `timeout` argument in the reconnect mutation specifies the maximum time (in milliseconds) the browser will remain open waiting for a reconnection **after you disconnect**. If no reconnection occurs within this timeframe, that specific browser instance will be automatically closed, but you can always start a new session.

```
reconnect(timeout: 60000) # 1 minute timeout for Prototyping/Starter plans
```

```
reconnect(timeout: 300000) # 5 minute timeout for Scale plan
```

Set appropriate timeout values to ensure sessions remain active without resource leaks while staying within your plan's limits.



# Puppeteer & Playwright

If you're already using Puppeteer or Playwright working with WebSockets, you can still mix-and-match BrowserQL in your scripts. This is perfect for getting past a nasty bot blockage and then connecting your existing scripts back.

Reconnecting with More BQL

You can also run *more* BrowserQL at a later time by doing the same process this guide will teach you. Refer to the [Reconnecting with More BQL](https://docs.browserless.io/browserql/session-management/reconnect-to-browserless) guide for more details.

## Using Reconnect​

With BQL, you'll navigate to the desired page, do the actions you require, like verifying or solving a captcha, and finally, use the [reconnect](https://docs.browserless.io/bql-schema/operations/mutations/reconnect) mutation to retrieve a websocket endpoint. This endpoint will be your entry point when starting your Puppeteer or Playwright connection.

Using the [https://example.com/](https://example.com/) page, you can run the following BrowserQL query then ask for a connection back:

Reconnect Timeout

The `reconnect` mutation has a `timeout` argument, which is a limit (in milliseconds) for how long the browser should be available before it gets shutdown when nothing connects to it. If a connection were to happen after this time, a semantic `404` is returned back. When a connection happens, this will clear the timer and the session can continue past this limit.

```
mutation Reconnect {  goto(url: "https://example.com/", waitUntil: networkIdle) {    status  }  reconnect (timeout: 30000) {    browserWSEndpoint  }}
```

## Connecting with Libraries​

Now, you need to integrate the BQL query above into your library code. You can use BrowserQL Editor's Export Query as Code to translate any query into multiple code languages, like Javascript.

- Learn how to Export Query as Code.
- See the Available programming languages.

With the query turned into your preferred code language, you can integrate the code into your script. The examples below use the `browserWSEndpoint` to make a connection with your chosen library and take a screenshot of the webpage:

- Puppeteer
- Playwright (JavaScript)
- Playwright (Python)
- Playwright (Java)
- Playwright (C#)

```
import puppeteer from 'puppeteer-core';const url = 'https://example.com';const token = 'YOUR_API_TOKEN_HERE';const timeout = 5 * 60 * 1000;const queryParams = new URLSearchParams({  timeout,  token,}).toString();const query = `  mutation Reconnect($url: String!) {    goto(url: $url, waitUntil: networkIdle) {      status    }    reconnect(timeout: 30000) {      browserWSEndpoint    }  }`;const variables = { url };const endpoint = `https://production-sfo.browserless.io/chromium/bql?${queryParams}`;const options = {  method: 'POST',  headers: {    'content-type': 'application/json'  },  body: JSON.stringify({    query,    variables,  }),};try {  console.log(`Running BQL Query: ${url}`);  const response = await fetch(endpoint, options);  if (!response.ok) {    throw new Error(`Got non-ok response:\n` + (await response.text()));  }  const { data } = await response.json();  const browserWSEndpoint = data.reconnect.browserWSEndpoint  console.log(`Got OK response! Connecting puppeteer to ${browserWSEndpoint}`);  const browser = await puppeteer.connect({    browserWSEndpoint,  });  console.log(`Connected to ${await browser.version()}`);  const pages = await browser.pages();  const page = pages.find((p) => p.url().includes(url));  await page.screenshot({ fullPage: true, path: 'temp.png' });  await browser.close();} catch (error) {  console.error(error);}
```

```
import playwright from 'playwright-core';const url = 'https://example.com';const token = 'YOUR_API_TOKEN_HERE';const timeout = 5 * 60 * 1000;const queryParams = new URLSearchParams({  timeout,  token,}).toString();const query = `  mutation Reconnect($url: String!) {    goto(url: $url, waitUntil: networkIdle) {      status    }    reconnect(timeout: 30000) {      browserWSEndpoint    }  }`;const variables = { url };const endpoint =  `https://production-sfo.browserless.io/playwright./bql?${queryParams}`;const options = {  method: 'POST',  headers: {    'content-type': 'application/json',  },  body: JSON.stringify({    query,    variables,  }),};(async () => {  try {    console.log(`Running BQL Query: ${url}`);    const response = await fetch(endpoint, options);    if (!response.ok) {      throw new Error(`Got non-ok response:\n` + (await response.text()));    }    const { data } = await response.json();    const browserWSEndpoint = data.reconnect.browserWSEndpoint;    console.log(`Got OK response! Connecting Playwright to ${browserWSEndpoint}`);    const browser = await playwright.chromium.connectOverCDP(browserWSEndpoint);    const context = browser.contexts()[0];    const page = context.pages().find((p) => p.url().includes(url));    if (!page) {      throw new Error(`Could not find a page matching ${url}`);    }    await page.screenshot({ fullPage: true, path: 'temp.png' });    await browser.close();  } catch (error) {    console.error(error);  }})();
```

```
import requestsfrom playwright.sync_api import sync_playwrighturl = "https://example.com"token = "YOUR_API_TOKEN_HERE"timeout = 5 * 60 * 1000query_params = f"token={token}&timeout={timeout}"endpoint = f"https://production-sfo.browserless.io/chromium/bql?{query_params}"query = """  mutation Reconnect($url: String!) {    goto(url: $url, waitUntil: networkIdle) {      status    }    reconnect(timeout: 30000) {      browserWSEndpoint    }  }"""variables = {"url": url}headers = {"content-type": "application/json"}body = {"query": query, "variables": variables}try:    print(f"Running BQL Query: {url}")    response = requests.post(endpoint, json=body, headers=headers)    if response.status_code != 200:        raise Exception(f"Got non-ok response:\n{response.text}")    data = response.json().get("data")    browser_ws_endpoint = data["reconnect"]["browserWSEndpoint"]    print(f"Got OK response! Connecting Playwright to {browser_ws_endpoint}")    with sync_playwright() as playwright:        browser = playwright.chromium.connect_over_cdp(browser_ws_endpoint)        context = browser.contexts[0]        page = next((p for p in context.pages if url in p.url), None)        if not page:            raise Exception(f"Could not find a page matching {url}")        page.screenshot(path="temp.png", full_page=True)        browser.close()except Exception as e:    print(f"Error: {e}")
```

```
package com.example;import com.microsoft.playwright.*;import com.google.gson.*;import java.net.http.*;import java.net.URI;import java.util.*;public class PlaywrightBQL {    public static void main(String[] args) {        String url = "https://example.com";        String token = "YOUR_API_TOKEN_HERE";        int timeout = 5 * 60 * 1000;        String queryParams = String.format("token=%s&timeout=%d", token, timeout);        String endpoint = String.format("https://production-sfo.browserless.io/chromium/bql?%s", queryParams);        String query = """                mutation Reconnect($url: String!) {                  goto(url: $url, waitUntil: networkIdle) {                    status                  }                  reconnect(timeout: 30000) {                    browserWSEndpoint                  }                }                """;        JsonObject variables = new JsonObject();        variables.addProperty("url", url);        JsonObject body = new JsonObject();        body.addProperty("query", query);        body.add("variables", variables);        try {            // Send GraphQL request            HttpClient client = HttpClient.newHttpClient();            HttpRequest request = HttpRequest.newBuilder()                    .uri(URI.create(endpoint))                    .header("Content-Type", "application/json")                    .POST(HttpRequest.BodyPublishers.ofString(body.toString()))                    .build();            HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());            if (response.statusCode() != 200) {                throw new RuntimeException("Failed request: " + response.body());            }            // Parse response            JsonObject data = JsonParser.parseString(response.body()).getAsJsonObject().getAsJsonObject("data");            String browserWSEndpoint = data.getAsJsonObject("reconnect").get("browserWSEndpoint").getAsString();            System.out.println("Connecting Playwright to " + browserWSEndpoint);            try (Playwright playwright = Playwright.create()) {                Browser browser = playwright.chromium().connectOverCDP(browserWSEndpoint);                BrowserContext context = browser.contexts().get(0);                Page page = context.pages().stream()                        .filter(p -> p.url().contains(url))                        .findFirst()                        .orElseThrow(() -> new RuntimeException("Page not found"));                page.screenshot(new Page.ScreenshotOptions().setPath("temp.png").setFullPage(true));                browser.close();            }        } catch (Exception e) {            e.printStackTrace();        }    }}
```

```
using System;using System.Net.Http;using System.Text;using System.Text.Json;using System.Text.Json.Nodes;using Microsoft.Playwright;class Program{    static async System.Threading.Tasks.Task Main(string[] args)    {        string url = "https://example.com";        string token = "YOUR_API_TOKEN_HERE";        int timeout = 5 * 60 * 1000;        string queryParams = $"token={token}&timeout={timeout}";        string endpoint = $"https://production-sfo.browserless.io/chromium/bql?{queryParams}";        string query = @"        mutation Reconnect($url: String!) {          goto(url: $url, waitUntil: networkIdle) {            status          }          reconnect(timeout: 30000) {            browserWSEndpoint          }        }";        var body = new        {            query = query,            variables = new { url }        };        try        {            // Send GraphQL request            using var client = new HttpClient();            var requestContent = new StringContent(JsonSerializer.Serialize(body), Encoding.UTF8, "application/json");            var response = await client.PostAsync(endpoint, requestContent);            if (!response.IsSuccessStatusCode)            {                throw new Exception($"Request failed: {await response.Content.ReadAsStringAsync()}");            }            var jsonResponse = JsonNode.Parse(await response.Content.ReadAsStringAsync());            string browserWSEndpoint = jsonResponse["data"]["reconnect"]["browserWSEndpoint"].ToString();            Console.WriteLine($"Connecting Playwright to {browserWSEndpoint}");            // Connect to Playwright            using var playwright = await Playwright.CreateAsync();            var browser = await playwright.Chromium.ConnectOverCDPAsync(browserWSEndpoint);            var context = browser.Contexts[0];            var page = context.Pages.Find(p => p.Url.Contains(url)) ?? throw new Exception("Page not found");            // Take screenshot            await page.ScreenshotAsync(new PageScreenshotOptions { Path = "temp.png", FullPage = true });            await browser.CloseAsync();        }        catch (Exception ex)        {            Console.WriteLine($"Error: {ex.Message}");        }    }}
```



# Persisting State

The Session API provides explicit programmatic control over browser session lifecycle while enabling BQL (BrowserQL) query execution against persistent sessions. This approach is ideal for advanced automation workflows that require maintaining browser state across multiple script runs, user authentication persistence, and precise session management.

Stealth Sessions Required

BQL functionality is only available for stealth sessions. When creating a session, you must set `stealth: true` to receive the `browserQL` property in the response.

## How Session API with BQL Works​

When you create a stealth session through the Session API, Browserless returns a `browserQL` property containing a fully-qualified URL for running BQL queries against that specific session. This enables you to:

- Maintain browser state including cookies, localStorage, sessionStorage, and navigation state
- Apply session properties like proxy settings, stealth mode, and other configurations to all BQL queries
- Disconnect and reconnect to resume automation from the exact same point
- Manage session lifecycle programmatically with explicit creation and deletion

## Creating a Session with BQL Support​

- JavaScript
- Python
- cURL

```
const sessionConfig = {  ttl: 300000, // 5 minutes  stealth: true, // Required for BQL support  browser: 'chromium',  proxy: {    type: 'residential',    country: 'us',    sticky: true  }};const response = await fetch(  'https://production-sfo.browserless.io/session?token=YOUR_API_TOKEN_HERE',  {    method: 'POST',    headers: { 'Content-Type': 'application/json' },    body: JSON.stringify(sessionConfig),  });if (!response.ok) {  throw new Error(`Failed to create session: ${response.status}`);}const session = await response.json();console.log('Session created:', session.id);console.log('BrowserQL URL:', session.browserQL);console.log('WebSocket URL:', session.connect);console.log('Stop URL:', session.stop);
```

```
import requestssession_config = {    'ttl': 300000,  # 5 minutes    'stealth': True,  # Required for BQL support    'browser': 'chromium',    'proxy': {        'type': 'residential',        'country': 'us',        'sticky': True    }}response = requests.post(    'https://production-sfo.browserless.io/session',    params={'token': 'YOUR_API_TOKEN_HERE'},    json=session_config)response.raise_for_status()session = response.json()print(f'Session created: {session["id"]}')print(f'BrowserQL URL: {session["browserQL"]}')print(f'WebSocket URL: {session["connect"]}')print(f'Stop URL: {session["stop"]}')
```

```
curl -X POST "https://production-sfo.browserless.io/session?token=YOUR_API_TOKEN_HERE" \  -H "Content-Type: application/json" \  -d '{    "ttl": 300000,    "stealth": true,    "browser": "chromium",    "proxy": {      "type": "residential",      "country": "us",      "sticky": true    }  }'
```

### Session Response Schema​

The session creation response includes the following properties:

| Property | Type | Description |
| --- | --- | --- |
| id | string | Unique session identifier |
| connect | string | WebSocket URL for CDP-based libraries (Puppeteer, Playwright) |
| browserQL | string | Fully-qualified URL for running BQL queries (stealth sessions only) |
| stop | string | URL for session termination via DELETE request |
| ttl | number | Session time-to-live in milliseconds |

## Running BQL Queries Against Sessions​

Once you have a session with BQL support, use the `browserQL` URL to execute GraphQL mutations. All session properties (proxy settings, stealth mode, etc.) automatically apply to BQL queries.

- JavaScript
- Python

```
// Using the browserQL URL from session creationconst browserQLURL = session.browserQL;const firstQuery = `  mutation FirstQuery {    goto(url: "https://example.com", waitUntil: networkIdle) {      status    }    title {      title    }    evaluate(content: "localStorage.setItem('testData', 'persistent-value')") {      value    }  }`;const firstResponse = await fetch(browserQLURL, {  method: 'POST',  headers: { 'Content-Type': 'application/json' },  body: JSON.stringify({ query: firstQuery })});const firstResult = await firstResponse.json();console.log('First query result:', firstResult.data);
```

```
# Using the browserQL URL from session creationbrowserql_url = session['browserQL']first_query = """mutation FirstQuery {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  title {    title  }  evaluate(content: "localStorage.setItem('testData', 'persistent-value')") {    value  }}"""first_response = requests.post(    browserql_url,    json={'query': first_query})first_result = first_response.json()print('First query result:', first_result['data'])
```

## Session State Persistence and Reconnection​

One of the key benefits of Session API with BQL is the ability to disconnect and reconnect while maintaining all browser state. This includes localStorage, cookies, navigation state, and any other browser data.

- JavaScript
- Python

```
// Complete example showing session creation, usage, and reconnectionconst sessionResponse = await fetch('https://production-sfo.browserless.io/session?token=YOUR_API_TOKEN_HERE', {  method: 'POST',  headers: {     'Content-Type': 'application/json'  },  body: JSON.stringify({    ttl: 300000, // 5 minutes    stealth: true,    browser: 'chromium'  })});const session = await sessionResponse.json();console.log('Session created');console.log('Session ID:', session.id);console.log('BrowserQL URL:', session.browserQL);// Wait for session to be readyconsole.log('Waiting for session to be ready...');await new Promise(resolve => setTimeout(resolve, 2000));console.log('Setting localStorage...');const firstQuery = `  mutation FirstQuery {    goto(url: "https://example.com", waitUntil: networkIdle) {      status    }    title {      title    }    evaluate(content: "localStorage.setItem('testData', 'persistent-value'); return localStorage.getItem('testData');") {      value    }  }`;console.log('Making first BrowserQL query...');const firstResponse = await fetch(session.browserQL, {  method: 'POST',  headers: {     'Content-Type': 'application/json'  },  body: JSON.stringify({ query: firstQuery })});const firstResult = await firstResponse.json();console.log('First query result:', firstResult.data);// Wait before next queryawait new Promise(resolve => setTimeout(resolve, 2000));// Check if localStorage persistsconsole.log('Checking if localStorage persists...');const checkQuery = `  mutation CheckQuery {    goto(url: "https://example.com", waitUntil: networkIdle) {      status    }    evaluate(content: "localStorage.getItem('testData') || 'no-data-found'") {      value    }    url {      url    }    title {      title    }  }`;console.log('Making check BrowserQL query...');const checkResponse = await fetch(session.browserQL, {  method: 'POST',  headers: {     'Content-Type': 'application/json'  },  body: JSON.stringify({ query: checkQuery })});const checkResult = await checkResponse.json();console.log('Check Query Result:');console.log('Raw response:', JSON.stringify(checkResult, null, 2));console.log('localStorage value:', checkResult.data?.evaluate?.value);console.log('Current URL:', checkResult.data?.url?.url);console.log('Page title:', checkResult.data?.title?.title);console.log('Cleaning up...');await new Promise(resolve => setTimeout(resolve, 1000));const deleteResponse = await fetch(session.stop, {   method: 'DELETE'});if (deleteResponse.ok) {  const deleteResult = await deleteResponse.json();  console.log('Session deleted successfully:', deleteResult.message);} else {  console.log('Session deletion failed:', deleteResponse.status);}const checkValue = checkResult.data?.evaluate?.value;console.log('Final localStorage check:', checkValue);
```

```
import requestsimport time# Create sessionsession_response = requests.post(    'https://production-sfo.browserless.io/session',    params={'token': 'YOUR_API_TOKEN_HERE'},    json={        'ttl': 300000,  # 5 minutes        'stealth': True,        'browser': 'chromium'    })session = session_response.json()print('Session created')print(f'Session ID: {session["id"]}')print(f'BrowserQL URL: {session["browserQL"]}')# Wait for session to be readyprint('Waiting for session to be ready...')time.sleep(2)print('Setting localStorage...')first_query = """mutation FirstQuery {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  title {    title  }  evaluate(content: "localStorage.setItem('testData', 'persistent-value'); return localStorage.getItem('testData');") {    value  }}"""print('Making first BrowserQL query...')first_response = requests.post(    session['browserQL'],    json={'query': first_query})first_result = first_response.json()print('First query result:', first_result['data'])# Wait before next querytime.sleep(2)# Check if localStorage persistsprint('Checking if localStorage persists...')check_query = """mutation CheckQuery {  goto(url: "https://example.com", waitUntil: networkIdle) {    status  }  evaluate(content: "localStorage.getItem('testData') || 'no-data-found'") {    value  }  url {    url  }  title {    title  }}"""print('Making check BrowserQL query...')check_response = requests.post(    session['browserQL'],    json={'query': check_query})check_result = check_response.json()print('Check Query Result:')print('Raw response:', check_result)print(f'localStorage value: {check_result["data"]["evaluate"]["value"]}')print(f'Current URL: {check_result["data"]["url"]["url"]}')print(f'Page title: {check_result["data"]["title"]["title"]}')print('Cleaning up...')time.sleep(1)delete_response = requests.delete(session['stop'])if delete_response.ok:    delete_result = delete_response.json()    print(f'Session deleted successfully: {delete_result["message"]}')else:    print(f'Session deletion failed: {delete_response.status_code}')check_value = check_result['data']['evaluate']['value']print(f'Final localStorage check: {check_value}')
```

## Session Configuration Options​

All session configuration options apply to both WebSocket connections and BQL queries:

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| ttl | number | 300000 | Time-to-live in milliseconds (max varies by plan) |
| stealth | boolean | false | Required for BQL support - enables stealth mode |
| headless | boolean | true | Run browser in headless mode |
| browser | string | 'chromium' | Browser type ('chromium' or 'chrome') |
| blockAds | boolean | false | Enable ad-blocking |
| args | string[] | [] | Additional Chrome launch arguments |
| proxy | object | null | Proxy configuration (applies to all BQL queries) |

### Proxy Configuration​

When proxy settings are configured for a session, they automatically apply to all BQL queries executed against that session:

```
const sessionWithProxy = {  ttl: 300000,  stealth: true,  proxy: {    type: 'residential',    country: 'us',    state: 'california',    city: 'san-francisco',    sticky: true  }};// All BQL queries will use the configured proxy settings
```

## Session Management​

### Checking Session Status​

You can verify session status by making a simple BQL query:

```
const statusQuery = `  mutation CheckStatus {    url {      url    }  }`;const response = await fetch(session.browserQL, {  method: 'POST',  headers: { 'Content-Type': 'application/json' },  body: JSON.stringify({ query: statusQuery })});if (response.ok) {  console.log('Session is active');} else {  console.log('Session may have expired');}
```

### Terminating Sessions​

Sessions automatically expire after their TTL, but you can manually terminate them:

```
// Using the stop URL from session creationconst stopResponse = await fetch(session.stop, {  method: 'DELETE'});if (stopResponse.ok) {  console.log('Session terminated successfully');}
```

## Comparison with BQL Reconnect​

The Session API approach differs from the standard BQL `reconnect` mutation:

| Feature | Session API + BQL | BQL Reconnect |
| --- | --- | --- |
| Session Creation | Explicit via REST API | Implicit with first query |
| Lifecycle Control | Programmatic start/stop | Timeout-based only |
| State Management | Persistent across disconnections | Requires active connection |
| Proxy Configuration | Set once, applies to all queries | Per-query configuration |
| Stealth Requirement | Required for BQL support | Available for all BQL queries |

## Best Practices​

1. Always use stealth mode when you need BQL functionality
2. Set appropriate TTL based on your workflow duration
3. Handle session expiration gracefully in your applications
4. Reuse sessions for multiple related operations to maintain state
5. Configure proxy settings at session creation for consistent behavior
6. Monitor session status before executing long-running operations

## Next Steps​

- Reconnecting to Browserless - Learn about standard BQL reconnection patterns
- Puppeteer & Playwright Integration - Mix BQL with Puppeteer and Playwright workflows
- BQL Language Basics - Master BQL query syntax and mutations



# Session Replay with BQL

The **Session Replay** feature in BrowserQL allows you to record browser sessions and later replay them for debugging and analysis. When using BQL, session recording is controlled through connection parameters and provides seamless integration with GraphQL mutations.

This feature is particularly useful for:

- Debugging complex BQL automation workflows
- Creating visual documentation of GraphQL-based browser automation
- Troubleshooting BQL mutations with recorded evidence

## Prerequisites​

Before using Session Replay with BQL, make sure you have:

1. A Browserless account with Session Replay access
2. A browserless API key
3. Access to the BQL endpoint
4. Understanding of GraphQL mutation syntax

## Recording a Session with BQL​

### Connection String Configuration​

To enable session recording with BQL, add the `replay=true` parameter to your connection string:

```
wss://production-sfo.browserless.io?token=YOUR_API_TOKEN_HERE&replay=true
```

### Basic Recording Example​

- CURL
- JavaScript
- Python

```
curl --request POST \  --url 'https://production-sfo.browserless.io/chrome/bql?token=YOUR_API_TOKEN_HERE&replay=true' \                                     --header 'Content-Type: application/json' \  --data '{"query":"mutation replay {\n  goto(url: \"https://www.browserless.io\") {\n  \ttime\n  }\n  click(selector:\"a\"){\n    time\n  }\n  waitForTimeout(time:2000){\n    time\n  }\n}","variables":{},"operationName":"replay"}'
```

```
import fetch from 'node-fetch';const API_KEY = "YOUR_API_TOKEN_HERE";const BQL_ENDPOINT = `https://production-sfo.browserless.io/chromium/bql?replay=true&token=${API_KEY}`;const recordingQuery = `mutation replay {  goto(url: "https://www.browserless.io") {    time  }   click(selector:"a"){    time  }  waitForTimeout(time:2000){    time  }}`;const recordSession = async () => {  const response = await fetch(BQL_ENDPOINT, {    method: 'POST',    headers: {      'Content-Type': 'application/json'    },    body: JSON.stringify({ query: recordingQuery,"operationName":"replay" })  });  const result = await response.json();  console.log('Recording Result:', JSON.stringify(result, null, 2));    // Session recording automatically stops when the BQL query completes  console.log('Session recorded successfully');};recordSession().catch(console.error);
```

```
import requestsimport jsonAPI_KEY = "YOUR_API_TOKEN_HERE"BQL_ENDPOINT = f"https://production-sfo.browserless.io/chromium/bql?replay=true&token={API_KEY}"recording_query = """mutation RecordSession {  goto(url: "https://www.example.com") {    status    time  }    click(selector: "button.example") {    time    x    y  }    type(selector: "input[name='search']", text: "browserless") {    time  }    waitForSelector(selector: ".search-results") {    time  }}"""def record_session():    response = requests.post(        BQL_ENDPOINT,        headers={            'Content-Type': 'application/json'        },        json={'query': recording_query}    )        result = response.json()    print('Recording Result:', json.dumps(result, indent=2))        # Session recording automatically stops when the BQL query completes    print('Session recorded successfully')if __name__ == "__main__":    record_session()
```



# Injecting Cookies

Cookie management is essential for maintaining session state, authentication, and personalized user experiences during browser automation. BrowserQL provides powerful cookie injection and extraction capabilities through the `cookies` mutation, allowing you to set cookies before navigation and retrieve them after page interactions.

## Cookie Operations​

The `cookies` mutation in BrowserQL serves dual purposes:

- Setting cookies: Pass an array of CookieInput objects to inject cookies into the browser
- Getting cookies: Call without parameters to retrieve all cookies from the current page

### Cookie Input Structure​

When setting cookies, use the `CookieInput` type with the following properties:

- name (required): Cookie name
- value (required): Cookie value
- domain: Cookie domain (e.g., "example.com")
- path: Cookie path (defaults to "/")
- secure: Boolean indicating if cookie requires HTTPS
- httpOnly: Boolean for HTTP-only cookies
- sameSite: Cookie SameSite policy (Strict, Lax, or None)
- expires: Expiration timestamp (session cookie if not set)
- url: Request URI to associate with the cookie

### Cookie Response​

The mutation returns a `CookieResponse` containing:

- cookies: Array of StandardCookie objects with name, value, domain, path, and security properties
- time: Execution time in milliseconds

## Complete Cookie Management Example​

Here's a comprehensive example demonstrating cookie injection and extraction using the test site setcookie.net:

- BrowserQL
- JavaScript
- Python

```
mutation cookies {  setCookies: cookies(cookies: [    {      name: "test_cookie"      value: "123456"      domain: "setcookie.net"      path: "/"      secure: true    }  ]) {    cookies {      name      value    }  }  waitForTimeout(time: 3000) {    time  }  goto(url: "https://setcookie.net/", waitUntil: networkIdle) {    status  }  getCookies: cookies {    cookies {      name      value      domain      path      secure    }  }}
```

```
import fetch from 'node-fetch';const API_KEY = "YOUR_API_TOKEN_HERE";const BQL_ENDPOINT = `https://production-sfo.browserless.io/chromium/bql?token=${API_KEY}`;const cookieQuery = `mutation cookies {  setCookies: cookies(cookies: [    {      name: "test_cookie"      value: "123456"      domain: "setcookie.net"      path: "/"      secure: true    }  ]) {    cookies {      name      value    }  }  waitForTimeout(time: 3000) {    time  }  goto(url: "https://setcookie.net/", waitUntil: networkIdle) {    status  }  getCookies: cookies {    cookies {      name      value      domain      path      secure    }  }}`;async function manageCookies() {  const response = await fetch(BQL_ENDPOINT, {    method: 'POST',    headers: {      'Content-Type': 'application/json'    },    body: JSON.stringify({ query: cookieQuery })  });  const result = await response.json();  console.log('Cookie Management Result:', JSON.stringify(result, null, 2));    // Access the set cookies  console.log('Set Cookies:', result.data.setCookies.cookies);    // Access the retrieved cookies  console.log('Retrieved Cookies:', result.data.getCookies.cookies);}manageCookies().catch(console.error);
```

```
import requestsimport jsonAPI_KEY = "YOUR_API_TOKEN_HERE"BQL_ENDPOINT = f"https://production-sfo.browserless.io/chromium/bql?token={API_KEY}"cookie_query = """mutation cookies {  setCookies: cookies(cookies: [    {      name: "test_cookie"      value: "123456"      domain: "setcookie.net"      path: "/"      secure: true    }  ]) {    cookies {      name      value    }  }  waitForTimeout(time: 3000) {    time  }  goto(url: "https://setcookie.net/", waitUntil: networkIdle) {    status  }  getCookies: cookies {    cookies {      name      value      domain      path      secure    }  }}"""def manage_cookies():    response = requests.post(        BQL_ENDPOINT,        headers={            'Content-Type': 'application/json'        },        json={'query': cookie_query}    )        result = response.json()    print('Cookie Management Result:', json.dumps(result, indent=2))        # Access the set cookies    print('Set Cookies:', result['data']['setCookies']['cookies'])        # Access the retrieved cookies      print('Retrieved Cookies:', result['data']['getCookies']['cookies'])if __name__ == "__main__":    manage_cookies()
```

## Common Use Cases​

### Authentication Cookies​

Set authentication cookies before navigating to protected pages:

```
mutation setAuthCookie {  cookies(cookies: [    {      name: "session_token"      value: "abc123xyz789"      domain: "example.com"      path: "/"      secure: true      httpOnly: true    }  ]) {    cookies {      name      value    }  }  goto(url: "https://example.com/dashboard") {    status  }}
```

HttpOnly Cookie Limitations

HttpOnly cookies are protected by the browser and cannot be accessed or modified via client-side JavaScript or automation frameworks like BrowserQL, Puppeteer, or Playwright. This security design prevents cross-site scripting (XSS) attacks from stealing authentication tokens. If your workflow requires persisting HttpOnly cookies for authentication across sessions, you should use our [persisting sessions](https://docs.browserless.io/baas/session-management/persisting-state) feature, which maintains all browser state including HttpOnly cookies between reconnections.

### Preference Cookies​

Inject user preference cookies to customize page behavior:

```
mutation setPreferences {  cookies(cookies: [    {      name: "theme"      value: "dark"      domain: "example.com"    },    {      name: "language"      value: "en-US"      domain: "example.com"    }  ]) {    cookies {      name      value    }  }}
```

### Cookie Extraction for Analysis​

Retrieve cookies after user interactions to analyze session data:

```
mutation extractCookies {  goto(url: "https://example.com/login") {    status  }  typeUsername: type(selector: "#username", text: "user@example.com") {    time  }  typePassword: type(selector: "#password", text: "password123") {    time  }  click(selector: "#login-button") {    time  }  waitForSelector(selector: ".dashboard") {    time  }  cookies {    cookies {      name      value      domain      expires      secure      httpOnly    }  }}
```

Cookie management in BrowserQL provides the foundation for sophisticated session handling, enabling seamless automation of authenticated workflows and personalized user experiences.



# Overview

BrowserQL was built from the ground up to handle common challenges when accessing e-commerce or heavily monitored pages. The Bot Detection section helps you understand and overcome anti-bot measures employed by modern websites. These pages cover accessing protected pages, submitting forms without triggering bot flags, solving various types of CAPTCHAs, handling two-factor authentication, reusing sessions through cookies, and utilizing proxies for enhanced anonymity.

**Key Features:**

- Stealth Route: Use the /stealth/bql route for enhanced anti-detection
- Proxy Integration: Utilize built-in residential proxies and third-party proxies for enhanced anonymity and geographic flexibility
- CAPTCHA Solving: Built-in support for solving challenges automatically
- Fingerprint Configuration: Advanced browser fingerprint settings including browser binaries, adblock, and human-like behavior patterns

## Using a Proxy​

BrowserQL offers residential proxy support and third party proxies to successfully bypass bot detection. Proxies are a great tool for bypassing location-specific restrictions, improving stealth, and avoiding IP-based detection mechanisms.

**Proxy Options:**

- Built-in Residential Proxies: BQL includes built-in support for residential proxies, allowing you to select countries for proxy routing and configure whether to reuse the same proxy for multiple requests
- Third-Party Proxies: Support for external proxy servers with flexible configuration options for different request types
- Optimization Strategies: Use request filtering and resource rejection to minimize bandwidth consumption and reduce proxy unit usage

For detailed information on proxy configuration, optimization techniques, and advanced usage patterns, see our [Proxies documentation](https://docs.browserless.io/browserql/bot-detection/proxies).

warning

Using a proxy will consume 6 units per MB.

## Solving CAPTCHAs​

CAPTCHAs are a common roadblock in automation, but BrowserQL includes built-in support for solving various types of CAPTCHA challenges.

For detailed information on CAPTCHA solving techniques, conditional verification, and form submission after solving, see our [Solving CAPTCHAs documentation](https://docs.browserless.io/browserql/bot-detection/solving-captchas).

## Human-like Fingerprints​

BrowserQL automatically ensures a convincing fingerprint. BQL ensures your browser sessions are indistinguishable from genuine user activity. This built-in feature saves time and effort while providing top-notch stealth for your automation needs.

There are a few things that you can configure for your BQL executions, listed below.

Enterprise

For enterprise users, BQL supports M1 systems, providing high-performance browser automation on macOS devices.

### Browser Binaries​

You can select which browser you want to use, either Chromium or Chrome.
Which is the best? Well, the one that works for you!
Keep in mind that Chrome comes with codecs to render things like streamed videos, or other type of multimedia, so it is typically regarded as a more human-like browsers, however it's not a guarantee, and sometimes Chromium is the way to go!

Some detectors will block Chromium specifically, but it's more efficient to run. You have a choice of running Chrome or Chromium browsers, which you can change in the session settings.

### Adblock​

Everyone hates ads, especially humans. Using the [blockAds option](https://docs.browserless.io/browserql/launch-parameters#launch-options-query-parameters) basically means you're running an extension that blocks ads, meaning the target site will recognize that you actually have an adblocking extension installed, and this itself will change the fingerprint of your session.

### Human-like Behavior​

This will help with sites that track interactions with the website. Using this turned on will make smooth mouse behavior and human-like typing patterns, i.e. it'll make mistakes while typing, vary in speed and the mouse movements will be more erratic and human-like.

## Next Steps​

Ready to take your bot detection bypass to the next level? Explore these key areas:

[Solving CAPTCHAsHandle Cloudflare, reCAPTCHA, and a variety of others automatically with built-in support.](https://docs.browserless.io/browserql/bot-detection/solving-captchas)
[ProxiesUse residential and external proxies for enhanced anonymity and geographic flexibility.](https://docs.browserless.io/browserql/bot-detection/proxies)
[Stealthy BQLLearn more about our stealth routes for BQL](https://docs.browserless.io/browserql/bot-detection/stealth)



# Stealth Route

BrowserQL's stealth route provides advanced anti-detection capabilities specifically optimized for our BQL tool. This route combines BrowserQL's powerful automation features with comprehensive browser fingerprint mitigations and entropy injection for maximum effectiveness against bot detection systems.

## Available Stealth Route​

- Stealth Route (Recommended) - /stealth/bql
Our recommended stealth route for BrowserQL users. This managed stealth environment provides advanced anti-detection and realistic fingerprinting with comprehensive browser fingerprint mitigations and entropy injection for maximum effectiveness against bot detection systems.

## Using the Stealth Route​

To use the stealth route with BrowserQL, you can select the Stealth browser in the [BQL IDE settings](https://account.browserless.io/bql/), or when running programmatically, simply specify the stealth endpoint:

```
# Stealth (Recommended)curl -X POST \  https://production-sfo.browserless.io/stealth/bql?token=YOUR_API_TOKEN_HERE \  -H 'Content-Type: application/json' \  -d '{    "query": "query { goto(url: \"https://example.com\") { status } }"  }'
```

## Additional Bot Detection Strategies​

To further enhance your ability to bypass bot detection with BrowserQL:

- Use Residential Proxies: Many sites monitor IP addresses and may block data-center IPs or enforce rate limits. BrowserQL supports built-in residential proxies with country selection and proxy reuse options. For setup details, see our Proxies documentation.
- Enable Human-like Behavior: Configure mouse movements and typing patterns to appear more natural and human-like.
- Block Ads: Using ad-blocking can make your sessions appear more like real users, as most humans use ad blockers.
- Advanced Techniques: If standard stealth features aren't enough, contact us at support@browserless.io. We can assist with advanced solutions and specialized infrastructure available on our enterprise plans.

## Next Steps​

Ready to implement stealth routes in your BrowserQL automation? Explore these key areas:

[Solving CAPTCHAsHandle Cloudflare, reCAPTCHA, and other challenges automatically with built-in support.](https://docs.browserless.io/browserql/bot-detection/solving-captchas)
[ProxiesUse residential and external proxies for enhanced anonymity and geographic flexibility.](https://docs.browserless.io/browserql/bot-detection/proxies)
[Bot Detection OverviewLearn about all available bot detection features and strategies in BrowserQL.](https://docs.browserless.io/browserql/bot-detection/overview)

If you need more help or want to discuss your specific use case, don't hesitate to reach out. We're here to help you succeed with even the toughest bot detection challenges.


# Solving CAPTCHAs

CAPTCHAs are a common roadblock in automation. They may appear less when using a [stealth route](https://docs.browserless.io/browserql/bot-detection/stealth) but some sites always enforce them. BrowserQL includes built-in support for CAPTCHA challenges. BQL can detect and interact with CAPTCHAs, even those embedded in iframes or shadow DOMs.

You can use the following mutations:

- Verify
- Solve

## Verify​

The [Verify](https://docs.browserless.io/bql-schema/operations/mutations/verify) mutation clicks a verification button to assert human-like interaction. This mutation can be used to surpass cloudflare's human verification step. Make sure that you have our residential proxying turned on, as it's a requirement for it to work.

If you're not sure whether a site has Cloudflare protection, you can use the `if` mutation with a `waitForSelector` to conditionally run the verification. Since the `if` mutation doesn't wait for a selector to be present, adding a `waitForSelector` before it ensures the Cloudflare turnstile is available before attempting verification.

```
mutation Verify {  # Enable residential proxies so cloudflare can be solved successfully  goto(url: "https://protected.domain") {    status  }  verify(type: cloudflare) {    found    solved    time  }}
```

### Conditional Cloudflare Verification​

Here's an example of using conditional verification with the `if` mutation:

```
mutation Verify {  # Enable residential proxies so cloudflare can be solved successfully  goto(url: "https://www.browserless.io/practice-form") {    status  }  waitForSelector(selector:".cf-turnstile",timeout:1000){    time  }  if(selector:".cf-turnstile"){    verify(type:cloudflare,timeout:30000){      found      solved      time    }  }  html{    html  }}
```

Note that `.cf-turnstile` is specific to our sample website. For your own implementation, you should look for a selector that works for your target website. Some alternatives that might work on other sites include `a[href*="cloudflare.com"]` or other Cloudflare-specific elements.

### Conditional Cloudflare Challenge Page Verification​

While the previous example handles Cloudflare turnstile challenges, Cloudflare also presents challenge pages that require a different approach. These challenge pages can be identified by looking for links containing "cloudflare.com" and require special handling:

```
mutation VerifyCloudflareChallenge {  goto(url: "https://protected.domain") {    status  }    waitForSelector(selector:"a[href*=\"cloudflare.com\"]",timeout:1000){    time  }  if1:if(selector:"a[href*=\"cloudflare.com\"]"){    verify(type:cloudflare,timeout:20000){      found      solved      time    }    w1:waitForNavigation(waitUntil:networkIdle,timeout:20000){       status      time    }  }}
```

**Important notes about Cloudflare challenge pages:**

- Navigation wait: After verification, the script waits for navigation to complete to ensure the challenge page has been properly processed.
- Timeout handling: The script waits 1 second to detect if a Cloudflare challenge page appears. If no challenge page is found, you'll see an error message about the selector not being found - this can be safely ignored.
- Alternative approach: If you don't want to wait 1 second, you can wait for a successful selector (the opposite of the challenge detection), but this requires knowing which selector indicates successful page load for your specific target URL.

## Solve​

The [Solve](https://docs.browserless.io/bql-schema/operations/mutations/solve) mutation solves CAPTCHAs on a page. By default, it automatically detects the CAPTCHA type without requiring you to specify it. This auto-detection feature is the preferred approach and simplifies your queries.

info

When solving reCAPTCHAs, it's normal if there isn't a visual confirmation that the CAPTCHA has been solved (i.e., the checkbox may not appear ticked). This is expected behavior. After solving, you should proceed and click on the form's submit button.

```
mutation SolveCaptcha {  goto(url: "https://protected.domain") {    status  }  solve {    found    solved    time  }}
```

### Specifying type​

The `type` argument is optional and can be used to specify which CAPTCHA type to solve. Specifying the type can reduce verification time by a few milliseconds if you're certain which CAPTCHA type is present on the site. We're constantly supporting more CAPTCHAs - you can find the list of supported types in our [browserQL schema](https://docs.browserless.io/bql-schema/types/enums/captcha-types).

```
mutation SolveCaptchaWithType {  goto(url: "https://protected.domain") {    status  }  solve(type: recaptcha) {    found    solved    time  }}
```

### Form Submission After Solving​

After solving a CAPTCHA, you should proceed with form submission by clicking the submit button:

```
mutation SolveAndSubmit {  goto(url: "https://protected.domain") {    status  }  solve {    found    solved    time  }  click(selector: "button[type='submit']") {    time  }}
```

If there isn't a submit button available, you can trigger form submission manually using the `evaluate` mutation:

```
mutation SolveAndTriggerSubmit {  goto(url: "https://protected.domain") {    status  }  solve {    found    solved    time  }  evaluate(content: "window.onSubmit()") {    time  }}
```

Replace `window.onSubmit()` with the appropriate JavaScript function that submits the form on your target website.

## Next Steps​

Ready to take your bot detection bypass to the next level? Explore these key areas:

[Bot detectionLearn more about our Bot detection techniques for BQL](https://docs.browserless.io/browserql/bot-detection/overview)
[ProxiesUse residential and external proxies for enhanced anonymity and geographic flexibility.](https://docs.browserless.io/browserql/bot-detection/proxies)
[Stealthy BQLLearn more about our stealth routes for BQL](https://docs.browserless.io/browserql/bot-detection/stealth)



# Proxies

Proxies act as intermediaries between your device and the internet, enhancing privacy, security, and geographic flexibility by masking your IP address. This page covers the built-in proxy features in BrowserQL, tips for optimizing bandwidth usage with the reject API, and support for third-party proxies for more advanced configurations.

- Built-in Proxies
- External Proxies

## Built-In Proxies​

BrowserQL supports **residential proxies** to enhance privacy, security, and geographic flexibility in browser automation. These proxies help bypass location-specific restrictions, improve stealth, and avoid IP-based detection mechanisms. With built-in proxying, you can configure:

- Proxy Country: Route requests through a specific country.
- Sticky Proxying: Reuse the same proxy for multiple requests.

### How to Enable Built-In Proxies​

1. Open the Session Settings Panel.
2. Toggle Residential Proxying to On.
3. Configure your settings:

Sticky Proxying: Use the same IP for consecutive requests.
Proxy Country: Select the desired country for proxy routing.

warning

Using a proxy consumes **6 units per MB**.

Watch the video below to learn how to turn on proxy:

Your browser does not support the video tag.

### Programmatic Usage​

You can also enable built-in proxies programmatically by adding proxy parameters directly to your BQL endpoint URL. This is useful when calling BQL from your application code rather than using the IDE.

- Basic Residential Proxy
- Country-Specific Proxy
- Sticky Proxy

```
https://production-sfo.browserless.io/stealth/bql?token=YOUR_API_TOKEN_HERE&proxy=residential
```

```
https://production-sfo.browserless.io/stealth/bql?token=YOUR_API_TOKEN_HERE&proxy=residential&proxyCountry=us
```

```
https://production-sfo.browserless.io/stealth/bql?token=YOUR_API_TOKEN_HERE&proxy=residential&proxyCountry=us&proxySticky=true
```

**Available Parameters:**

- proxy=residential - Enables residential proxy routing
- proxyCountry=us - Routes through a specific country ISO 3166 country codes
- proxyCity=chicago - Routes through a specific city within the selected country
- proxySticky=true - Maintains the same proxy IP across the session when possible

City-Level Proxying

City-level proxying requires a **Scale plan** (500k+ units). Plans under 500k units will receive a `401` error.

To get a list of available cities, use the following endpoints:

- All supported cities: https://production-sfo.browserless.io/proxy/cities?token=YOUR_TOKEN
- Cities for a specific country: https://production-sfo.browserless.io/proxy/cities?country=US&token=YOUR_TOKEN

warning

Using a proxy consumes **6 units per MB**, regardless of whether configured via the IDE or programmatically.

## Optimizing Proxy Usage​

You can optimize your proxy usage by filtering what resources pass through proxies or reject unnecessary requests. This can help reduce bandwidth consumption and improve efficiency when using proxies.

### Filtering specific Requests​

You can define which requests need to be proxied, based on URL pattern, request method and request type. To proxy all requests, simply use `url: "*"` to match everything. To proxy only the document requests, set `type: document` as follows:

```
mutation proxy_filtering{  proxy(server: "http://john:1337@myproxy.com:1234" type: [document, xhr]) {    time  }  goto(url: "https://nordvpn.com/what-is-my-ip/", waitUntil: load) {    status  }}
```

### Using resource rejection​

The reject mutation allows you to block requests based on:

- URL patterns: Use glob-style patterns to match specific domains or paths.
- HTTP methods: Reject specific request methods (e.g., GET, POST).
- Resource types: Filter by resource types, such as images, media, or scripts.
- Operators: Define whether conditions should be combined using "and" (all must match) or "or" (any match).

Bot Detection

While you can reject resources to reduce bandwidth and costs, it could also trigger bot-detection, so use it wisely.

The following example rejects image and media requests, helping save bandwidth:

- Rejecting Images and Media
- Rejecting Media from a Specific Domain

```
mutation RejectImages {  reject(type: [image, media]) {    enabled    time  }  goto(url: "https://cnn.com", waitUntil: firstContentfulPaint) {    status    time  }}
```

To reject media requests originating from the `google.com` domain, use the `and` operator:

```
mutation Reject {  reject(    operator: and    type: image    url: "*google.com*"  ) {    enabled    time  }  goto(url: "https://cnn.com", waitUntil: firstContentfulPaint) {    status    time  }}
```

Behavior

The reject mutation only takes effect during query execution. For instance, scripts that return quickly might still see assets loading in the editor since rejections occur only while mutations are actively running.

## External Proxies​

Alongside the Browserless residential proxy, you can also use an external proxy as well. This is done via the `proxy` mutation, which takes several options with regards to how and when to proxy.

The first requirement is to specify the server's URI to proxy through. This takes the format of `${protocol}://${username}:${password}@${host}:${port}`. For instance, if you have a username of `john` and a password of `1337code` and a URL of `myproxy.com` and a port of `1234`, the server argument would look like: `http://john:1337@myproxy.com:1234`. If you don't have a username or password you can simply omit those fields in the URI. Most proxy servers will also have simple generation widgets that can help build these URI's out for you.

Here's the full snippet in BrowserQL:

```
mutation ExternalProxy {  # Proxy to this server for all requests  proxy(server: "http://john:1337@myproxy.com:1234" url: "*") {    time  }  goto(url: "https://nordvpn.com/what-is-my-ip/", waitUntil: load) {    status  }  waitForTimeout(time: 5000) {    time  }}
```

The second important part of the `proxy` mutation is deciding which requests need to be proxied. BrowserQL supports this by allowing you make patterns of the type of requests you'd like to proxy. You can proxy based upon URL pattern, request methods, and even request types. To proxy *all* requests, simply use `url: "*"` which will match all requests being sent by BrowserQL.

If you want to proxy only the Document requests (typically what most pages are), then you'd set the `type: document` for this. Here's an example of proxying for Document and XHR requests:

```
mutation ProxyDocumentAndXHR {  proxy(server: "http://john:1337@myproxy.com:1234" type: [document, xhr]) {    time  }  goto(url: "https://nordvpn.com/what-is-my-ip/", waitUntil: load) {    status  }  waitForTimeout(time: 5000) {    time  }}
```

Finally, you can mix and match proxies as well with this API. The first proxy that matches the request will be the chosen proxy for that request, so ordering can be important if you want to mix and match proxies for various types of requests.

For instance, you can proxy `document` and `xhr` requests through a residential proxy querying that first, and all other requests through a data-center proxy. Here's how that'd look by specifying the residential proxy *first*, then matching all others via the greedy `url: "*"` pattern:

```
mutation ProxyDocumentAndXHR {  # Proxy document and xhr through residential  residential: proxy(server: "http://john:1337@residential.proxy.com:1234" type: [document, xhr]) {    time  }  # Proxy all else through datacenter  datacenter: proxy(server: "http://john:1337@datacenter.proxy.com:1234" url: "*") {    time  }  goto(url: "https://nordvpn.com/what-is-my-ip/", waitUntil: load) {    status  }  waitForTimeout(time: 5000) {    time  }}
```

## Next Steps​

Ready to take your bot detection bypass to the next level? Explore these key areas:

[Solving CAPTCHAsHandle Cloudflare, reCAPTCHA, and a variety of others automatically with built-in support.](https://docs.browserless.io/browserql/bot-detection/solving-captchas)
[Bot detectionLearn more about our Bot detectiont echniques for BQL](https://docs.browserless.io/browserql/bot-detection/overview)
[Stealthy BQLLearn more about our stealth routes for BQL](https://docs.browserless.io/browserql/bot-detection/stealth)