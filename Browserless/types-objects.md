# Browserless Objects Documentation



---

## Object: Attribute
Source: https://docs.browserless.io/bql-schema/types/objects/attribute

* * Types* Objects* Attribute

Open in ChatGPT

On this page

# Attribute

No description

```
type Attribute {  
  name: String  
  value: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`Attribute.name`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#attributenamestring- "Direct link to attributenamestring-")

#### [`Attribute.value`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#attributevaluestring- "Direct link to attributevaluestring-")

### Member Of[​](#member-of "Direct link to Member Of")

[`MapSelectorResponse`](/bql-schema/types/objects/map-selector-response) object

---

## Object: CaptchaResponse
Source: https://docs.browserless.io/bql-schema/types/objects/captcha-response

* * Types* Objects* CaptchaResponse

Open in ChatGPT

On this page

# CaptchaResponse

Response returned after a captcha has been solved

```
type CaptchaResponse {  
  found: Boolean  
  solved: Boolean  
  time: Float  
  token: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`CaptchaResponse.found`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#captcharesponsefoundboolean- "Direct link to captcharesponsefoundboolean-")

If a captcha was found or not

#### [`CaptchaResponse.solved`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#captcharesponsesolvedboolean- "Direct link to captcharesponsesolvedboolean-")

If a captcha was found, whether or not it was solved

#### [`CaptchaResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#captcharesponsetimefloat- "Direct link to captcharesponsetimefloat-")

The total time it took to find, and solve, the captcha

#### [`CaptchaResponse.token`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#captcharesponsetokenstring- "Direct link to captcharesponsetokenstring-")

The solved token of the response, if any is provided

### Returned By[​](#returned-by "Direct link to Returned By")

[`solve`](/bql-schema/operations/mutations/solve) mutation ● [`verify`](/bql-schema/operations/mutations/verify) mutation

---

## Object: ClickResponse
Source: https://docs.browserless.io/bql-schema/types/objects/click-response

* * Types* Objects* ClickResponse

Open in ChatGPT

On this page

# ClickResponse

Response returned after having clicked on an element

```
type ClickResponse {  
  selector: String  
  time: Float  
  x: Float  
  y: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ClickResponse.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#clickresponseselectorstring- "Direct link to clickresponseselectorstring-")

The selector text if specified

#### [`ClickResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#clickresponsetimefloat- "Direct link to clickresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of clicking to completion

#### [`ClickResponse.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#clickresponsexfloat- "Direct link to clickresponsexfloat-")

The X coordinate of the click, in pixels, on the page

#### [`ClickResponse.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#clickresponseyfloat- "Direct link to clickresponseyfloat-")

The Y coordinate of the click, in pixels, on the page

### Returned By[​](#returned-by "Direct link to Returned By")

[`checkbox`](/bql-schema/operations/mutations/checkbox) mutation ● [`click`](/bql-schema/operations/mutations/click) mutation

---

## Object: CookieResponse
Source: https://docs.browserless.io/bql-schema/types/objects/cookie-response

* * Types* Objects* CookieResponse

Open in ChatGPT

On this page

# CookieResponse

The response returned after setting or getting cookies

```
type CookieResponse {  
  cookies: [StandardCookie]  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`CookieResponse.cookies`](#) ● [`[StandardCookie]`](/bql-schema/types/objects/standard-cookie) list object[​](#cookieresponsecookiesstandardcookie-- "Direct link to cookieresponsecookiesstandardcookie--")

A standard cookie object with the values of the set cookies

#### [`CookieResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#cookieresponsetimefloat- "Direct link to cookieresponsetimefloat-")

The time it took to set and return the cookies

### Returned By[​](#returned-by "Direct link to Returned By")

[`cookies`](/bql-schema/operations/mutations/cookies) mutation

---

## Object: DefaultResponse
Source: https://docs.browserless.io/bql-schema/types/objects/default-response

* * Types* Objects* DefaultResponse

Open in ChatGPT

On this page

# DefaultResponse

Default response for all methods

```
type DefaultResponse {  
  timeout: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`DefaultResponse.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#defaultresponsetimeoutfloat- "Direct link to defaultresponsetimeoutfloat-")

The default timeout for all methods. Default timeout is 30 seconds, or 30000.

### Returned By[​](#returned-by "Direct link to Returned By")

[`preferences`](/bql-schema/operations/mutations/preferences) mutation

---

## Object: EvaluateResponse
Source: https://docs.browserless.io/bql-schema/types/objects/evaluate-response

* * Types* Objects* EvaluateResponse

Open in ChatGPT

On this page

# EvaluateResponse

Response returned after evaluating a script

```
type EvaluateResponse {  
  time: Float  
  value: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`EvaluateResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#evaluateresponsetimefloat- "Direct link to evaluateresponsetimefloat-")

The time it took for the evaluate call to happen

#### [`EvaluateResponse.value`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#evaluateresponsevaluestring- "Direct link to evaluateresponsevaluestring-")

The returned value of the script, if any

### Returned By[​](#returned-by "Direct link to Returned By")

[`evaluate`](/bql-schema/operations/mutations/evaluate) mutation

---

## Object: Headers
Source: https://docs.browserless.io/bql-schema/types/objects/headers

* * Types* Objects* Headers

Open in ChatGPT

On this page

# Headers

An object representing the header's name and underlying value

```
type Headers {  
  name: String  
  value: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`Headers.name`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#headersnamestring- "Direct link to headersnamestring-")

#### [`Headers.value`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#headersvaluestring- "Direct link to headersvaluestring-")

### Member Of[​](#member-of "Direct link to Member Of")

[`RequestResponse`](/bql-schema/types/objects/request-response) object ● [`ResponseResponse`](/bql-schema/types/objects/response-response) object

---

## Object: HoverResponse
Source: https://docs.browserless.io/bql-schema/types/objects/hover-response

* * Types* Objects* HoverResponse

Open in ChatGPT

On this page

# HoverResponse

Response returned after having hovered over an element

```
type HoverResponse {  
  selector: String  
  time: Float  
  x: Float  
  y: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`HoverResponse.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#hoverresponseselectorstring- "Direct link to hoverresponseselectorstring-")

The selector text

#### [`HoverResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hoverresponsetimefloat- "Direct link to hoverresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start to completion

#### [`HoverResponse.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hoverresponsexfloat- "Direct link to hoverresponsexfloat-")

The X coordinate in pixels, on the page

#### [`HoverResponse.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#hoverresponseyfloat- "Direct link to hoverresponseyfloat-")

The Y coordinate in pixels, on the page

### Returned By[​](#returned-by "Direct link to Returned By")

[`hover`](/bql-schema/operations/mutations/hover) mutation

---

## Object: HTMLResponse
Source: https://docs.browserless.io/bql-schema/types/objects/html-response

* * Types* Objects* HTMLResponse

Open in ChatGPT

On this page

# HTMLResponse

HTML content of a page

```
type HTMLResponse {  
  html: String  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`HTMLResponse.html`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#htmlresponsehtmlstring- "Direct link to htmlresponsehtmlstring-")

The content of the page's HTML

#### [`HTMLResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#htmlresponsetimefloat- "Direct link to htmlresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of content retrieval to completion

### Returned By[​](#returned-by "Direct link to Returned By")

[`html`](/bql-schema/operations/mutations/html) mutation

---

## Object: HTTPHeadersResponse
Source: https://docs.browserless.io/bql-schema/types/objects/http-headers-response

Error: 404 Client Error: Not Found for url: https://docs.browserless.io/bql-schema/types/objects/HTTPHeadersResponse


---

## Object: HTTPHeaders
Source: https://docs.browserless.io/bql-schema/types/objects/http-headers

* * Types* Objects* HTTPHeaders

Open in ChatGPT

On this page

# HTTPHeaders

An object representing the header's name and underlying value

```
type HTTPHeaders {  
  name: String  
  value: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`HTTPHeaders.name`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#httpheadersnamestring- "Direct link to httpheadersnamestring-")

#### [`HTTPHeaders.value`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#httpheadersvaluestring- "Direct link to httpheadersvaluestring-")

### Member Of[​](#member-of "Direct link to Member Of")

[`HTTPHeadersResponse`](/bql-schema/types/objects/httpheaders-response) object

---

## Object: HTTPResponse
Source: https://docs.browserless.io/bql-schema/types/objects/http-response

* * Types* Objects* HTTPResponse

Open in ChatGPT

On this page

# HTTPResponse

Response returned after a navigation event

```
type HTTPResponse {  
  status: Int  
  time: Float  
  text: String  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`HTTPResponse.status`](#) ● [`Int`](/bql-schema/types/scalars/int) scalar[​](#httpresponsestatusint- "Direct link to httpresponsestatusint-")

The status code response of the initial page-load

#### [`HTTPResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#httpresponsetimefloat- "Direct link to httpresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of navigation to completion

#### [`HTTPResponse.text`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#httpresponsetextstring- "Direct link to httpresponsetextstring-")

The status text of the response from the initial page-load. Generally 'ok'

#### [`HTTPResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#httpresponseurlstring- "Direct link to httpresponseurlstring-")

The final URL of the page after any potential redirects or URL rewrites

### Returned By[​](#returned-by "Direct link to Returned By")

[`back`](/bql-schema/operations/mutations/back) mutation ● [`content`](/bql-schema/operations/mutations/content) mutation ● [`forward`](/bql-schema/operations/mutations/forward) mutation ● [`goto`](/bql-schema/operations/mutations/goto) mutation ● [`reload`](/bql-schema/operations/mutations/reload) mutation ● [`waitForNavigation`](/bql-schema/operations/mutations/wait-for-navigation) mutation

### Member Of[​](#member-of "Direct link to Member Of")

[`SwitchWindowResponse`](/bql-schema/types/objects/switch-window-response) object

---

## Object: JavaScriptResponse
Source: https://docs.browserless.io/bql-schema/types/objects/java-script-response

* * Types* Objects* JavaScriptResponse

Open in ChatGPT

On this page

# JavaScriptResponse

The response returned after enabling or disabling JavaScript on the page

```
type JavaScriptResponse {  
  enabled: Boolean  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`JavaScriptResponse.enabled`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#javascriptresponseenabledboolean- "Direct link to javascriptresponseenabledboolean-")

Whether or not JavaScript is enabled on the page

#### [`JavaScriptResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#javascriptresponsetimefloat- "Direct link to javascriptresponsetimefloat-")

The time it took to perform this action

### Returned By[​](#returned-by "Direct link to Returned By")

[`javaScriptEnabled`](/bql-schema/operations/mutations/java-script-enabled) mutation

---

## Object: LiveURLResponse
Source: https://docs.browserless.io/bql-schema/types/objects/live-url-response

Error: 404 Client Error: Not Found for url: https://docs.browserless.io/bql-schema/types/objects/LiveURLResponse


---

## Object: MapSelectorResponse
Source: https://docs.browserless.io/bql-schema/types/objects/map-selector-response

* * Types* Objects* MapSelectorResponse

Open in ChatGPT

On this page

# MapSelectorResponse

Response returned from a Map Selector

```
type MapSelectorResponse {  
  innerHTML: String  
  innerText: String  
  id: String  
  class: [String]  
  attribute(  
    name: String  
  ): Attribute  
  mapSelector(  
    selector: String!  
    timeout: Float  
    wait: Boolean = true  
  ): [MapSelectorResponse]  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`MapSelectorResponse.innerHTML`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#mapselectorresponseinnerhtmlstring- "Direct link to mapselectorresponseinnerhtmlstring-")

The innerHTML of the selected DOM Node

#### [`MapSelectorResponse.innerText`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#mapselectorresponseinnertextstring- "Direct link to mapselectorresponseinnertextstring-")

The innerText of the selected DOM Node, eg, the raw textual content

#### [`MapSelectorResponse.id`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#mapselectorresponseidstring- "Direct link to mapselectorresponseidstring-")

The ID attribute's value, if any, of the node

#### [`MapSelectorResponse.class`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#mapselectorresponseclassstring-- "Direct link to mapselectorresponseclassstring--")

The class attribute's value, if any, of the node represented as an array of strings

#### [`MapSelectorResponse.attribute`](#) ● [`Attribute`](/bql-schema/types/objects/attribute) object[​](#mapselectorresponseattributeattribute- "Direct link to mapselectorresponseattributeattribute-")

Retrieve an attribute by the name of the attribute itself, eg, "data-test-id"

##### [`MapSelectorResponse.attribute.name`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#mapselectorresponseattributenamestring- "Direct link to mapselectorresponseattributenamestring-")

#### [`MapSelectorResponse.mapSelector`](#) ● [`[MapSelectorResponse]`](/bql-schema/types/objects/map-selector-response) list object[​](#mapselectorresponsemapselectormapselectorresponse-- "Direct link to mapselectorresponsemapselectormapselectorresponse--")

You can further map nested DOM nodes as well. For instance, given a parent ".product" node, you can map further nodes like ".price" or ".shipping" as examples. This will give you items appropriately nested by their parent node for better hierarchical representation of data

##### [`MapSelectorResponse.mapSelector.selector`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#mapselectorresponsemapselectorselectorstring-- "Direct link to mapselectorresponsemapselectorselectorstring--")

A query-selector-al compatible string, or JavaScript code that returns an DOM NodeList. Examples include:

* All `<button />` Elements:
  `selector: "button"`
* A JavaScript snippet that returns a button element
  `selector: "document.querySelectorAll('button')"`

##### [`MapSelectorResponse.mapSelector.timeout`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#mapselectorresponsemapselectortimeoutfloat- "Direct link to mapselectorresponsemapselectortimeoutfloat-")

How long to wait for the element to appear before timing out, overriding any defaults. Default timeout is 30 seconds, or 30000.

##### [`MapSelectorResponse.mapSelector.wait`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#mapselectorresponsemapselectorwaitboolean- "Direct link to mapselectorresponsemapselectorwaitboolean-")

Whether or not to wait for the selectors to present in the DOM

### Returned By[​](#returned-by "Direct link to Returned By")

[`mapSelector`](/bql-schema/operations/mutations/map-selector) mutation

### Member Of[​](#member-of "Direct link to Member Of")

[`MapSelectorResponse`](/bql-schema/types/objects/map-selector-response) object

---

## Object: Mutation
Source: https://docs.browserless.io/bql-schema/types/objects/mutation

* * Types* Objects* Mutation

Open in ChatGPT

# Mutation

This document is a complete technical specification of every mutation in the BrowserQL API. To get you started, the ones you'll use most will probably include:

* [goto](/bql-schema/operations/mutations/goto)
* [reject](/bql-schema/operations/mutations/reject)
* [proxy](/bql-schema/operations/mutations/proxy)
* [click](/bql-schema/operations/mutations/click)
* [type](/bql-schema/operations/mutations/type)
* [html](/bql-schema/operations/mutations/html)
* [reconnect](/bql-schema/operations/mutations/reconnect)

---

## Object: PDFResponse
Source: https://docs.browserless.io/bql-schema/types/objects/pdf-response

* * Types* Objects* PDFResponse

Open in ChatGPT

On this page

# PDFResponse

The response returned after generating a PDF

```
type PDFResponse {  
  base64: String  
  size: Float  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`PDFResponse.base64`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#pdfresponsebase64string- "Direct link to pdfresponsebase64string-")

Base64 encoded PDF content

#### [`PDFResponse.size`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#pdfresponsesizefloat- "Direct link to pdfresponsesizefloat-")

The size of the resulting PDF in bytes

#### [`PDFResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#pdfresponsetimefloat- "Direct link to pdfresponsetimefloat-")

The time it took to generate the PDF

### Returned By[​](#returned-by "Direct link to Returned By")

[`pdf`](/bql-schema/operations/mutations/pdf) mutation

---

## Object: ProxyResponse
Source: https://docs.browserless.io/bql-schema/types/objects/proxy-response

* * Types* Objects* ProxyResponse

Open in ChatGPT

On this page

# ProxyResponse

Response returned after setting up the proxy patterns

```
type ProxyResponse {  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ProxyResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#proxyresponsetimefloat- "Direct link to proxyresponsetimefloat-")

### Returned By[​](#returned-by "Direct link to Returned By")

[`proxy`](/bql-schema/operations/mutations/proxy) mutation

---

## Object: QuerySelectorResponse
Source: https://docs.browserless.io/bql-schema/types/objects/query-selector-response

* * Types* Objects* QuerySelectorResponse

Open in ChatGPT

On this page

# QuerySelectorResponse

The response returned after querying the page for a selector

```
type QuerySelectorResponse {  
  childElementCount: Float  
  className: String  
  id: String  
  innerHTML: String  
  innerText: String  
  localName: String  
  outerHTML: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`QuerySelectorResponse.childElementCount`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#queryselectorresponsechildelementcountfloat- "Direct link to queryselectorresponsechildelementcountfloat-")

The Element.childElementCount read-only property returns the number of child elements of this element

#### [`QuerySelectorResponse.className`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponseclassnamestring- "Direct link to queryselectorresponseclassnamestring-")

The className property of the Element interface gets and sets the value of the class attribute of the specified element

#### [`QuerySelectorResponse.id`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponseidstring- "Direct link to queryselectorresponseidstring-")

The id property of the Element interface represents the element's identifier, reflecting the id global attribute

#### [`QuerySelectorResponse.innerHTML`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponseinnerhtmlstring- "Direct link to queryselectorresponseinnerhtmlstring-")

The Element property innerHTML gets the HTML or XML markup contained within the element

#### [`QuerySelectorResponse.innerText`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponseinnertextstring- "Direct link to queryselectorresponseinnertextstring-")

The Element property innerText gets the text contained within the element

#### [`QuerySelectorResponse.localName`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponselocalnamestring- "Direct link to queryselectorresponselocalnamestring-")

The Element.localName read-only property returns the local part of the qualified name of an element

#### [`QuerySelectorResponse.outerHTML`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#queryselectorresponseouterhtmlstring- "Direct link to queryselectorresponseouterhtmlstring-")

The outerHTML attribute of the Element DOM interface gets the serialized HTML fragment describing the element including its descendants. It can also be set to replace the element with nodes parsed from the given string

### Returned By[​](#returned-by "Direct link to Returned By")

[`querySelector`](/bql-schema/operations/mutations/query-selector) mutation ● [`querySelectorAll`](/bql-schema/operations/mutations/query-selector-all) mutation

---

## Object: ReconnectionResponse
Source: https://docs.browserless.io/bql-schema/types/objects/reconnection-response

* * Types* Objects* ReconnectionResponse

Open in ChatGPT

On this page

# ReconnectionResponse

The response received after attempting to reconnect a BrowserQL session

```
type ReconnectionResponse {  
  browserQLEndpoint: String  
  browserWSEndpoint: String  
  devtoolsFrontendUrl: String  
  webSocketDebuggerUrl: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ReconnectionResponse.browserQLEndpoint`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#reconnectionresponsebrowserqlendpointstring- "Direct link to reconnectionresponsebrowserqlendpointstring-")

The fully-qualified URL to reconnect future BrowserQL sessions, eg: <https://chrome.browserless.io/bql/$id>. Please note that token information is not returned by this API and might be required

#### [`ReconnectionResponse.browserWSEndpoint`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#reconnectionresponsebrowserwsendpointstring- "Direct link to reconnectionresponsebrowserwsendpointstring-")

The fully-qualified URL of the browserWSEndpoint which can be used with other libraries like playwright or puppeteer. Please note that token information is not returned by this API and might be required

#### [`ReconnectionResponse.devtoolsFrontendUrl`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#reconnectionresponsedevtoolsfrontendurlstring- "Direct link to reconnectionresponsedevtoolsfrontendurlstring-")

The fully-qualified URL of the devtools resources for loading Chrome's developer tools remotely

#### [`ReconnectionResponse.webSocketDebuggerUrl`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#reconnectionresponsewebsocketdebuggerurlstring- "Direct link to reconnectionresponsewebsocketdebuggerurlstring-")

The underlying page's webSocketDebuggerUrl, useful for hooking libraries that operate on a page and not a browser object

### Returned By[​](#returned-by "Direct link to Returned By")

[`reconnect`](/bql-schema/operations/mutations/reconnect) mutation

---

## Object: RejectResponse
Source: https://docs.browserless.io/bql-schema/types/objects/reject-response

* * Types* Objects* RejectResponse

Open in ChatGPT

On this page

# RejectResponse

The response parameters for the reject mutation

```
type RejectResponse {  
  time: Float  
  enabled: Boolean  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`RejectResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#rejectresponsetimefloat- "Direct link to rejectresponsetimefloat-")

#### [`RejectResponse.enabled`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#rejectresponseenabledboolean- "Direct link to rejectresponseenabledboolean-")

### Returned By[​](#returned-by "Direct link to Returned By")

[`reject`](/bql-schema/operations/mutations/reject) mutation

---

## Object: RequestResponse
Source: https://docs.browserless.io/bql-schema/types/objects/request-response

* * Types* Objects* RequestResponse

Open in ChatGPT

On this page

# RequestResponse

Response returned from the request API

```
type RequestResponse {  
  url: String  
  method: Method  
  type: ResourceType  
  headers: [Headers]  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`RequestResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#requestresponseurlstring- "Direct link to requestresponseurlstring-")

The final URL of the request

#### [`RequestResponse.method`](#) ● [`Method`](/bql-schema/types/enums/method) enum[​](#requestresponsemethodmethod- "Direct link to requestresponsemethodmethod-")

The HTTP method of the request

#### [`RequestResponse.type`](#) ● [`ResourceType`](/bql-schema/types/enums/resource-type) enum[​](#requestresponsetyperesourcetype- "Direct link to requestresponsetyperesourcetype-")

The type of request that was made

#### [`RequestResponse.headers`](#) ● [`[Headers]`](/bql-schema/types/objects/headers) list object[​](#requestresponseheadersheaders-- "Direct link to requestresponseheadersheaders--")

The headers of the request

### Returned By[​](#returned-by "Direct link to Returned By")

[`request`](/bql-schema/operations/mutations/request) mutation

---

## Object: ResponseResponse
Source: https://docs.browserless.io/bql-schema/types/objects/response-response

* * Types* Objects* ResponseResponse

Open in ChatGPT

On this page

# ResponseResponse

Response returned from the response API

```
type ResponseResponse {  
  status: Int  
  url: String  
  method: Method  
  type: ResourceType  
  headers: [Headers]  
  body: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ResponseResponse.status`](#) ● [`Int`](/bql-schema/types/scalars/int) scalar[​](#responseresponsestatusint- "Direct link to responseresponsestatusint-")

The HTTP status code of the response

#### [`ResponseResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#responseresponseurlstring- "Direct link to responseresponseurlstring-")

The final URL of the response

#### [`ResponseResponse.method`](#) ● [`Method`](/bql-schema/types/enums/method) enum[​](#responseresponsemethodmethod- "Direct link to responseresponsemethodmethod-")

The HTTP method of the request that facilitated the response

#### [`ResponseResponse.type`](#) ● [`ResourceType`](/bql-schema/types/enums/resource-type) enum[​](#responseresponsetyperesourcetype- "Direct link to responseresponsetyperesourcetype-")

The type of response that was received

#### [`ResponseResponse.headers`](#) ● [`[Headers]`](/bql-schema/types/objects/headers) list object[​](#responseresponseheadersheaders-- "Direct link to responseresponseheadersheaders--")

The response headers returned

#### [`ResponseResponse.body`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#responseresponsebodystring- "Direct link to responseresponsebodystring-")

The body of the response, represented as a string when possible or base64 for binary-type requests like images

### Returned By[​](#returned-by "Direct link to Returned By")

[`response`](/bql-schema/operations/mutations/response) mutation

---

## Object: ScreenshotResponse
Source: https://docs.browserless.io/bql-schema/types/objects/screenshot-response

* * Types* Objects* ScreenshotResponse

Open in ChatGPT

On this page

# ScreenshotResponse

The response returned after generating a Screenshot

```
type ScreenshotResponse {  
  base64: String  
  format: String  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ScreenshotResponse.base64`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#screenshotresponsebase64string- "Direct link to screenshotresponsebase64string-")

The base64 encoded image of the screenshot

#### [`ScreenshotResponse.format`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#screenshotresponseformatstring- "Direct link to screenshotresponseformatstring-")

The format of the screenshot

#### [`ScreenshotResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotresponsetimefloat- "Direct link to screenshotresponsetimefloat-")

The time it took to take the screenshot

### Returned By[​](#returned-by "Direct link to Returned By")

[`screenshot`](/bql-schema/operations/mutations/screenshot) mutation

---

## Object: ScrollResponse
Source: https://docs.browserless.io/bql-schema/types/objects/scroll-response

* * Types* Objects* ScrollResponse

Open in ChatGPT

On this page

# ScrollResponse

Response returned after having scrolling inside the page

```
type ScrollResponse {  
  selector: String  
  time: Float  
  x: Float  
  y: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ScrollResponse.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#scrollresponseselectorstring- "Direct link to scrollresponseselectorstring-")

The CSS selector of the element on the page you want to scroll to

#### [`ScrollResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrollresponsetimefloat- "Direct link to scrollresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of scrolling to completion

#### [`ScrollResponse.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrollresponsexfloat- "Direct link to scrollresponsexfloat-")

The X coordinate, in pixels, to scroll to

#### [`ScrollResponse.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#scrollresponseyfloat- "Direct link to scrollresponseyfloat-")

The Y coordinate, in pixels, to scroll to

### Returned By[​](#returned-by "Direct link to Returned By")

[`scroll`](/bql-schema/operations/mutations/scroll) mutation

---

## Object: SelectResponse
Source: https://docs.browserless.io/bql-schema/types/objects/select-response

* * Types* Objects* SelectResponse

Open in ChatGPT

On this page

# SelectResponse

The response returned after selecting a value from a dropdown or multiple select element

```
type SelectResponse {  
  selector: String  
  time: Float  
  value: StringOrArray  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`SelectResponse.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#selectresponseselectorstring- "Direct link to selectresponseselectorstring-")

The selector of the element you selected from

#### [`SelectResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#selectresponsetimefloat- "Direct link to selectresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of selecting to completion

#### [`SelectResponse.value`](#) ● [`StringOrArray`](/bql-schema/types/scalars/string-or-array) scalar[​](#selectresponsevaluestringorarray- "Direct link to selectresponsevaluestringorarray-")

The value or values you selected from the select element

### Returned By[​](#returned-by "Direct link to Returned By")

[`select`](/bql-schema/operations/mutations/select) mutation

---

## Object: StandardCookie
Source: https://docs.browserless.io/bql-schema/types/objects/standard-cookie

* * Types* Objects* StandardCookie

Open in ChatGPT

On this page

# StandardCookie

A standard cookie

```
type StandardCookie {  
  domain: String  
  expires: Float  
  httpOnly: Boolean  
  name: String!  
  path: String  
  sameSite: CookieSameSite  
  secure: Boolean  
  value: String!  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`StandardCookie.domain`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#standardcookiedomainstring- "Direct link to standardcookiedomainstring-")

Cookie domain

#### [`StandardCookie.expires`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#standardcookieexpiresfloat- "Direct link to standardcookieexpiresfloat-")

Cookie expiration date, session cookie if not set

#### [`StandardCookie.httpOnly`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#standardcookiehttponlyboolean- "Direct link to standardcookiehttponlyboolean-")

True if cookie is http-only

#### [`StandardCookie.name`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#standardcookienamestring-- "Direct link to standardcookienamestring--")

Cookie name

#### [`StandardCookie.path`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#standardcookiepathstring- "Direct link to standardcookiepathstring-")

Cookie path

#### [`StandardCookie.sameSite`](#) ● [`CookieSameSite`](/bql-schema/types/enums/cookie-same-site) enum[​](#standardcookiesamesitecookiesamesite- "Direct link to standardcookiesamesitecookiesamesite-")

Cookie SameSite type

#### [`StandardCookie.secure`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#standardcookiesecureboolean- "Direct link to standardcookiesecureboolean-")

True if cookie is secure

#### [`StandardCookie.value`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#standardcookievaluestring-- "Direct link to standardcookievaluestring--")

Cookie value

#### [`StandardCookie.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#standardcookieurlstring- "Direct link to standardcookieurlstring-")

The request-URI to associate with the setting of the cookie. This value can affect the default domain, path, source port, and source scheme values of the created cookie

### Member Of[​](#member-of "Direct link to Member Of")

[`CookieResponse`](/bql-schema/types/objects/cookie-response) object

---

## Object: StopSessionRecordingResponse
Source: https://docs.browserless.io/bql-schema/types/objects/stop-session-recording-response

* * Types* Objects* StopSessionRecordingResponse

Open in ChatGPT

On this page

# StopSessionRecordingResponse

The response received after stopping session recording

```
type StopSessionRecordingResponse {  
  success: Boolean  
  error: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`StopSessionRecordingResponse.success`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#stopsessionrecordingresponsesuccessboolean- "Direct link to stopsessionrecordingresponsesuccessboolean-")

Whether the recording was successfully stopped and uploaded

#### [`StopSessionRecordingResponse.error`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#stopsessionrecordingresponseerrorstring- "Direct link to stopsessionrecordingresponseerrorstring-")

Error message if the operation failed

### Returned By[​](#returned-by "Direct link to Returned By")

[`stopSessionRecording`](/bql-schema/operations/mutations/stop-session-recording) mutation

---

## Object: SwitchWindowResponse
Source: https://docs.browserless.io/bql-schema/types/objects/switch-window-response

* * Types* Objects* SwitchWindowResponse

Open in ChatGPT

On this page

# SwitchWindowResponse

Response from window switching operation

```
type SwitchWindowResponse {  
  success: Boolean!  
  error: String  
  title: String  
  url: String  
  navigation: HTTPResponse  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`SwitchWindowResponse.success`](#) ● [`Boolean!`](/bql-schema/types/scalars/boolean) non-null scalar[​](#switchwindowresponsesuccessboolean-- "Direct link to switchwindowresponsesuccessboolean--")

#### [`SwitchWindowResponse.error`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#switchwindowresponseerrorstring- "Direct link to switchwindowresponseerrorstring-")

#### [`SwitchWindowResponse.title`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#switchwindowresponsetitlestring- "Direct link to switchwindowresponsetitlestring-")

#### [`SwitchWindowResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#switchwindowresponseurlstring- "Direct link to switchwindowresponseurlstring-")

#### [`SwitchWindowResponse.navigation`](#) ● [`HTTPResponse`](/bql-schema/types/objects/httpresponse) object[​](#switchwindowresponsenavigationhttpresponse- "Direct link to switchwindowresponsenavigationhttpresponse-")

### Returned By[​](#returned-by "Direct link to Returned By")

[`switchToWindow`](/bql-schema/operations/mutations/switch-to-window) mutation

---

## Object: TextResponse
Source: https://docs.browserless.io/bql-schema/types/objects/text-response

* * Types* Objects* TextResponse

Open in ChatGPT

On this page

# TextResponse

Text content of a page

```
type TextResponse {  
  text: String  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`TextResponse.text`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#textresponsetextstring- "Direct link to textresponsetextstring-")

The textual content of the page

#### [`TextResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#textresponsetimefloat- "Direct link to textresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of text retrieval to completion

### Returned By[​](#returned-by "Direct link to Returned By")

[`text`](/bql-schema/operations/mutations/text) mutation

---

## Object: TitleResponse
Source: https://docs.browserless.io/bql-schema/types/objects/title-response

* * Types* Objects* TitleResponse

Open in ChatGPT

On this page

# TitleResponse

Response returned after the page's title has been set or get

```
type TitleResponse {  
  title: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`TitleResponse.title`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#titleresponsetitlestring- "Direct link to titleresponsetitlestring-")

The title of the current page

### Returned By[​](#returned-by "Direct link to Returned By")

[`title`](/bql-schema/operations/mutations/title) mutation

---

## Object: TypeResponse
Source: https://docs.browserless.io/bql-schema/types/objects/type-response

* * Types* Objects* TypeResponse

Open in ChatGPT

On this page

# TypeResponse

Response returned after having typed into an element

```
type TypeResponse {  
  selector: String  
  text: String  
  time: Float  
  x: Float  
  y: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`TypeResponse.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#typeresponseselectorstring- "Direct link to typeresponseselectorstring-")

The selector of the element you typed into

#### [`TypeResponse.text`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#typeresponsetextstring- "Direct link to typeresponsetextstring-")

The textual content that was typed

#### [`TypeResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#typeresponsetimefloat- "Direct link to typeresponsetimefloat-")

The amount of time, in milliseconds, elapsed since the start of typing to completion

#### [`TypeResponse.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#typeresponsexfloat- "Direct link to typeresponsexfloat-")

The X coordinate of the element, in pixels, on the page

#### [`TypeResponse.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#typeresponseyfloat- "Direct link to typeresponseyfloat-")

The Y coordinate of the element, in pixels, on the page

### Returned By[​](#returned-by "Direct link to Returned By")

[`type`](/bql-schema/operations/mutations/type) mutation

---

## Object: URLResponse
Source: https://docs.browserless.io/bql-schema/types/objects/url-response

* * Types* Objects* URLResponse

Open in ChatGPT

On this page

# URLResponse

Response returned after the URL of the page has been set or get

```
type URLResponse {  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`URLResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#urlresponseurlstring- "Direct link to urlresponseurlstring-")

The URL of the current page

### Returned By[​](#returned-by "Direct link to Returned By")

[`url`](/bql-schema/operations/mutations/url) mutation

---

## Object: UserAgentResponse
Source: https://docs.browserless.io/bql-schema/types/objects/user-agent-response

* * Types* Objects* UserAgentResponse

Open in ChatGPT

On this page

# UserAgentResponse

The response returned after setting the User-Agent

```
type UserAgentResponse {  
  userAgent: String  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`UserAgentResponse.userAgent`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#useragentresponseuseragentstring- "Direct link to useragentresponseuseragentstring-")

The User-Agent string that was set

#### [`UserAgentResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#useragentresponsetimefloat- "Direct link to useragentresponsetimefloat-")

The time it took to set the User-Agent

### Returned By[​](#returned-by "Direct link to Returned By")

[`userAgent`](/bql-schema/operations/mutations/user-agent) mutation

---

## Object: VerifyResponse
Source: https://docs.browserless.io/bql-schema/types/objects/verify-response

* * Types* Objects* VerifyResponse

Open in ChatGPT

On this page

# VerifyResponse

Response returned after a verification method has been bypassed

```
type VerifyResponse {  
  found: Boolean  
  solved: Boolean  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`VerifyResponse.found`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#verifyresponsefoundboolean- "Direct link to verifyresponsefoundboolean-")

If a verification was found or not

#### [`VerifyResponse.solved`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#verifyresponsesolvedboolean- "Direct link to verifyresponsesolvedboolean-")

If a verification was found, whether or not it was clicked

#### [`VerifyResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#verifyresponsetimefloat- "Direct link to verifyresponsetimefloat-")

The total time it took to find, and click, the verification

---

## Object: ViewportResponse
Source: https://docs.browserless.io/bql-schema/types/objects/viewport-response

* * Types* Objects* ViewportResponse

Open in ChatGPT

On this page

# ViewportResponse

Response returned after setting the viewport

```
type ViewportResponse {  
  width: Float  
  height: Float  
  deviceScaleFactor: Float  
  mobile: Boolean  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ViewportResponse.width`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#viewportresponsewidthfloat- "Direct link to viewportresponsewidthfloat-")

The width of the viewport in pixels

#### [`ViewportResponse.height`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#viewportresponseheightfloat- "Direct link to viewportresponseheightfloat-")

The height of the viewport in pixels

#### [`ViewportResponse.deviceScaleFactor`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#viewportresponsedevicescalefactorfloat- "Direct link to viewportresponsedevicescalefactorfloat-")

The device scale factor

#### [`ViewportResponse.mobile`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#viewportresponsemobileboolean- "Direct link to viewportresponsemobileboolean-")

Whether the device is in mobile mode

#### [`ViewportResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#viewportresponsetimefloat- "Direct link to viewportresponsetimefloat-")

The time it took to set the viewport

### Returned By[​](#returned-by "Direct link to Returned By")

[`viewport`](/bql-schema/operations/mutations/viewport) mutation

---

## Object: WaitForRequest
Source: https://docs.browserless.io/bql-schema/types/objects/wait-for-request

* * Types* Objects* WaitForRequest

Open in ChatGPT

On this page

# WaitForRequest

Response returned after a particular network request has been sent

```
type WaitForRequest {  
  time: Float  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`WaitForRequest.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforrequesttimefloat- "Direct link to waitforrequesttimefloat-")

The period of time elapsed, in milliseconds, waited for

#### [`WaitForRequest.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#waitforrequesturlstring- "Direct link to waitforrequesturlstring-")

The URL parameter used to match the response with

### Returned By[​](#returned-by "Direct link to Returned By")

[`waitForRequest`](/bql-schema/operations/mutations/wait-for-request) mutation

---

## Object: WaitForResponse
Source: https://docs.browserless.io/bql-schema/types/objects/wait-for-response

* * Types* Objects* WaitForResponse

Open in ChatGPT

On this page

# WaitForResponse

Response returned after a particular network response has been received

```
type WaitForResponse {  
  time: Float  
  status: Int  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`WaitForResponse.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforresponsetimefloat- "Direct link to waitforresponsetimefloat-")

The period of time elapsed, in milliseconds, waited for

#### [`WaitForResponse.status`](#) ● [`Int`](/bql-schema/types/scalars/int) scalar[​](#waitforresponsestatusint- "Direct link to waitforresponsestatusint-")

The status code response of the response

#### [`WaitForResponse.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#waitforresponseurlstring- "Direct link to waitforresponseurlstring-")

The URL parameter used to match the response with

### Returned By[​](#returned-by "Direct link to Returned By")

[`waitForResponse`](/bql-schema/operations/mutations/wait-for-response) mutation

---

## Object: WaitForSelector
Source: https://docs.browserless.io/bql-schema/types/objects/wait-for-selector

* * Types* Objects* WaitForSelector

Open in ChatGPT

On this page

# WaitForSelector

Response returned after a particular selector has been found in the DOM

```
type WaitForSelector {  
  height: Float  
  selector: String  
  time: Float  
  y: Float  
  x: Float  
  width: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`WaitForSelector.height`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectorheightfloat- "Direct link to waitforselectorheightfloat-")

The height, in pixels, of the element

#### [`WaitForSelector.selector`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#waitforselectorselectorstring- "Direct link to waitforselectorselectorstring-")

The selector waited for

#### [`WaitForSelector.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectortimefloat- "Direct link to waitforselectortimefloat-")

The period of time elapsed, in milliseconds, waited for

#### [`WaitForSelector.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectoryfloat- "Direct link to waitforselectoryfloat-")

The position, in pixels, top of the viewport

#### [`WaitForSelector.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectorxfloat- "Direct link to waitforselectorxfloat-")

The position, in pixels, left of the viewport

#### [`WaitForSelector.width`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitforselectorwidthfloat- "Direct link to waitforselectorwidthfloat-")

The width, in pixels, of the element

### Returned By[​](#returned-by "Direct link to Returned By")

[`waitForSelector`](/bql-schema/operations/mutations/wait-for-selector) mutation

---

## Object: WaitForTimeout
Source: https://docs.browserless.io/bql-schema/types/objects/wait-for-timeout

* * Types* Objects* WaitForTimeout

Open in ChatGPT

On this page

# WaitForTimeout

Response returned after having waited for a selector to appear in the DOM

```
type WaitForTimeout {  
  time: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`WaitForTimeout.time`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#waitfortimeouttimefloat- "Direct link to waitfortimeouttimefloat-")

The period of time elapsed, in milliseconds, waited for

### Returned By[​](#returned-by "Direct link to Returned By")

[`waitForTimeout`](/bql-schema/operations/mutations/wait-for-timeout) mutation