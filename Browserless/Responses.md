# Responses

This page presents reference for all mutations responses.

## CaptchaResponse​

Represents the response structure for solving a captcha.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The total time it took to find and solve the captcha. |
| found | Boolean | Indicates if a captcha was found. |
| solved | Boolean | Indicates if a captcha was found and solved. |
| token | String | The solved token of the captcha response, if any is provided. |

## ClickResponse​

Represents the response structure for clicking on an element.

| Field | Type | Description |
| --- | --- | --- |
| selector | String | The selector text of the clicked element, if specified. |
| x | Float | The x-coordinate of the click, in pixels, on the page. |
| y | Float | The y-coordinate of the click, in pixels, on the page. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of clicking to completion. |

## CookieResponse​

Represents the response structure for setting and retrieving cookies.

| Field | Type | Description |
| --- | --- | --- |
| cookies | [StandardCookie] | A standard cookie object with the values of the set cookies. |
| time | Float | The time it took to set the cookies. |

## DefaultResponse​

Represents the default response structure for methods.

| Field | Type | Description |
| --- | --- | --- |
| timeout | Float | The default timeout for all methods. |

## EvaluateResponse​

Represents the response structure for evaluating a script in the browser.

| Field | Type | Description |
| --- | --- | --- |
| value | String | The returned value of the script, if any. |
| time | Float | The time it took for the evaluate call to complete. |

## HTMLResponse​

Represents the response structure for retrieving a page's HTML content.

| Field | Type | Description |
| --- | --- | --- |
| html | String | The content of the page's HTML. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of content retrieval to completion. |

## HTTPResponse​

Represents the HTTP response structure for a page load.

| Field | Type | Description |
| --- | --- | --- |
| status | Int | The status code of the response from the initial page load. |
| text | String | The status text of the response from the initial page load, generally "ok". |
| url | String | The final URL of the page after any potential redirects or URL rewrites. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of navigation to completion. |

## HoverResponse​

Represents the response structure for hovering over an element.

| Field | Type | Description |
| --- | --- | --- |
| selector | String | The selector text of the hovered element. |
| x | Float | The x-coordinate in pixels, on the page. |
| y | Float | The y-coordinate in pixels, on the page. |
| time | Float | The amount of time, in milliseconds, elapsed since the start to completion. |

## JavaScriptResponse​

Represents the response structure for enabling or disabling JavaScript on a page.

| Field | Type | Description |
| --- | --- | --- |
| enabled | Boolean | Whether JavaScript is enabled on the page. |
| time | Float | The time it took to perform this action. |

## PDFResponse​

Represents the response structure for generating a PDF.

| Field | Type | Description |
| --- | --- | --- |
| base64 | String | Base64 encoded PDF content. |
| size | Float | The size of the resulting PDF in bytes. |
| time | Float | The time it took to generate the PDF. |

## QuerySelectorResponse​

Represents the response structure for querying an element using `querySelector`.

| Field | Type | Description |
| --- | --- | --- |
| id | String | The element's identifier, reflecting the id global attribute. |
| childElementCount | Float | The number of child elements of this element. |
| className | String | The value of the class attribute of the specified element. |
| innerHTML | String | The HTML or XML markup contained within the element. |
| innerText | String | The text contained within the element. |
| localName | String | The local part of the qualified name of the element. |
| outerHTML | String | The serialized HTML fragment describing the element and its descendants. |

## ReconnectionResponse​

Represents the response structure for reconnecting to a browser session.

| Field | Type | Description |
| --- | --- | --- |
| browserQLEndpoint | String | The fully-qualified URL to reconnect future BrowserQL sessions. Token information might be required. |
| browserWSEndpoint | String | The fully-qualified URL of the browserWSEndpoint for use with libraries like Playwright or Puppeteer. Token information might be required. |
| devtoolsFrontendUrl | String | The fully-qualified URL of the devtools resources for remotely loading Chrome's developer tools. |
| webSocketDebuggerUrl | String | The underlying page's WebSocketDebuggerUrl for libraries that operate on a page rather than a browser object. |

## ScrollResponse​

Represents the response structure for scrolling to an element or coordinate.

| Field | Type | Description |
| --- | --- | --- |
| selector | String | The CSS selector of the element on the page scrolled to. |
| x | Float | The x-coordinate, in pixels, to scroll to. |
| y | Float | The y-coordinate, in pixels, to scroll to. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of scrolling to completion. |

## ScreenshotResponse​

Represents the response structure for taking a screenshot.

| Field | Type | Description |
| --- | --- | --- |
| base64 | String | The base64 encoded image of the screenshot. |
| format | String | The format of the screenshot. |
| time | Float | The time it took to take the screenshot. |

## SelectResponse​

Represents the response structure for selecting a value from a dropdown or multiple select element.

| Field | Type | Description |
| --- | --- | --- |
| selector | String | The selector of the element you selected from. |
| value | StringOrArray | The value or values you selected from the select element. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of selecting to completion. |

## TextResponse​

Represents the response structure for retrieving the textual content of a page.

| Field | Type | Description |
| --- | --- | --- |
| text | String | The textual content of the page. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of text retrieval to completion. |

## TitleResponse​

Represents the response structure for retrieving the title of the current page.

| Field | Type | Description |
| --- | --- | --- |
| title | String | The title of the current page. |

## TypeResponse​

Represents the response structure for typing text into an element.

| Field | Type | Description |
| --- | --- | --- |
| selector | String | The selector of the element you typed into. |
| text | String | The textual content that was typed. |
| x | Float | The x-coordinate of the element, in pixels, on the page. |
| y | Float | The y-coordinate of the element, in pixels, on the page. |
| time | Float | The amount of time, in milliseconds, elapsed since the start of typing to completion. |

## URLResponse​

Represents the response structure for retrieving the URL of the current page.

| Field | Type | Description |
| --- | --- | --- |
| url | String | The URL of the current page. |

## VerifyResponse​

Represents the response structure for a verification action.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The total time it took to find and click the verification. |
| found | Boolean | Indicates if a verification was found. |
| solved | Boolean | Indicates if a verification was found and clicked. |

## WaitForRequest​

Represents the response structure for waiting for a specific request.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The period of time elapsed, in milliseconds, waited for. |
| url | String | The URL parameter used to match the response with. |

## WaitForResponse​

Represents the response structure for waiting for a specific response.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The period of time elapsed, in milliseconds, waited for. |
| status | Int | The status code of the response. |
| url | String | The URL parameter used to match the response with. |

## WaitForSelector​

Represents the response structure for waiting for a selector.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The period of time elapsed, in milliseconds, waited for. |
| selector | String | The selector waited for. |
| x | Float | The x-coordinate position, in pixels, left of the viewport. |
| y | Float | The y-coordinate position, in pixels, top of the viewport. |
| width | Float | The width, in pixels, of the element. |
| height | Float | The height, in pixels, of the element. |

## WaitForTimeout​

Represents the response structure for waiting a specified period.

| Field | Type | Description |
| --- | --- | --- |
| time | Float | The period of time elapsed, in milliseconds, waited for. |