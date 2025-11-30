# Browserless Inputs Documentation



---

## Input: CleanInput
Source: https://docs.browserless.io/bql-schema/types/inputs/clean-input

* * Types* Inputs* CleanInput

Open in ChatGPT

On this page

# CleanInput

Options for cleaning up the DOM prior to exporting its content. Many options are available, and this query can destructively remove non-text DOM nodes, DOM attributes, and gratuitous whitespace characters. Since these operations are destructive in their nature it's recommended to run them at the very end of your query in order to preserve page functionality

```
input CleanInput {  
  removeNonTextNodes: Boolean  
  removeAttributes: Boolean  
  removeRegex: Boolean  
  selectors: [String!]  
  attributes: [String]  
  mode: AttributeMode  
  regexes: [String!]  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`CleanInput.removeNonTextNodes`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#cleaninputremovenontextnodesboolean- "Direct link to cleaninputremovenontextnodesboolean-")

When true (default is true) this will remove non-textual nodes from the DOM like scripts, links, video, canvas, etc. You may override this by specifying a `selectors` argument for DOM selectors to remove.

#### [`CleanInput.removeAttributes`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#cleaninputremoveattributesboolean- "Direct link to cleaninputremoveattributesboolean-")

When true (default is false) this will remove all attributes on all DOM nodes. Useful for "cleaning" up all HTML markup but preserving the structure overall. You can specify specific attributes to remove with `attributes` argument

#### [`CleanInput.removeRegex`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#cleaninputremoveregexboolean- "Direct link to cleaninputremoveregexboolean-")

Removes any characters in the HTML by a regex pattern and arn in order. By default this is true and removes newlines, returns, tabs, multi-spaces and HTML comments in that order. You may supply your own regex by using the `regexes` argument

#### [`CleanInput.selectors`](#) ● [`[String!]`](/bql-schema/types/scalars/string) list scalar[​](#cleaninputselectorsstring-- "Direct link to cleaninputselectorsstring--")

A list of selectors to remove from the page when `removeNonTextNodes` is set to true (`true` by default).

#### [`CleanInput.attributes`](#) ● [`[String]`](/bql-schema/types/scalars/string) list scalar[​](#cleaninputattributesstring-- "Direct link to cleaninputattributesstring--")

A list of attributes to remove from all DOM nodes. When this isn't specified, and `removeAttributes` is true, all attributes on all DOM nodes are removed. `removeNonTextNodes` must be set to `true` for this to take effect

#### [`CleanInput.mode`](#) ● [`AttributeMode`](/bql-schema/types/enums/attribute-mode) enum[​](#cleaninputmodeattributemode- "Direct link to cleaninputmodeattributemode-")

Controls how the `attributes` field is interpreted. When set to "allow", the `attributes` field specifies which attributes to keep. When set to "deny" (default), the `attributes` field specifies which attributes to remove. Defaults to "deny" for backward compatibility.

#### [`CleanInput.regexes`](#) ● [`[String!]`](/bql-schema/types/scalars/string) list scalar[​](#cleaninputregexesstring-- "Direct link to cleaninputregexesstring--")

When `removeRegex` is set to "true" this list of regex items, without the beginning and ending `/`, are removed from the page. These are each run in order and replaced with a single space character to preserve some of their contents

### Member Of[​](#member-of "Direct link to Member Of")

[`html`](/bql-schema/operations/mutations/html) mutation ● [`text`](/bql-schema/operations/mutations/text) mutation

---

## Input: CookieInput
Source: https://docs.browserless.io/bql-schema/types/inputs/cookie-input

* * Types* Inputs* CookieInput

Open in ChatGPT

On this page

# CookieInput

The cookie to be sent to the page

```
input CookieInput {  
  domain: String  
  expires: Float  
  httpOnly: Boolean  
  name: String!  
  path: String  
  sameSite: CookieSameSite  
  secure: Boolean  
  url: String  
  value: String!  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`CookieInput.domain`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#cookieinputdomainstring- "Direct link to cookieinputdomainstring-")

Cookie domain

#### [`CookieInput.expires`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#cookieinputexpiresfloat- "Direct link to cookieinputexpiresfloat-")

Cookie expiration date, session cookie if not set

#### [`CookieInput.httpOnly`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#cookieinputhttponlyboolean- "Direct link to cookieinputhttponlyboolean-")

True if cookie is http-only

#### [`CookieInput.name`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#cookieinputnamestring-- "Direct link to cookieinputnamestring--")

Cookie name

#### [`CookieInput.path`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#cookieinputpathstring- "Direct link to cookieinputpathstring-")

Cookie path

#### [`CookieInput.sameSite`](#) ● [`CookieSameSite`](/bql-schema/types/enums/cookie-same-site) enum[​](#cookieinputsamesitecookiesamesite- "Direct link to cookieinputsamesitecookiesamesite-")

Cookie SameSite type

#### [`CookieInput.secure`](#) ● [`Boolean`](/bql-schema/types/scalars/boolean) scalar[​](#cookieinputsecureboolean- "Direct link to cookieinputsecureboolean-")

True if cookie is secure

#### [`CookieInput.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#cookieinputurlstring- "Direct link to cookieinputurlstring-")

The request-URI to associate with the setting of the cookie. This value can affect the default domain, path, source port, and source scheme values of the created cookie

#### [`CookieInput.value`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#cookieinputvaluestring-- "Direct link to cookieinputvaluestring--")

Cookie value

### Member Of[​](#member-of "Direct link to Member Of")

[`cookies`](/bql-schema/operations/mutations/cookies) mutation

---

## Input: HeaderInput
Source: https://docs.browserless.io/bql-schema/types/inputs/header-input

* * Types* Inputs* HeaderInput

Open in ChatGPT

On this page

# HeaderInput

A HTTP header input type

```
input HeaderInput {  
  name: String!  
  value: String!  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`HeaderInput.name`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#headerinputnamestring-- "Direct link to headerinputnamestring--")

The name of the HTTP header

#### [`HeaderInput.value`](#) ● [`String!`](/bql-schema/types/scalars/string) non-null scalar[​](#headerinputvaluestring-- "Direct link to headerinputvaluestring--")

The value of the HTTP header

### Member Of[​](#member-of "Direct link to Member Of")

[`setExtraHTTPHeaders`](/bql-schema/operations/mutations/set-extra-httpheaders) mutation

---

## Input: RequestInput
Source: https://docs.browserless.io/bql-schema/types/inputs/request-input

* * Types* Inputs* RequestInput

Open in ChatGPT

On this page

# RequestInput

The specific request to perform a conditional action on

```
input RequestInput {  
  method: Method  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`RequestInput.method`](#) ● [`Method`](/bql-schema/types/enums/method) enum[​](#requestinputmethodmethod- "Direct link to requestinputmethodmethod-")

The HTTP Method of the request

#### [`RequestInput.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#requestinputurlstring- "Direct link to requestinputurlstring-")

The pattern of the request URL to wait for, using glob-style pattern-matching

### Member Of[​](#member-of "Direct link to Member Of")

[`if`](/bql-schema/operations/mutations/if) mutation ● [`ifnot`](/bql-schema/operations/mutations/ifnot) mutation

---

## Input: ResponseInput
Source: https://docs.browserless.io/bql-schema/types/inputs/response-input

* * Types* Inputs* ResponseInput

Open in ChatGPT

On this page

# ResponseInput

The specific response to perform a conditional action on

```
input ResponseInput {  
  statuses: [Int]  
  codes: [Int] @deprecated  
  url: String  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ResponseInput.statuses`](#) ● [`[Int]`](/bql-schema/types/scalars/int) list scalar[​](#responseinputstatusesint-- "Direct link to responseinputstatusesint--")

The HTTP Response code(s) of the URL to wait for. Can be a single HTTP code or a list of desired codes

#### [`ResponseInput.codes`](#) ● [`[Int]`](/bql-schema/types/scalars/int) deprecated list scalar[​](#responseinputcodesint--- "Direct link to responseinputcodesint---")

DEPRECATED

Use `statuses` field instead as it is more consistent in BrowserQL.

The HTTP Response code(s) of the URL to wait for. Can be a single HTTP code or a list of desired codes

#### [`ResponseInput.url`](#) ● [`String`](/bql-schema/types/scalars/string) scalar[​](#responseinputurlstring- "Direct link to responseinputurlstring-")

The pattern of the response URL to wait for, using glob-style pattern-matching

### Member Of[​](#member-of "Direct link to Member Of")

[`if`](/bql-schema/operations/mutations/if) mutation ● [`ifnot`](/bql-schema/operations/mutations/ifnot) mutation

---

## Input: ScreenshotClip
Source: https://docs.browserless.io/bql-schema/types/inputs/screenshot-clip

* * Types* Inputs* ScreenshotClip

Open in ChatGPT

On this page

# ScreenshotClip

The clipping to be applied to the screenshot

```
input ScreenshotClip {  
  height: Float  
  scale: Float  
  width: Float  
  x: Float  
  y: Float  
}
```

### Fields[​](#fields "Direct link to Fields")

#### [`ScreenshotClip.height`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotclipheightfloat- "Direct link to screenshotclipheightfloat-")

The height of the clip, in pixels

#### [`ScreenshotClip.scale`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotclipscalefloat- "Direct link to screenshotclipscalefloat-")

The scale factor of the clip

#### [`ScreenshotClip.width`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotclipwidthfloat- "Direct link to screenshotclipwidthfloat-")

The width of the clip, in pixels

#### [`ScreenshotClip.x`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotclipxfloat- "Direct link to screenshotclipxfloat-")

The x coordinate to start clipping, in pixels

#### [`ScreenshotClip.y`](#) ● [`Float`](/bql-schema/types/scalars/float) scalar[​](#screenshotclipyfloat- "Direct link to screenshotclipyfloat-")

The y coordinate to start clipping, in pixels

### Member Of[​](#member-of "Direct link to Member Of")

[`screenshot`](/bql-schema/operations/mutations/screenshot) mutation