# Browserless Mutations Documentation



---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/back

* * Operations* Mutations* back

Open in ChatGPT

On this page

# back

Goes back in browser history, optionally accepting waitUntil and timeout arguments. Returns null if no back is possible

**Usage Example:**

```
mutation GoBack {  
  firstNav: goto(url: "https://example.com") {  
    time  
  }  
  
  secondNav: goto(url: "https://browserless.com") {  
    time  
  }  
  
  back(waitUntil: domContentLoaded) {  
    status  
  }  
}
```

**Field Definition:**

```
back(  
  timeout: Float  
  waitUntil: WaitUntilHistory = load  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`back.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#backtimeoutfloat- "Direct link to backtimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`back.waitUntil`](#) ● [`WaitUntilHistory`](/bql-schema/types/enums/wait-until-history) enum[​](#backwaituntilwaituntilhistory- "Direct link to backwaituntilwaituntilhistory-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/checkbox

* * Operations* Mutations* checkbox

Open in ChatGPT

On this page

# checkbox

Sets or un-sets the value of a checkbox on the page

**Usage Example:**

```
mutation ClickCheckbox {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  checkbox(  
    checked: true  
    selector: "input[type='checkbox']"  
  ) {  
    time  
  }  
}
```

**Field Definition:**

```
checkbox(  
  checked: Boolean!  
  selector: String!  
  scroll: Boolean = true  
  timeout: Float  
  visible: Boolean = false  
  wait: Boolean = true  
): ClickResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`checkbox.checked`](#) ● [`Boolean!`](/bql-schema/types/scalars/boolean) non-null scalar[​](#checkboxcheckedboolean-- "Direct link to checkboxcheckedboolean--")

Whether or not the input should be checked

#### [`checkbox.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#checkboxselectorstring-- "Direct link to checkboxselectorstring--")

The CSS selector of the element on the page you want to check/uncheck

#### [`checkbox.scroll`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#checkboxscrollboolean- "Direct link to checkboxscrollboolean-")

Whether or not to scroll to the element prior to clicking, defaults to true

#### [`checkbox.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#checkboxtimeoutfloat- "Direct link to checkboxtimeoutfloat-")

How long to wait for the element to appear before timing out on the handler, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`checkbox.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#checkboxvisibleboolean- "Direct link to checkboxvisibleboolean-")

Whether or not to check/uncheck the element only if it's visible

#### [`checkbox.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#checkboxwaitboolean- "Direct link to checkboxwaitboolean-")

Whether or not to wait for the element to present in the DOM

### Type[​](#type "Direct link to Type")

#### [`ClickResponse`](/bql-schema/types/objects/click-response) object[​](#clickresponse- "Direct link to clickresponse-")

Response returned after having clicked on an element

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/click

* * Operations* Mutations* click

Open in ChatGPT

On this page

# click

Waits for the element to be visible, scrolls to it, then clicks on it with native events

**Usage Example:**

```
mutation ClickButton {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  click(selector: "a") {  
    time  
  }  
}
```

**Field Definition:**

```
click(  
  selector: String!  
  scroll: Boolean = true  
  timeout: Float  
  visible: Boolean = false  
  wait: Boolean = true  
): ClickResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`click.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#clickselectorstring-- "Direct link to clickselectorstring--")

A query-selector compatible string, JavaScript that returns an HTML Node, OR a Browserless-deep query. Examples include:

* A simple `<button />` Element:
  `selector: "button"`
* A JavaScript snippet that returns a button element
  `selector: "document.querySelector('button')"`
* A Browserless Deep query. These queries must start with a "<" character.
  Deep queries will traverse all iframes, shadow-doms (open or closed), and more.
  Basic deep query:
  `selector: "< button"`

Advanced deep query features:

* URL Pattern Matching: Target elements within specific iframes using glob patterns
  `selector: "< https://example.com/* button.active"`
  `selector: "< *google.com/recaptcha* #recaptcha-anchor"`
* Complex Selectors: Combine multiple attributes, classes, and IDs
  `selector: "< input#username.login-form[type='text'][data-test-id*='user']"`
* Attribute Matching: Use various attribute matching operators

  + Contains (\*): `[data-test*="partial"]`
  + Starts with (^): `[class^="prefix-"]`
  + Ends with ($): `[id$="-suffix"]`
  + Exact match: `[type="submit"]`
  + Presence only: `[required]`
* Class and ID Combinations:
  `selector: "< button#submit.primary.large[data-action='save']"`

For reCAPTCHA interactions, you can use deep selectors to target elements within the reCAPTCHA iframe:
`selector: "< *google.com/recaptcha* #recaptcha-anchor"`

Note: Deep selectors support standard CSS selector syntax while maintaining security by disallowing potentially dangerous characters and patterns.

#### [`click.scroll`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#clickscrollboolean- "Direct link to clickscrollboolean-")

Whether or not to scroll to the element prior to clicking, defaults to true

#### [`click.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#clicktimeoutfloat- "Direct link to clicktimeoutfloat-")

How long to wait for the element to appear before timing out on the click handler, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`click.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#clickvisibleboolean- "Direct link to clickvisibleboolean-")

Whether or not to click the element only if it's visible

#### [`click.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#clickwaitboolean- "Direct link to clickwaitboolean-")

Whether or not to wait for the element to present in the DOM

### Type[​](#type "Direct link to Type")

#### [`ClickResponse`](/bql-schema/types/objects/click-response) object[​](#clickresponse- "Direct link to clickresponse-")

Response returned after having clicked on an element

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/content

* * Operations* Mutations* content

Open in ChatGPT

On this page

# content

Sets the given HTML content on the page with an optional waitUntil parameter

**Usage Example:**

```
mutation SetContent {  
  content(html: "<h1>Hello, World!</h1>") {  
    status  
  }  
}
```

**Field Definition:**

```
content(  
  html: String!  
  waitUntil: WaitUntilHistory  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`content.html`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#contenthtmlstring-- "Direct link to contenthtmlstring--")

When present, sets the content of page to the value passed, then returns the pages content

#### [`content.waitUntil`](#) ● [`WaitUntilHistory`](/bql-schema/types/enums/wait-until-history) enum[​](#contentwaituntilwaituntilhistory- "Direct link to contentwaituntilwaituntilhistory-")

When to consider the page fully-loaded and proceed with further execution, used in conjunction with the value parameter

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/cookies

* * Operations* Mutations* cookies

Open in ChatGPT

On this page

# cookies

Sets and gets cookies on the page

**Usage Example:**

```
mutation SetCookies {  
  # Get the cookies on the page  
  getCookies: cookies {  
    cookies {  
      name  
      value  
    }  
  }  
  
  # Set a cookie on the page  
  setCookies: cookies(cookies: [  
      {  
        name: "my-cookie"  
        value: "my-value"  
        url: "https://example.com"  
      }  
  ]) {  
    cookies {  
      name  
      value  
    }  
  }  
}
```

**Field Definition:**

```
cookies(  
  cookies: [CookieInput]  
): CookieResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`cookies.cookies`](#) ● [`[CookieInput]`](/bql-schema/types/inputs/cookie-input) list input[​](#cookiescookiescookieinput-- "Direct link to cookiescookiescookieinput--")

The cookies to set on the page

### Type[​](#type "Direct link to Type")

#### [`CookieResponse`](/bql-schema/types/objects/cookie-response) object[​](#cookieresponse- "Direct link to cookieresponse-")

The response returned after setting or getting cookies

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/evaluate

* * Operations* Mutations* evaluate

Open in ChatGPT

On this page

# evaluate

Evaluates JavaScript client-side, via raw content or a URL to some JavaScript code, in the browser's page environment

**Usage Example:**

```
mutation EvaluateScript {  
  byContent: evaluate(content: "2 + 2") {  
    value  
  }  
  
  byUrl: evaluate(url: "https://example.com/script.js") {  
    value  
  }  
}
```

**Field Definition:**

```
evaluate(  
  content: String  
  timeout: Float  
  url: String  
): EvaluateResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`evaluate.content`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#evaluatecontentstring- "Direct link to evaluatecontentstring-")

The raw script you'd like to evaluate. This code gets wrapped in an async function so you can use `return` at the end as well as `await` and other async concepts. You can return any stringified value from this function

#### [`evaluate.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#evaluatetimeoutfloat- "Direct link to evaluatetimeoutfloat-")

A timeout to wait for the script to finish evaluating, overriding any defaults. Useful for async scripts that may be longer running. Default timeout is 30 seconds, or 30000.

#### [`evaluate.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#evaluateurlstring- "Direct link to evaluateurlstring-")

The URL of the script you'd like to evaluate. This code gets wrapped in an async function so you can use `return` at the end as well as `await` and other async
concepts. You can return any stringified value from this function

### Type[​](#type "Direct link to Type")

#### [`EvaluateResponse`](/bql-schema/types/objects/evaluate-response) object[​](#evaluateresponse- "Direct link to evaluateresponse-")

Response returned after evaluating a script

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/forward

* * Operations* Mutations* forward

Open in ChatGPT

On this page

# forward

Goes forward in browser history, optionally accepting waitUntil and timeout arguments. Returns null if no forward is possible

**Usage Example:**

```
mutation GoForward {  
  firstNav: goto(url: "https://example.com", waitUntil: load) {  
    time  
  }  
  
  secondNav: goto(url: "https://browserless.io", waitUntil: load) {  
    time  
  }  
  
  back(waitUntil: domContentLoaded) {  
    status  
  }  
  
  forward(waitUntil: domContentLoaded) {  
    status  
  }  
}
```

**Field Definition:**

```
forward(  
  timeout: Float  
  waitUntil: WaitUntilHistory = load  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`forward.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#forwardtimeoutfloat- "Direct link to forwardtimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`forward.waitUntil`](#) ● [`WaitUntilHistory`](/bql-schema/types/enums/wait-until-history) enum[​](#forwardwaituntilwaituntilhistory- "Direct link to forwardwaituntilwaituntilhistory-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/goto

* * Operations* Mutations* goto

Open in ChatGPT

On this page

# goto

Navigates to a URL with an optional waitUntil parameter and timeout parameter

**Usage Example:**

```
mutation NavigateToPage {  
  goto(url: "https://example.com") {  
    status  
  }  
}
```

**Field Definition:**

```
goto(  
  url: String!  
  timeout: Float  
  waitUntil: WaitUntilGoto = load  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`goto.url`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#gotourlstring-- "Direct link to gotourlstring--")

The fully-qualified URL of the page you'd like to navigate to

#### [`goto.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#gototimeoutfloat- "Direct link to gototimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`goto.waitUntil`](#) ● [`WaitUntilGoto`](/bql-schema/types/enums/wait-until-goto) enum[​](#gotowaituntilwaituntilgoto- "Direct link to gotowaituntilwaituntilgoto-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/hover

* * Operations* Mutations* hover

Open in ChatGPT

On this page

# hover

Waits for the element to be visible, scrolls to it, then hover on it with native events

**Usage Example:**

```
mutation HoverElement {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  hover(selector: "a") {  
    time  
  }  
}
```

**Field Definition:**

```
hover(  
  scroll: Boolean = true  
  selector: String  
  timeout: Float  
  visible: Boolean = false  
  wait: Boolean = true  
  x: Float  
  y: Float  
): HoverResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`hover.scroll`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#hoverscrollboolean- "Direct link to hoverscrollboolean-")

Whether or not to scroll to the element, defaults to true

#### [`hover.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#hoverselectorstring- "Direct link to hoverselectorstring-")

The CSS selector of the element on the page you want to hover on

#### [`hover.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hovertimeoutfloat- "Direct link to hovertimeoutfloat-")

How long to wait for the element to appear before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`hover.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#hovervisibleboolean- "Direct link to hovervisibleboolean-")

Whether or not to hover on the element only if it's visible

#### [`hover.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#hoverwaitboolean- "Direct link to hoverwaitboolean-")

Whether or not to wait for the element to present in the DOM

#### [`hover.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hoverxfloat- "Direct link to hoverxfloat-")

The X coordinate, in pixels, to hover on the page

#### [`hover.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hoveryfloat- "Direct link to hoveryfloat-")

The Y coordinate, in pixels, to hover on the page

### Type[​](#type "Direct link to Type")

#### [`HoverResponse`](/bql-schema/types/objects/hover-response) object[​](#hoverresponse- "Direct link to hoverresponse-")

Response returned after having hovered over an element

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/html

* * Operations* Mutations* html

Open in ChatGPT

On this page

# html

Returns the HTML content of the page or selector when specified. This API can also "clean" HTML markup returned by specifying a "clean" argument with numerous options. Features of the "clean" argument include removal of non-text nodes, removal of DOM attributes, as well as removal of excessive whitespace and newlines. Using "clean" can save nearly 1,000 times the payload size. Useful for LLM's and other scenarios

**Usage Example:**

```
mutation ExtractHTML {  
  goto(url: "https://example.com") {  
    status  
  }  
  html(selector: "h1") {  
    html  
  }  
}
```

Remove non-text DOM nodes and all Node attributes, but preserve the DOM tree

```
mutation ExtractHTML {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  html(clean: {  
    removeAttributes: true  
    removeNonTextNodes: true  
  }) {  
    html  
  }  
}
```

**Field Definition:**

```
html(  
  selector: String  
  timeout: Float  
  visible: Boolean = false  
  clean: CleanInput  
): HTMLResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`html.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#htmlselectorstring- "Direct link to htmlselectorstring-")

The DOM selector of the given element you want to return the HTML of

#### [`html.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#htmltimeoutfloat- "Direct link to htmltimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the selector to appear, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`html.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#htmlvisibleboolean- "Direct link to htmlvisibleboolean-")

Whether or not to return the HTMLπ content of the element only if it's visible

#### [`html.clean`](#) ● [`CleanInput`](/bql-schema/types/inputs/clean-input) input[​](#htmlcleancleaninput- "Direct link to htmlcleancleaninput-")

Specifies conditions for "cleaning" HTML, useful for minimizing the amount of markup returned for cases like LLMs and more. See nested options for parameters.

### Type[​](#type "Direct link to Type")

#### [`HTMLResponse`](/bql-schema/types/objects/htmlresponse) object[​](#htmlresponse- "Direct link to htmlresponse-")

HTML content of a page

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/if

* * Operations* Mutations* if

Open in ChatGPT

On this page

# if

Triggers a nested branch of work when a given condition is `true`. Does not wait for these items and is a point-in-time check. Use the wait method if you're wanting to await certain behaviors to be present

**Usage Example:**

```
mutation ConditionalRequest {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  # Will only trigger the screenshot if the h1 is present  
  if(selector: "h1") {  
    screenshot {  
      base64  
    }  
  }  
}
```

**Field Definition:**

```
if(  
  request: RequestInput  
  response: ResponseInput  
  selector: String  
  visible: Boolean = false  
): Mutation
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`if.request`](#) ● [`RequestInput`](/bql-schema/types/inputs/request-input) input[​](#ifrequestrequestinput- "Direct link to ifrequestrequestinput-")

Triggers the nested conditions if a request has been made with the following conditions

#### [`if.response`](#) ● [`ResponseInput`](/bql-schema/types/inputs/response-input) input[​](#ifresponseresponseinput- "Direct link to ifresponseresponseinput-")

Triggers the nested conditions if a response has been received with the following conditions

#### [`if.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#ifselectorstring- "Direct link to ifselectorstring-")

Triggers the subsequent conditions if the selector is immediately present

#### [`if.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#ifvisibleboolean- "Direct link to ifvisibleboolean-")

When using selectors in conditionals this options sets whether their or not to consider if they're visible to the viewport

### Type[​](#type "Direct link to Type")

#### [`Mutation`](/bql-schema/types/objects/mutation) object[​](#mutation- "Direct link to mutation-")

Below is a list of all available API options for the service. Click on an API for options, examples, and even argument details.

For more comprehensive examples and recipes, [see our documentation site here](https://docs.browserless.io/).

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/ifnot

* * Operations* Mutations* ifnot

Open in ChatGPT

On this page

# ifnot

Triggers a nested branch of work when a given condition is `false`. This method does not wait for these items and is a point-in-time check. Use the wait method if you're wanting to await certain behaviors to be present

**Usage Example:**

```
mutation ConditionalRequestNot {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  # Will only trigger the screenshot if the h2 is not present  
  ifnot(selector: "h2") {  
    screenshot {  
      base64  
    }  
  }  
}
```

**Field Definition:**

```
ifnot(  
  request: RequestInput  
  response: ResponseInput  
  selector: String  
): Mutation
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`ifnot.request`](#) ● [`RequestInput`](/bql-schema/types/inputs/request-input) input[​](#ifnotrequestrequestinput- "Direct link to ifnotrequestrequestinput-")

Triggers the nested conditions if a request has been made with the following conditions

#### [`ifnot.response`](#) ● [`ResponseInput`](/bql-schema/types/inputs/response-input) input[​](#ifnotresponseresponseinput- "Direct link to ifnotresponseresponseinput-")

Triggers the nested conditions if a response has been received with the following conditions

#### [`ifnot.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#ifnotselectorstring- "Direct link to ifnotselectorstring-")

Triggers the subsequent conditions if the selector is immediately present

### Type[​](#type "Direct link to Type")

#### [`Mutation`](/bql-schema/types/objects/mutation) object[​](#mutation- "Direct link to mutation-")

Below is a list of all available API options for the service. Click on an API for options, examples, and even argument details.

For more comprehensive examples and recipes, [see our documentation site here](https://docs.browserless.io/).

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/javaScriptEnabled

* * Operations* Mutations* javaScriptEnabled

Open in ChatGPT

On this page

# javaScriptEnabled

Sets and gets JavaScript execution on the page

**Note: changing this value won't affect scripts that have already been run. It will take full effect on the next navigation.**

**Usage Example:**

```
mutation EnableJavaScript {  
  status: javaScriptEnabled {  
    enabled  
  }  
  
  disable: javaScriptEnabled(enabled: false) {  
    enabled  
  }  
  
  enable: javaScriptEnabled(enabled: true) {  
    enabled  
  }  
}
```

**Field Definition:**

```
javaScriptEnabled(  
  enabled: Boolean  
): JavaScriptResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`javaScriptEnabled.enabled`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#javascriptenabledenabledboolean- "Direct link to javascriptenabledenabledboolean-")

Whether or not to enable JavaScript on the page

### Type[​](#type "Direct link to Type")

#### [`JavaScriptResponse`](/bql-schema/types/objects/java-script-response) object[​](#javascriptresponse- "Direct link to javascriptresponse-")

The response returned after enabling or disabling JavaScript on the page

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/liveURL

* * Operations* Mutations* liveURL

Open in ChatGPT

On this page

# liveURL

Returns a fully-qualified, user-shareable live-URL for streaming the web-browser to an end-user, optionally interactive.

**Set 30 second timer for interaction**

```
mutation CreateLiveURL {  
  goto(url: "https://example.com") {  
    status  
  }  
  liveURL {  
    liveURL  
  }  
}
```

**Maintain the current browsers viewport and don't resize it**

```
mutation CreateLiveURL {  
  goto(url: "https://example.com") {  
    status  
  }  
  liveURL(resizable: false) {  
    liveURL  
  }  
}
```

**Don't allow interaction at all**

```
mutation CreateLiveURL {  
  goto(url: "https://example.com") {  
    status  
  }  
  liveURL(interactable: false) {  
    liveURL  
  }  
}
```

**Low quality for better bandwidth**

```
mutation CreateLiveURL {  
  goto(url: "https://example.com") {  
    status  
  }  
  liveURL(quality: 20 type: jpeg) {  
    liveURL  
  }  
}
```

**Field Definition:**

```
liveURL(  
  timeout: Float  
  interactable: Boolean = true  
  type: LiveURLStreamType = jpeg  
  quality: Int = 100  
  resizable: Boolean = true  
  showBrowserInterface: Boolean = false  
): LiveURLResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`liveURL.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#liveurltimeoutfloat- "Direct link to liveurltimeoutfloat-")

The maximum time allowed for the browser to remain alive. Once the time is reached, the end-user will receive a prompt that the session has closed

#### [`liveURL.interactable`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#liveurlinteractableboolean- "Direct link to liveurlinteractableboolean-")

Whether the session is interactable or not. Set to "false" to not allow click and mouse events to be forwarded through to the end-user

#### [`liveURL.type`](#) ● [`LiveURLStreamType`](/bql-schema/types/enums/live-urlstream-type) enum[​](#liveurltypeliveurlstreamtype- "Direct link to liveurltypeliveurlstreamtype-")

The binary-type of the streamed imaged. "jpeg" will consumer lower bandwidth and useful low bandwidth networks and devices. "png" is a much higher quality but will consume considerably more bandwidth.

Use "jpeg" when setting a custom quality

#### [`liveURL.quality`](#) ● [`Int`](/bql-schema/types/scalars/int) scalar[​](#liveurlqualityint- "Direct link to liveurlqualityint-")

The quality of the stream, represented as number from 1 - 100. Only used when "type" is "jpeg"

#### [`liveURL.resizable`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#liveurlresizableboolean- "Direct link to liveurlresizableboolean-")

Whether or not to resize the underlying browser to match the end-user's screen size. When `false` the underlying browser will retain it's current viewport, and the end users's screen wil maintain the appropriate aspect ratio.

#### [`liveURL.showBrowserInterface`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#liveurlshowbrowserinterfaceboolean- "Direct link to liveurlshowbrowserinterfaceboolean-")

Whether to show the browser interface and tabs in the live URL. When `false` (default), only the browser content is shown. When `true`, navigation bar and tabs are displayed.

### Type[​](#type "Direct link to Type")

#### [`LiveURLResponse`](/bql-schema/types/objects/live-urlresponse) object[​](#liveurlresponse- "Direct link to liveurlresponse-")

The response from the Live-URL query

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/mapSelector

* * Operations* Mutations* mapSelector

Open in ChatGPT

On this page

# mapSelector

Specify a selector that returns multiple nodes in a document (similar to `document.querySelectorAll`), or JavaScript that returns a NodeList, and this API will respond with details about those DOM nodes. Similar to how "map" works in most functional programming languages and libraries. Useful for mapping over repetitive data in sites and pages like product listings or search results. This will automatically wait for the selector to be present on the page, and is configurable with the "wait" and "timeout" options.

For getting arbitrary DOM attributes back you can specify them via the `attribute(name: "data-custom-attribute")` property. This will return an object with `name` and `value` properties.

You may also continuously map further nested items as well, for instance this query might get all books on a page, and then a nested `mapSelector` call might list all sellers of that book, or shipping speeds. Hierarchy of data is preserved to pass through the hierarchical data modeled inside the DOM.

This API will always return a list of results back regardless if one or more items are found, or `null` if none are found.

Using aliases can also give the returned JSON more meaning and better model the data returned by this powerful API.

**Simple Example**

```
mutation GetHNLinks {  
  goto(url: "https://news.ycombinator.com") {  
    status  
  }  
  
  # Get all the top links HTML  
  mapSelector(selector: ".athing") {  
    innerHTML  
  }  
}
```

**Nested Example With Aliases**

```
mutation GetHNLinksWithMetaData {  
  goto(url: "https://news.ycombinator.com") {  
    status  
  }  
  
  # Get all textual content  
  posts: mapSelector(selector: ".athing") {  
    postName: innerText  
  
    # Get the author(s)  
    authors: mapSelector(selector: ".author") {  
      authorName: innerText  
    }  
  
    # Get the post score  
    score: mapSelector(selector: ".score") {  
      score: innerText  
    }  
  }  
}
```

**Field Definition:**

```
mapSelector(  
  selector: String!  
  timeout: Float  
  wait: Boolean = true  
): [MapSelectorResponse]
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`mapSelector.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#mapselectorselectorstring-- "Direct link to mapselectorselectorstring--")

A `document.querySelectorAll` compatible string, or JavaScript that returns a DOM NodeList. Examples include:

* A list of `<button />` Elements:
  `selector: "button"`
* A JavaScript snippet that returns a button element
  `selector: "document.querySelectorAll('button')"`

#### [`mapSelector.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#mapselectortimeoutfloat- "Direct link to mapselectortimeoutfloat-")

How long to wait for the element to appear before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`mapSelector.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#mapselectorwaitboolean- "Direct link to mapselectorwaitboolean-")

Whether or not to wait for the selectors to present in the DOM

### Type[​](#type "Direct link to Type")

#### [`MapSelectorResponse`](/bql-schema/types/objects/map-selector-response) object[​](#mapselectorresponse- "Direct link to mapselectorresponse-")

Response returned from a Map Selector

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/pdf

* * Operations* Mutations* pdf

Open in ChatGPT

On this page

# pdf

Generates a PDF of the page with the print CSS media type

**Usage Example:**

```
mutation GeneratePDF {  
  goto(url: "https://example.com", waitUntil: firstMeaningfulPaint) {  
    status  
  }  
  
  simple: pdf {  
    base64  
  }  
  
  customArgs: pdf(  
    format: a5  
    displayHeaderFooter: true  
    headerTemplate: "<span style=\"font-size: 16pt;\">Hello World</span>"  
  ) {  
    base64  
  }  
}
```

**Field Definition:**

```
pdf(  
  displayHeaderFooter: Boolean  
  format: PDFPageFormat  
  footerTemplate: String  
  generateDocumentOutline: Boolean  
  generateTaggedPDF: Boolean  
  landscape: Boolean  
  printBackground: Boolean  
  scale: Float  
  timeout: Float  
  waitForImages: Boolean  
  width: FloatOrString  
  headerTemplate: String  
  height: FloatOrString  
  marginBottom: FloatOrString  
  marginLeft: FloatOrString  
  marginRight: FloatOrString  
  marginTop: FloatOrString  
  pageRanges: String  
  preferCSSPageSize: Boolean  
  transferMode: String  
): PDFResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`pdf.displayHeaderFooter`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfdisplayheaderfooterboolean- "Direct link to pdfdisplayheaderfooterboolean-")

Display header and footer. Defaults to false

#### [`pdf.format`](#) ● [`PDFPageFormat`](/bql-schema/types/enums/pdfpage-format) enum[​](#pdfformatpdfpageformat- "Direct link to pdfformatpdfpageformat-")

The page format to use for the PDF

#### [`pdf.footerTemplate`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#pdffootertemplatestring- "Direct link to pdffootertemplatestring-")

HTML template for the print footer. Should use the same format as the `headerTemplate`.

#### [`pdf.generateDocumentOutline`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfgeneratedocumentoutlineboolean- "Direct link to pdfgeneratedocumentoutlineboolean-")

Whether or not to embed the document outline into the PDF

#### [`pdf.generateTaggedPDF`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfgeneratetaggedpdfboolean- "Direct link to pdfgeneratetaggedpdfboolean-")

Whether or not to generate tagged (accessible) PDF. Defaults to embedded choice

#### [`pdf.landscape`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdflandscapeboolean- "Direct link to pdflandscapeboolean-")

Paper orientation. Defaults to false

#### [`pdf.printBackground`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfprintbackgroundboolean- "Direct link to pdfprintbackgroundboolean-")

Print background graphics. Defaults to false

#### [`pdf.scale`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#pdfscalefloat- "Direct link to pdfscalefloat-")

Scale of the webpage rendering. Defaults to 1

#### [`pdf.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#pdftimeoutfloat- "Direct link to pdftimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the PDF to be generated. Default timeout is 30 seconds, or 30000.

#### [`pdf.waitForImages`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfwaitforimagesboolean- "Direct link to pdfwaitforimagesboolean-")

When true, waits for all images on the page to load before generating the PDF.
Default: False

#### [`pdf.width`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfwidthfloatorstring- "Direct link to pdfwidthfloatorstring-")

Width in inches or CSS unit. Defaults to 8.5 inches

#### [`pdf.headerTemplate`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#pdfheadertemplatestring- "Direct link to pdfheadertemplatestring-")

HTML template for the print header. Should be valid HTML markup with following
classes used to inject printing values into them:

* `date`: formatted print date
* `title`: document title
* `url`: document location
* `pageNumber`: current page number
* `totalPages`: total pages in the document

For example, `<span class=title></span>` would generate span containing the title

#### [`pdf.height`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfheightfloatorstring- "Direct link to pdfheightfloatorstring-")

Height in inches or CSS unit. Defaults to 11 inches

#### [`pdf.marginBottom`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfmarginbottomfloatorstring- "Direct link to pdfmarginbottomfloatorstring-")

Bottom margin in inches or CSS unit. Defaults to 1cm (~0.4 inches).

#### [`pdf.marginLeft`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfmarginleftfloatorstring- "Direct link to pdfmarginleftfloatorstring-")

Left margin in inches or CSS unit. Defaults to 1cm (~0.4 inches).

#### [`pdf.marginRight`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfmarginrightfloatorstring- "Direct link to pdfmarginrightfloatorstring-")

Right margin in inches or CSS unit. Defaults to 1cm (~0.4 inches).

#### [`pdf.marginTop`](#) ● [`FloatOrString`](/bql-schema/types/scalars/float-or-string) scalar[​](#pdfmargintopfloatorstring- "Direct link to pdfmargintopfloatorstring-")

Top margin in inches or CSS unit. Defaults to 1cm (~0.4 inches).

#### [`pdf.pageRanges`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#pdfpagerangesstring- "Direct link to pdfpagerangesstring-")

Paper ranges to print, one based, e.g., '1-5, 8, 11-13'. Pages are
printed in the document order, not in the order specified, and no
more than once. Defaults to empty string, which implies the entire document is printed.
The page numbers are quietly capped to actual page count of the
document, and ranges beyond the end of the document are ignored.
If this results in no pages to print, an error is reported.
It is an error to specify a range with start greater than end

#### [`pdf.preferCSSPageSize`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#pdfprefercsspagesizeboolean- "Direct link to pdfprefercsspagesizeboolean-")

Whether or not to prefer page size as defined by css. Defaults to false,
in which case the content will be scaled to fit the paper size

#### [`pdf.transferMode`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#pdftransfermodestring- "Direct link to pdftransfermodestring-")

Return as stream (PrintToPDFRequestTransferMode enum)

### Type[​](#type "Direct link to Type")

#### [`PDFResponse`](/bql-schema/types/objects/pdfresponse) object[​](#pdfresponse- "Direct link to pdfresponse-")

The response returned after generating a PDF

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/preferences

* * Operations* Mutations* preferences

Open in ChatGPT

On this page

# preferences

Sets configuration for the entirety of the session, replacing defaults like the 30 second timeout default

**Usage Example:**

```
mutation SetPreferences {  
  preferences(timeout: 10000) {  
    timeout  
  }  
}
```

**Field Definition:**

```
preferences(  
  timeout: Float = 30000  
): DefaultResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`preferences.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#preferencestimeoutfloat- "Direct link to preferencestimeoutfloat-")

Sets a default timeout for all methods, including 'goto', 'type', 'wait', etc. Default timeout is 30 seconds, or 30000.

### Type[​](#type "Direct link to Type")

#### [`DefaultResponse`](/bql-schema/types/objects/default-response) object[​](#defaultresponse- "Direct link to defaultresponse-")

Default response for all methods

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/proxy

* * Operations* Mutations* proxy

Open in ChatGPT

On this page

# proxy

Proxies requests, by a specified set of conditions, through either the Browserless residential proxy or through an external proxy. Only requests that match these conditions are proxied and the rest are sent from the instance's own IP address.

Use the "server" argument to specify an external proxy for Browserless to use for requests. For requests with authentication, the username and password should be included in the URL using Basic Authentication. See the examples below for more information on how to format those URLs.

**Using the browserless proxy for all requests and proxy through Brazil**

```
proxy(  
  url: "*"  
  country: BR  
) {  
  time  
}
```

**Using an external proxy for all requests**

```
proxy(  
  url: "*"  
  server: "http://username:password@my-proxy.com:12321"  
) {  
  time  
}
```

**Using the Browserless proxy for only document requests and proxying through France**

```
proxy(  
  url: "*"  
  type: document  
  country: FR  
) {  
  time  
}
```

**Field Definition:**

```
proxy(  
  country: CountryType  
  city: String  
  state: String  
  sticky: Boolean  
  server: String  
  method: [Method]  
  operator: OperatorTypes = or  
  type: [ResourceType]  
  url: [String]  
): ProxyResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`proxy.country`](#) ● [`CountryType`](/bql-schema/types/enums/country-type) enum[​](#proxycountrycountrytype- "Direct link to proxycountrycountrytype-")

The country you wish to proxy through. Only allowed when using the browserless.io proxy and no `server` argument.

#### [`proxy.city`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#proxycitystring- "Direct link to proxycitystring-")

The city you wish to proxy through. Any spaces should be removed and all casing lowercase. For instance, "New York City" should be "newyorkcity"

#### [`proxy.state`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#proxystatestring- "Direct link to proxystatestring-")

The state or provence you wish to proxy through. Any spaces should be removed and all casing lowercase. For instance, "Rhode Island" would be "rhodeisland" and "New Brunswick" would be "newbrunswick"

#### [`proxy.sticky`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#proxystickyboolean- "Direct link to proxystickyboolean-")

Whether or not you want the same IP to be used for subsequent requests matching the pattern

#### [`proxy.server`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#proxyserverstring- "Direct link to proxyserverstring-")

An external proxy to use for these requests matching the specified patterns set in the other arguments. When this is set then `country`, `city`, `state` and `sticky` options will throw errors as these are only valid for the browserless.io proxy network

#### [`proxy.method`](#) ● [`[Method]`](/bql-schema/types/enums/method) list enum[​](#proxymethodmethod-- "Direct link to proxymethodmethod--")

The Method(s) of the request you'd like to proxy

#### [`proxy.operator`](#) ● [`OperatorTypes`](/bql-schema/types/enums/operator-types) enum[​](#proxyoperatoroperatortypes- "Direct link to proxyoperatoroperatortypes-")

Whether to "or" conditions together, meaning any condition that matches will be proxied, or "and" them together meaning every condition must match to proxy the request.

#### [`proxy.type`](#) ● [`[ResourceType]`](/bql-schema/types/enums/resource-type) list enum[​](#proxytyperesourcetype-- "Direct link to proxytyperesourcetype--")

The content-type of the request you'd like to proxy requests to

#### [`proxy.url`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#proxyurlstring-- "Direct link to proxyurlstring--")

A glob-style URL pattern to match requests, and if matched, are proxied through

### Type[​](#type "Direct link to Type")

#### [`ProxyResponse`](/bql-schema/types/objects/proxy-response) object[​](#proxyresponse- "Direct link to proxyresponse-")

Response returned after setting up the proxy patterns

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/querySelectorAll

* * Operations* Mutations* querySelectorAll

Open in ChatGPT

On this page

# querySelectorAll

Passes through certain properties of the browsers' own `document.querySelectorAll` API

**Usage Example:**

```
mutation FindElements {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  query: querySelectorAll(selector: "h1") {  
    innerHTML  
  }  
}
```

**Field Definition:**

```
querySelectorAll(  
  selector: String!  
  timeout: Float  
  visible: Boolean = false  
): [QuerySelectorResponse]
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`querySelectorAll.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#queryselectorallselectorstring-- "Direct link to queryselectorallselectorstring--")

#### [`querySelectorAll.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#queryselectoralltimeoutfloat- "Direct link to queryselectoralltimeoutfloat-")

#### [`querySelectorAll.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#queryselectorallvisibleboolean- "Direct link to queryselectorallvisibleboolean-")

### Type[​](#type "Direct link to Type")

#### [`QuerySelectorResponse`](/bql-schema/types/objects/query-selector-response) object[​](#queryselectorresponse- "Direct link to queryselectorresponse-")

The response returned after querying the page for a selector

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/querySelector

* * Operations* Mutations* querySelector

Open in ChatGPT

On this page

# querySelector

Passes through certain properties of the browsers' own `document.querySelector` API

**Usage Example:**

```
mutation FindElement {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  query: querySelector(selector: "h1") {  
    innerHTML  
  }  
}
```

**Field Definition:**

```
querySelector(  
  selector: String!  
  timeout: Float  
  visible: Boolean = false  
): QuerySelectorResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`querySelector.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#queryselectorselectorstring-- "Direct link to queryselectorselectorstring--")

#### [`querySelector.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#queryselectortimeoutfloat- "Direct link to queryselectortimeoutfloat-")

#### [`querySelector.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#queryselectorvisibleboolean- "Direct link to queryselectorvisibleboolean-")

### Type[​](#type "Direct link to Type")

#### [`QuerySelectorResponse`](/bql-schema/types/objects/query-selector-response) object[​](#queryselectorresponse- "Direct link to queryselectorresponse-")

The response returned after querying the page for a selector

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/reconnect

* * Operations* Mutations* reconnect

Open in ChatGPT

On this page

# reconnect

Returns a payload with reconnection information in order to reconnect back to the same browser session

**Usage Example:**

```
mutation ReconnectSession {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  reconnect(timeout: 30000) {  
    browserQLEndpoint  
    browserWSEndpoint  
    devtoolsFrontendUrl  
    webSocketDebuggerUrl  
  }  
}
```

**Field Definition:**

```
reconnect(  
  timeout: Float = 30000  
): ReconnectionResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`reconnect.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#reconnecttimeoutfloat- "Direct link to reconnecttimeoutfloat-")

The amount of time, in milliseconds, to leave the browser open without a connection before it is manually terminated. Defaults to 30 seconds

### Type[​](#type "Direct link to Type")

#### [`ReconnectionResponse`](/bql-schema/types/objects/reconnection-response) object[​](#reconnectionresponse- "Direct link to reconnectionresponse-")

The response received after attempting to reconnect a BrowserQL session

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/reject

* * Operations* Mutations* reject

Open in ChatGPT

On this page

# reject

Rejects requests by a specified URL pattern, method, or type and operator. You may supply a single pattern, or a list (array) of them. This mutation, by default, will reject any requests that match *any* pattern, which we call an "or" operator. To reject requests where conditions must all match, specify an "and" operator in the mutation. Note that this only has an effect when the query is executing, so scripts that return quickly will likely see assets loading in the editor as these rejections only happen when mutations are executing.

---

**Rejecting images or media**

```
mutation RejectImages {  
  reject(type: [image, media]) {  
    enabled  
    time  
  }  
  goto(url: "https://cnn.com"  
  waitUntil: firstContentfulPaint) {  
    status  
    time  
  }  
}
```

---

**Rejecting media when coming from google.com domain**

```
mutation RejectRequests {  
  reject(  
    operator: and  
    type: image  
    url: "*google.com*"  
  ) {  
    enabled  
    time  
  }  
  goto(url: "https://cnn.com"  
  waitUntil: firstContentfulPaint) {  
    status  
    time  
  }  
}
```

**Field Definition:**

```
reject(  
  enabled: Boolean = true  
  method: [Method]  
  operator: OperatorTypes = or  
  type: [ResourceType]  
  url: [String]  
): RejectResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`reject.enabled`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#rejectenabledboolean- "Direct link to rejectenabledboolean-")

Whether or not to enable request rejections

#### [`reject.method`](#) ● [`[Method]`](/bql-schema/types/enums/method) list enum[​](#rejectmethodmethod-- "Direct link to rejectmethodmethod--")

The Method of the request you'd like to reject

#### [`reject.operator`](#) ● [`OperatorTypes`](/bql-schema/types/enums/operator-types) enum[​](#rejectoperatoroperatortypes- "Direct link to rejectoperatoroperatortypes-")

Whether to "or" conditions together, meaning any condition that matches will be rejected, or "and" them together meaning every condition must match to reject the request.

#### [`reject.type`](#) ● [`[ResourceType]`](/bql-schema/types/enums/resource-type) list enum[​](#rejecttyperesourcetype-- "Direct link to rejecttyperesourcetype--")

The type of resource you'd like to reject request to

#### [`reject.url`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#rejecturlstring-- "Direct link to rejecturlstring--")

The glob-style URL pattern you'd like to reject requests to

### Type[​](#type "Direct link to Type")

#### [`RejectResponse`](/bql-schema/types/objects/reject-response) object[​](#rejectresponse- "Direct link to rejectresponse-")

The response parameters for the reject mutation

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/reload

* * Operations* Mutations* reload

Open in ChatGPT

On this page

# reload

Reloads the given page with an optional waitUntil parameter and timeout parameter

**Usage Example:**

```
mutation ReloadPage {  
  goto(url: "https://example.com") {  
    status  
  }  
  reload(timeout: 10000) {  
    status  
  }  
}
```

**Field Definition:**

```
reload(  
  timeout: Float  
  waitUntil: WaitUntilHistory = load  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`reload.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#reloadtimeoutfloat- "Direct link to reloadtimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`reload.waitUntil`](#) ● [`WaitUntilHistory`](/bql-schema/types/enums/wait-until-history) enum[​](#reloadwaituntilwaituntilhistory- "Direct link to reloadwaituntilwaituntilhistory-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/request

* * Operations* Mutations* request

Open in ChatGPT

On this page

# request

Returns request information made by the Browser with optional filters via arguments. You may filter the returned results by a lob-like URL-pattern, the method of the request or the type of request. Applying an operator to this will then change the behavior by either "and"ing the filters together or "or"ing them. This API will automatically wait for the request to be made if none is immediately found which you can turn off by disabling the "wait" option.

**Getting all "Document" requests**

```
  mutation DocumentRequests {  
    goto(url: "https://example.com/", waitUntil: load) {  
      status  
    }  
    request(type:document) {  
      url  
      type  
      method  
      headers {  
        name  
        value  
      }  
    }  
  }
```

**Load all "GET" AJAX Requests**

```
  mutation AJAXGetCalls {  
    goto(url: "https://msn.com/", waitUntil: load) {  
      status  
    }  
    request(type: xhr, method: GET, operator: and) {  
      url  
      type  
      method  
      headers {  
        name  
        value  
      }  
    }  
  }
```

**Field Definition:**

```
request(  
  type: [ResourceType]  
  method: [Method]  
  timeout: Float  
  url: [String]  
  wait: Boolean = true  
  operator: OperatorTypes = or  
): [RequestResponse]
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`request.type`](#) ● [`[ResourceType]`](/bql-schema/types/enums/resource-type) list enum[​](#requesttyperesourcetype-- "Direct link to requesttyperesourcetype--")

The type content-type of the request to match against

#### [`request.method`](#) ● [`[Method]`](/bql-schema/types/enums/method) list enum[​](#requestmethodmethod-- "Direct link to requestmethodmethod--")

The method of the request to return results for

#### [`request.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#requesttimeoutfloat- "Direct link to requesttimeoutfloat-")

How long to wait for the request(s) to be made before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000. "wait" parameter must also be "true".

#### [`request.url`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#requesturlstring-- "Direct link to requesturlstring--")

The pattern of the request URL to wait for, using glob-style pattern-matching

#### [`request.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#requestwaitboolean- "Direct link to requestwaitboolean-")

Whether or not to wait for the request to be made. When set to `true`, generally only one request is returned since this API will wait for the first request that matches any patterns to be returned

#### [`request.operator`](#) ● [`OperatorTypes`](/bql-schema/types/enums/operator-types) enum[​](#requestoperatoroperatortypes- "Direct link to requestoperatoroperatortypes-")

When applying arguments like URL or method, this operator will either "and" them together, or "or" them together. Default is "or"

### Type[​](#type "Direct link to Type")

#### [`RequestResponse`](/bql-schema/types/objects/request-response) object[​](#requestresponse- "Direct link to requestresponse-")

Response returned from the request API

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/response

* * Operations* Mutations* response

Open in ChatGPT

On this page

# response

Returns response information, filtered by the provided arguments, made by the browser. You may optionally filter the returned results by a glob-like URL-pattern, the Method of the response or the Type of response. Applying an operator to this will then change the behavior by either "and"ing the filters together, or "or"ing them. This API will automatically wait for the response to be made if none is immediately found which you can turn off by disabling the "wait" option.

**Getting all "Document" responses**

```
  mutation DocumentResponses{  
    goto(url: "https://example.com/", waitUntil: load) {  
      status  
    }  
    response(type:document) {  
      url  
      body  
      headers {  
        name  
        value  
      }  
    }  
  }
```

**Load all "GET" AJAX Responses**

```
  mutation AJAXGetCalls {  
    goto(url: "https://msn.com/", waitUntil: load) {  
      status  
    }  
    response(type: xhr, method: GET, operator: and) {  
      url  
      type  
      method  
      body  
      headers {  
        name  
        value  
      }  
    }  
  }
```

**Field Definition:**

```
response(  
  status: [Int]  
  method: [Method]  
  operator: OperatorTypes = or  
  timeout: Float  
  type: [ResourceType]  
  url: [String]  
  wait: Boolean = true  
): [ResponseResponse]
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`response.status`](#) ● [`[Int]`](/bql-schema/types/scalars/int) list scalar[​](#responsestatusint-- "Direct link to responsestatusint--")

The status codes response to return results for

#### [`response.method`](#) ● [`[Method]`](/bql-schema/types/enums/method) list enum[​](#responsemethodmethod-- "Direct link to responsemethodmethod--")

The method of the response to return results for

#### [`response.operator`](#) ● [`OperatorTypes`](/bql-schema/types/enums/operator-types) enum[​](#responseoperatoroperatortypes- "Direct link to responseoperatoroperatortypes-")

When applying arguments like URL or method, this operator will either "and" them together, or "or" them together. Default is "or"

#### [`response.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#responsetimeoutfloat- "Direct link to responsetimeoutfloat-")

How long to wait for the response(s) to be made before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000. "wait" parameter must also be "true".

#### [`response.type`](#) ● [`[ResourceType]`](/bql-schema/types/enums/resource-type) list enum[​](#responsetyperesourcetype-- "Direct link to responsetyperesourcetype--")

The type content-type of the response to match against

#### [`response.url`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#responseurlstring-- "Direct link to responseurlstring--")

The pattern of the response URL to wait for, using glob-style pattern-matching

#### [`response.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#responsewaitboolean- "Direct link to responsewaitboolean-")

Whether or not to wait for the response to be received. When set to `true`, generally only one response is returned since this API will wait for the first response that matches any patterns to be returned

### Type[​](#type "Direct link to Type")

#### [`ResponseResponse`](/bql-schema/types/objects/response-response) object[​](#responseresponse- "Direct link to responseresponse-")

Response returned from the response API

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/screenshot

* * Operations* Mutations* screenshot

Open in ChatGPT

On this page

# screenshot

Screenshots the page or a specific selector

**Usage Example:**

```
mutation TakeScreenshot {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  screenshot {  
    base64  
  }  
}
```

**Field Definition:**

```
screenshot(  
  captureBeyondViewport: Boolean  
  clip: ScreenshotClip  
  fromSurface: Boolean  
  fullPage: Boolean  
  omitBackground: Boolean  
  optimizeForSpeed: Boolean  
  quality: Float  
  selector: String  
  type: ScreenshotType  
  timeout: Float  
  waitForImages: Boolean  
): ScreenshotResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`screenshot.captureBeyondViewport`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotcapturebeyondviewportboolean- "Direct link to screenshotcapturebeyondviewportboolean-")

Capture the screenshot beyond the viewport.
Default: False if there is no clip. True otherwise

#### [`screenshot.clip`](#) ● [`ScreenshotClip`](/bql-schema/types/inputs/screenshot-clip) input[​](#screenshotclipscreenshotclip- "Direct link to screenshotclipscreenshotclip-")

Specifies the region of the page/element to clip

#### [`screenshot.fromSurface`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotfromsurfaceboolean- "Direct link to screenshotfromsurfaceboolean-")

Capture the screenshot from the surface, rather than the view.
Default: True

#### [`screenshot.fullPage`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotfullpageboolean- "Direct link to screenshotfullpageboolean-")

When True, takes a screenshot of the full page.
Default: False

#### [`screenshot.omitBackground`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotomitbackgroundboolean- "Direct link to screenshotomitbackgroundboolean-")

Hides default white background and allows capturing screenshots with transparency.
Default: False

#### [`screenshot.optimizeForSpeed`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotoptimizeforspeedboolean- "Direct link to screenshotoptimizeforspeedboolean-")

Optimize image encoding for speed, not for resulting size.
Default: False

#### [`screenshot.quality`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotqualityfloat- "Direct link to screenshotqualityfloat-")

Quality of the image, between 0-100. Not applicable to png images.

#### [`screenshot.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#screenshotselectorstring- "Direct link to screenshotselectorstring-")

The CSS selector of the element on the page you want to screenshot

#### [`screenshot.type`](#) ● [`ScreenshotType`](/bql-schema/types/enums/screenshot-type) enum[​](#screenshottypescreenshottype- "Direct link to screenshottypescreenshottype-")

The final format of the screenshot

#### [`screenshot.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshottimeoutfloat- "Direct link to screenshottimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the screenshot to be taken. Default timeout is 30 seconds, or 30000.

#### [`screenshot.waitForImages`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#screenshotwaitforimagesboolean- "Direct link to screenshotwaitforimagesboolean-")

When true, waits for all images on the page to load before taking the screenshot.
Default: False

### Type[​](#type "Direct link to Type")

#### [`ScreenshotResponse`](/bql-schema/types/objects/screenshot-response) object[​](#screenshotresponse- "Direct link to screenshotresponse-")

The response returned after generating a Screenshot

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/scroll

* * Operations* Mutations* scroll

Open in ChatGPT

On this page

# scroll

Waits for a selector, then scrolls to it on the page or an x,y coordinate in pixels

**Usage Example:**

```
mutation ScrollToElement {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  scroll(selector: "h1") {  
    time  
  }  
}
```

**Field Definition:**

```
scroll(  
  selector: String  
  timeout: Float  
  visible: Boolean = false  
  wait: Boolean = true  
  x: Float  
  y: Float  
): ScrollResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`scroll.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#scrollselectorstring- "Direct link to scrollselectorstring-")

The DOM selector of the element on the page you want to scroll to

#### [`scroll.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrolltimeoutfloat- "Direct link to scrolltimeoutfloat-")

How long to wait for the element to appear before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`scroll.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#scrollvisibleboolean- "Direct link to scrollvisibleboolean-")

Whether or not to scroll to the element only if it's visible

#### [`scroll.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#scrollwaitboolean- "Direct link to scrollwaitboolean-")

Whether or not to wait for the element, then scroll to it

#### [`scroll.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrollxfloat- "Direct link to scrollxfloat-")

The X coordinate, in pixels, to scroll to

#### [`scroll.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrollyfloat- "Direct link to scrollyfloat-")

The Y coordinate, in pixels, to scroll to

### Type[​](#type "Direct link to Type")

#### [`ScrollResponse`](/bql-schema/types/objects/scroll-response) object[​](#scrollresponse- "Direct link to scrollresponse-")

Response returned after having scrolling inside the page

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/select

* * Operations* Mutations* select

Open in ChatGPT

On this page

# select

Selects a value from a dropdown or multiple select element

**Usage Example:**

```
mutation SelectOption {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  single: select(  
    selector: "select"  
    value: "option1"  
  ) {  
    time  
  }  
  
  multi: select(  
    selector: "select"  
    value: ["option1", "option2"]  
  ) {  
    time  
  }  
}
```

**Field Definition:**

```
select(  
  timeout: Float  
  scroll: Boolean = true  
  selector: String!  
  value: StringOrArray!  
  visible: Boolean = false  
  wait: Boolean = true  
): SelectResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`select.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#selecttimeoutfloat- "Direct link to selecttimeoutfloat-")

How long to wait for the element to appear before timing out on the handler, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`select.scroll`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#selectscrollboolean- "Direct link to selectscrollboolean-")

Whether or not to scroll to the select element prior to selecting, defaults to true

#### [`select.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#selectselectorstring-- "Direct link to selectselectorstring--")

The CSS selector of the element on the page you want to select a value from

#### [`select.value`](#) ● [`StringOrArray!`](/bql-schema/types/scalars/string-or-array) non-null scalar[​](#selectvaluestringorarray-- "Direct link to selectvaluestringorarray--")

The value or values to select from the dropdown or multiple select element

#### [`select.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#selectvisibleboolean- "Direct link to selectvisibleboolean-")

Whether or not to select the element only if it's visible

#### [`select.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#selectwaitboolean- "Direct link to selectwaitboolean-")

Whether or not to wait for the select to present in the DOM

### Type[​](#type "Direct link to Type")

#### [`SelectResponse`](/bql-schema/types/objects/select-response) object[​](#selectresponse- "Direct link to selectresponse-")

The response returned after selecting a value from a dropdown or multiple select element

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/setExtraHTTPHeaders

Error: 404 Client Error: Not Found for url: https://docs.browserless.io/bql-schema/operations/mutations/set-extra-http-headers


---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/solve

* * Operations* Mutations* solve

Open in ChatGPT

On this page

# solve

🚨 **EXPERIMENTAL** 🚨
Solves a captcha or other challenge. Can auto-detect the CAPTCHA type or solve a specific type.
Uses the same detection logic as BaaS to automatically identify the CAPTCHA type
and routes to the appropriate solver. Optionally accepts a specific type to solve.

Example (Auto-detection):

```
mutation SolveAuto {  
  goto(url: "https://protected.domain") {  
    status  
  }  
  
  solve {  
    found  
    solved  
    time  
    token  
  }  
}
```

Example (Specific type):

```
mutation SolveSpecific {  
  goto(url: "https://protected.domain") {  
    status  
  }  
  
  solve(type: recaptcha) {  
    found  
    solved  
    time  
    token  
  }  
}
```

```
solve(  
  type: CaptchaTypes  
  timeout: Float  
  wait: Boolean = true  
): CaptchaResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`solve.type`](#) ● [`CaptchaTypes`](/bql-schema/types/enums/captcha-types) enum[​](#solvetypecaptchatypes- "Direct link to solvetypecaptchatypes-")

An enum of the type of captcha to look for and solve. If not provided, auto-detection will be used.

#### [`solve.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#solvetimeoutfloat- "Direct link to solvetimeoutfloat-")

A time, in milliseconds, to wait for a captcha to appear. Only valid when wait = true.
If a captcha is found then this timer doesn't have an effect on timing-out the solve
Default timeout is 30 seconds, or 30000.

#### [`solve.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#solvewaitboolean- "Direct link to solvewaitboolean-")

Whether or not to wait for the Captcha to be present on the page

### Type[​](#type "Direct link to Type")

#### [`CaptchaResponse`](/bql-schema/types/objects/captcha-response) object[​](#captcharesponse- "Direct link to captcharesponse-")

Response returned after a captcha has been solved

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/stopSessionRecording

* * Operations* Mutations* stopSessionRecording

Open in ChatGPT

On this page

# stopSessionRecording

Stops the current session recording and processes the replay data, similar to closing the context. This mutation will stop RRWeb recording and upload the collected events.

**Usage Example:**

```
mutation StopRecording {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  stopSessionRecording {  
    success  
    error  
  }  
}
```

**Field Definition:**

```
stopSessionRecording: StopSessionRecordingResponse
```

### Type[​](#type "Direct link to Type")

#### [`StopSessionRecordingResponse`](/bql-schema/types/objects/stop-session-recording-response) object[​](#stopsessionrecordingresponse- "Direct link to stopsessionrecordingresponse-")

The response received after stopping session recording

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/switchToWindow

* * Operations* Mutations* switchToWindow

Open in ChatGPT

On this page

# switchToWindow

Switches context to a popup window matching specified criteria

```
switchToWindow(  
  url: String  
  title: String  
  newest: Boolean = false  
  timeout: Float = 5000  
  waitUntil: WaitUntilGoto  
): SwitchWindowResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`switchToWindow.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#switchtowindowurlstring- "Direct link to switchtowindowurlstring-")

URL pattern to match against window URLs (supports wildcards)

#### [`switchToWindow.title`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#switchtowindowtitlestring- "Direct link to switchtowindowtitlestring-")

Window title pattern to match

#### [`switchToWindow.newest`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#switchtowindownewestboolean- "Direct link to switchtowindownewestboolean-")

Whether to target most recently opened window

#### [`switchToWindow.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#switchtowindowtimeoutfloat- "Direct link to switchtowindowtimeoutfloat-")

Maximum time to wait for matching window (in milliseconds)

#### [`switchToWindow.waitUntil`](#) ● [`WaitUntilGoto`](/bql-schema/types/enums/wait-until-goto) enum[​](#switchtowindowwaituntilwaituntilgoto- "Direct link to switchtowindowwaituntilwaituntilgoto-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`SwitchWindowResponse`](/bql-schema/types/objects/switch-window-response) object[​](#switchwindowresponse- "Direct link to switchwindowresponse-")

Response from window switching operation

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/text

* * Operations* Mutations* text

Open in ChatGPT

On this page

# text

Returns the text content on the given page or by selector when specified

**Usage Example:**

```
mutation GetText {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  selector: text(selector: "h1") {  
      text  
  }  
  
  fullPage: text {  
    text  
  }  
}
```

**Field Definition:**

```
text(  
  timeout: Float  
  selector: String  
  visible: Boolean = false  
  clean: CleanInput  
): TextResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`text.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#texttimeoutfloat- "Direct link to texttimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the selector to appear, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`text.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#textselectorstring- "Direct link to textselectorstring-")

The DOM selector of the given element you want to return the text of

#### [`text.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#textvisibleboolean- "Direct link to textvisibleboolean-")

Whether or not to return the text content of the element only if it's visible

#### [`text.clean`](#) ● [`CleanInput`](/bql-schema/types/inputs/clean-input) input[​](#textcleancleaninput- "Direct link to textcleancleaninput-")

Specifies conditions for "cleaning" the returned text, useful for minimizing the amount of markup returned for cases like LLMs and more. See nested options for parameters.

### Type[​](#type "Direct link to Type")

#### [`TextResponse`](/bql-schema/types/objects/text-response) object[​](#textresponse- "Direct link to textresponse-")

Text content of a page

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/title

* * Operations* Mutations* title

Open in ChatGPT

On this page

# title

Returns the title of the page that the browser is currently at

**Usage Example:**

```
mutation GetTitle {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  title {  
    title  
  }  
}
```

**Field Definition:**

```
title: TitleResponse
```

### Type[​](#type "Direct link to Type")

#### [`TitleResponse`](/bql-schema/types/objects/title-response) object[​](#titleresponse- "Direct link to titleresponse-")

Response returned after the page's title has been set or get

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/type

* * Operations* Mutations* type

Open in ChatGPT

On this page

# type

Types text into an element by scrolling to it, clicking it, then emitting key events for every character

**Usage Example:**

```
mutation TypeText {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  type(  
    text: "Hello, World!"  
    selector: "input[type='text']"  
  ) {  
    time  
  }  
}
```

**Field Definition:**

```
type(  
  text: String!  
  selector: String!  
  delay: [Int] = [50, 200]  
  interactable: Boolean = true  
  scroll: Boolean = true  
  timeout: Float  
  visible: Boolean = false  
  wait: Boolean = true  
): TypeResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`type.text`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#typetextstring-- "Direct link to typetextstring--")

The text content you want to type into the element

#### [`type.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#typeselectorstring-- "Direct link to typeselectorstring--")

The CSS selector of the element on the page you want to type text into

#### [`type.delay`](#) ● [`[Int]`](/bql-schema/types/scalars/int) list scalar[​](#typedelayint-- "Direct link to typedelayint--")

The amount of delay between keystrokes in milliseconds. Values are used as a range and chosen at random

#### [`type.interactable`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#typeinteractableboolean- "Direct link to typeinteractableboolean-")

Whether or not to check if element can be interacted with by hovering over it and seeing if the element
is available at that x and y position

#### [`type.scroll`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#typescrollboolean- "Direct link to typescrollboolean-")

Whether or not to scroll to the element prior to typing, defaults to true

#### [`type.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#typetimeoutfloat- "Direct link to typetimeoutfloat-")

How long to wait for the element to appear before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`type.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#typevisibleboolean- "Direct link to typevisibleboolean-")

Whether or not to type into the element only if it's visible

#### [`type.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#typewaitboolean- "Direct link to typewaitboolean-")

Whether or not to wait for the element to present in the DOM

### Type[​](#type "Direct link to Type")

#### [`TypeResponse`](/bql-schema/types/objects/type-response) object[​](#typeresponse- "Direct link to typeresponse-")

Response returned after having typed into an element

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/url

* * Operations* Mutations* url

Open in ChatGPT

On this page

# url

Returns the URL of the page that the browser is currently at

**Usage Example:**

```
mutation GetURL {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  url {  
    url  
  }  
}
```

**Field Definition:**

```
url: URLResponse
```

### Type[​](#type "Direct link to Type")

#### [`URLResponse`](/bql-schema/types/objects/urlresponse) object[​](#urlresponse- "Direct link to urlresponse-")

Response returned after the URL of the page has been set or get

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/userAgent

* * Operations* Mutations* userAgent

Open in ChatGPT

On this page

# userAgent

Sets the User-Agent string for the browser session

**Usage Example:**

```
mutation SetUserAgent {  
  userAgent(userAgent: "Mozilla/5.0 (iPhone; CPU iPhone OS 14_6 like Mac OS X) AppleWebKit/605.1.15") {  
    userAgent  
    time  
  }  
  goto(url: "https://example.com") {  
    status  
  }  
}
```

**Field Definition:**

```
userAgent(  
  userAgent: String!  
): UserAgentResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`userAgent.userAgent`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#useragentuseragentstring-- "Direct link to useragentuseragentstring--")

The User-Agent string to set for the browser session

### Type[​](#type "Direct link to Type")

#### [`UserAgentResponse`](/bql-schema/types/objects/user-agent-response) object[​](#useragentresponse- "Direct link to useragentresponse-")

The response returned after setting the User-Agent

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/verify

* * Operations* Mutations* verify

Open in ChatGPT

On this page

# verify

🚨 **EXPERIMENTAL** 🚨
Clicks a verification button to assert human-like

**Usage Example:**

```
mutation VerifyCaptcha {  
  goto(url: "https://protected.domain") {  
    status  
  }  
  
  verify(type: cloudflare) {  
    found  
    solved  
    time  
  }  
}
```

**Field Definition:**

```
verify(  
  type: VerifyTypes!  
  timeout: Float  
  wait: Boolean = true  
): CaptchaResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`verify.type`](#) ● [`VerifyTypes!`](/bql-schema/types/enums/verify-types) non-null enum[​](#verifytypeverifytypes-- "Direct link to verifytypeverifytypes--")

An enum of the type of captcha to look for and solve

#### [`verify.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#verifytimeoutfloat- "Direct link to verifytimeoutfloat-")

A time, in milliseconds, to wait for a verification to appear. Only valid when wait = true. Default timeout is 30 seconds, or 30000.

#### [`verify.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#verifywaitboolean- "Direct link to verifywaitboolean-")

Whether or not to wait for the verification to be present on the page

### Type[​](#type "Direct link to Type")

#### [`CaptchaResponse`](/bql-schema/types/objects/captcha-response) object[​](#captcharesponse- "Direct link to captcharesponse-")

Response returned after a captcha has been solved

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/viewport

* * Operations* Mutations* viewport

Open in ChatGPT

On this page

# viewport

Sets the viewport dimensions for the browser session

**Usage Example:**

```
mutation SetViewport {  
  viewport(width: 1920, height: 1080) {  
    width  
    height  
    time  
  }  
}
```

**Mobile device simulation:**

```
mutation MobileViewport {  
  viewport(width: 375, height: 667, deviceScaleFactor: 1, mobile: true) {  
    width  
    height  
    deviceScaleFactor  
    mobile  
    time  
  }  
}
```

**Desktop simulation:**

```
mutation DesktopViewport {  
  viewport(width: 1920, height: 1080, mobile: false) {  
    width  
    height  
    mobile  
    time  
  }  
}
```

**Field Definition:**

```
viewport(  
  width: Float!  
  height: Float!  
  deviceScaleFactor: Float = 1  
  mobile: Boolean = false  
): ViewportResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`viewport.width`](#) ● [`Float!`](/bql-schema/types/scalars/float) non-null scalar[​](#viewportwidthfloat-- "Direct link to viewportwidthfloat--")

The width of the viewport in pixels

#### [`viewport.height`](#) ● [`Float!`](/bql-schema/types/scalars/float) non-null scalar[​](#viewportheightfloat-- "Direct link to viewportheightfloat--")

The height of the viewport in pixels

#### [`viewport.deviceScaleFactor`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#viewportdevicescalefactorfloat- "Direct link to viewportdevicescalefactorfloat-")

The device scale factor, defaults to 1

#### [`viewport.mobile`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#viewportmobileboolean- "Direct link to viewportmobileboolean-")

Whether to simulate a mobile device, defaults to false

### Type[​](#type "Direct link to Type")

#### [`ViewportResponse`](/bql-schema/types/objects/viewport-response) object[​](#viewportresponse- "Direct link to viewportresponse-")

Response returned after setting the viewport

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/waitForNavigation

* * Operations* Mutations* waitForNavigation

Open in ChatGPT

On this page

# waitForNavigation

Waits for a navigation even to fire, useful for clicking an element and waiting for a page load of some

**Usage Example:**

```
mutation WaitForNavigation {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  waitForNavigation(waitUntil: load) {  
    status  
  }  
}
```

**Field Definition:**

```
waitForNavigation(  
  timeout: Float  
  waitUntil: WaitUntilGoto = load  
): HTTPResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`waitForNavigation.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitfornavigationtimeoutfloat- "Direct link to waitfornavigationtimeoutfloat-")

The maximum amount of time, in milliseconds, to wait for the page to load, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`waitForNavigation.waitUntil`](#) ● [`WaitUntilGoto`](/bql-schema/types/enums/wait-until-goto) enum[​](#waitfornavigationwaituntilwaituntilgoto- "Direct link to waitfornavigationwaituntilwaituntilgoto-")

When to consider the page fully-loaded and proceed with further execution

### Type[​](#type "Direct link to Type")

#### [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#httpresponse- "Direct link to httpresponse-")

Response returned after a navigation event

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/waitForRequest

* * Operations* Mutations* waitForRequest

Open in ChatGPT

On this page

# waitForRequest

Waits for the browser to make a particular request

**Usage Example:**

```
mutation WaitForRequest {  
  goto(url: "https://browserless.io") {  
    status  
  }  
  
  waitForRequest(method: GET) {  
    time  
  }  
}
```

**Field Definition:**

```
waitForRequest(  
  method: Method  
  timeout: Float  
  url: String  
): WaitForRequest
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`waitForRequest.method`](#) ● [`Method`](/bql-schema/types/enums/method) enum[​](#waitforrequestmethodmethod- "Direct link to waitforrequestmethodmethod-")

The method of the request to wait for

#### [`waitForRequest.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforrequesttimeoutfloat- "Direct link to waitforrequesttimeoutfloat-")

How long to wait for the request to be made before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`waitForRequest.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#waitforrequesturlstring- "Direct link to waitforrequesturlstring-")

The pattern of the request URL to wait for, using glob-style pattern-matching

### Type[​](#type "Direct link to Type")

#### [`WaitForRequest`](/bql-schema/types/objects/wait-for-request) object[​](#waitforrequest- "Direct link to waitforrequest-")

Response returned after a particular network request has been sent

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/waitForResponse

* * Operations* Mutations* waitForResponse

Open in ChatGPT

On this page

# waitForResponse

Waits for a particular network response to be made back to the browser

**Usage Example:**

```
mutation WaitForResponse {  
  goto(url: "https://browserless.io") {  
    status  
  }  
  
  waitForResponse(codes: [200]) {  
    time  
  }  
}
```

**Field Definition:**

```
waitForResponse(  
  codes: [Int]  
  statuses: [Int]  
  url: String  
): WaitForResponse
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`waitForResponse.codes`](#) ● [`[Int]`](/bql-schema/types/scalars/int) deprecated list scalar[​](#waitforresponsecodesint--- "Direct link to waitforresponsecodesint---")

DEPRECATED

Use `statuses` field instead as it is more consistent in BrowserQL.

The HTTP Response code(s) of the URL to wait for. Can be a single HTTP code or a list of desired codes

#### [`waitForResponse.statuses`](#) ● [`[Int]`](/bql-schema/types/scalars/int) list scalar[​](#waitforresponsestatusesint-- "Direct link to waitforresponsestatusesint--")

The HTTP Response code(s) of the URL to wait for. Can be a single HTTP code or a list of desired codes

#### [`waitForResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#waitforresponseurlstring- "Direct link to waitforresponseurlstring-")

The pattern of the response URL to wait for, using glob-style pattern-matching

### Type[​](#type "Direct link to Type")

#### [`WaitForResponse`](/bql-schema/types/objects/wait-for-response) object[​](#waitforresponse- "Direct link to waitforresponse-")

Response returned after a particular network response has been received

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/waitForSelector

* * Operations* Mutations* waitForSelector

Open in ChatGPT

On this page

# waitForSelector

Waits for a given selector to be present in the DOM, with optional visibility

**Usage Example:**

```
mutation WaitForSelector {  
  goto(url: "https://example.com") {  
    status  
  }  
  
  waitForSelector(selector: "h1") {  
    time  
  }  
}
```

**Field Definition:**

```
waitForSelector(  
  selector: String!  
  timeout: Float  
  visible: Boolean = false  
): WaitForSelector
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`waitForSelector.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#waitforselectorselectorstring-- "Direct link to waitforselectorselectorstring--")

The selector to wait for until present in the DOM

#### [`waitForSelector.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectortimeoutfloat- "Direct link to waitforselectortimeoutfloat-")

When waiting for a selector applies a timeout to wait for in milliseconds, overriding any defaults. Default timeout is 30 seconds, or 30000.

#### [`waitForSelector.visible`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#waitforselectorvisibleboolean- "Direct link to waitforselectorvisibleboolean-")

Whether or not to consider the element as present only if it's visible

### Type[​](#type "Direct link to Type")

#### [`WaitForSelector`](/bql-schema/types/objects/wait-for-selector) object[​](#waitforselector- "Direct link to waitforselector-")

Response returned after a particular selector has been found in the DOM

---

## Source: https://docs.browserless.io/bql-schema/operations/mutations/waitForTimeout

* * Operations* Mutations* waitForTimeout

Open in ChatGPT

On this page

# waitForTimeout

Wait for a period of time, defined in milliseconds

**Usage Example:**

```
mutation WaitForTimeout {  
  waitForTimeout(time: 1000) {  
    time  
  }  
}
```

**Field Definition:**

```
waitForTimeout(  
  time: Float!  
): WaitForTimeout
```

### Arguments[​](#arguments "Direct link to Arguments")

#### [`waitForTimeout.time`](#) ● [`Float!`](/bql-schema/types/scalars/float) non-null scalar[​](#waitfortimeouttimefloat-- "Direct link to waitfortimeouttimefloat--")

The amount of time to wait for, in milliseconds

### Type[​](#type "Direct link to Type")

#### [`WaitForTimeout`](/bql-schema/types/objects/wait-for-timeout) object[​](#waitfortimeout- "Direct link to waitfortimeout-")

Response returned after having waited for a selector to appear in the DOM