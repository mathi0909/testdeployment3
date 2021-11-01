<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.WebBrowser_API"></a>
# WebBrowser API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

WebBrowser interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)
- [Properties](#head.Properties)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the WebBrowser interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

<a name="head.Case_Sensitivity"></a>
## Case Sensitivity

All identifiers of the interfaces described in this document are case-sensitive. Thus, unless stated otherwise, all keywords, entities, properties, relations and actions should be treated as such.

<a name="head.Acronyms,_Abbreviations_and_Terms"></a>
## Acronyms, Abbreviations and Terms

The table below provides and overview of acronyms used in this document and their definitions.

| Acronym | Description |
| :-------- | :-------- |
| <a name="acronym.API">API</a> | Application Programming Interface |
| <a name="acronym.HTTP">HTTP</a> | Hypertext Transfer Protocol |
| <a name="acronym.JSON">JSON</a> | JavaScript Object Notation; a data interchange format |
| <a name="acronym.JSON-RPC">JSON-RPC</a> | A remote procedure call protocol encoded in JSON |

The table below provides and overview of terms and abbreviations used in this document and their definitions.

| Term | Description |
| :-------- | :-------- |
| <a name="term.callsign">callsign</a> | The name given to an instance of a plugin. One plugin can be instantiated multiple times, but each instance the instance name, callsign, must be unique. |

<a name="head.References"></a>
## References

| Ref ID | Description |
| :-------- | :-------- |
| <a name="ref.HTTP">[HTTP](http://www.w3.org/Protocols)</a> | HTTP specification |
| <a name="ref.JSON-RPC">[JSON-RPC](https://www.jsonrpc.org/specification)</a> | JSON-RPC 2.0 specification |
| <a name="ref.JSON">[JSON](http://www.json.org/)</a> | JSON specification |
| <a name="ref.Thunder">[Thunder](https://github.com/WebPlatformForEmbedded/Thunder/blob/master/doc/WPE%20-%20API%20-%20WPEFramework.docx)</a> | Thunder API Reference |

<a name="head.Description"></a>
# Description

WebBrowser JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the WebBrowser interface:

WebBrowser interface methods:

| Method | Description |
| :-------- | :-------- |
| [collectgarbage](#method.collectgarbage) | Initiate garbage collection |


<a name="method.collectgarbage"></a>
## *collectgarbage <sup>method</sup>*

Initiate garbage collection.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.collectgarbage"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```

<a name="head.Properties"></a>
# Properties

The following properties are provided by the WebBrowser interface:

WebBrowser interface properties:

| Property | Description |
| :-------- | :-------- |
| [url](#property.url) | Page loaded in the browser |
| [visibility](#property.visibility) | Browser window visibility state |
| [fps](#property.fps) <sup>RO</sup> | Current framerate the browser is rendering at |
| [useragent](#property.useragent) | UserAgent string used by the browser |
| [localstorageenabled](#property.localstorageenabled) | Controls the local storage availability |
| [httpcookieacceptpolicy](#property.httpcookieacceptpolicy) | HTTP cookies accept policy |
| [bridgereply](#property.bridgereply) <sup>WO</sup> | Response for legacy $badger |
| [bridgeevent](#property.bridgeevent) <sup>WO</sup> | Send legacy $badger event |


<a name="property.url"></a>
## *url <sup>property</sup>*

Provides access to the page loaded in the browser.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| url | string | Loaded URL |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.url"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "https://example.com"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.url",
    "params": "https://example.com"
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.visibility"></a>
## *visibility <sup>property</sup>*

Provides access to the browser window visibility state.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| visible | string | Visiblity state (must be one of the following: *hidden*, *visible*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.visibility"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "hidden"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.visibility",
    "params": "hidden"
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.fps"></a>
## *fps <sup>property</sup>*

Provides access to the current framerate the browser is rendering at.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| fps | integer | Current FPS |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.fps"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0
}
```

<a name="property.useragent"></a>
## *useragent <sup>property</sup>*

Provides access to the userAgent string used by the browser.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| useragent | string | UserAgent value |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.useragent"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "Mozilla/5.0 (Linux; x86_64 GNU/Linux) AppleWebKit/601.1 (KHTML, like Gecko) Version/8.0 Safari/601.1 WP"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.useragent",
    "params": "Mozilla/5.0 (Linux; x86_64 GNU/Linux) AppleWebKit/601.1 (KHTML, like Gecko) Version/8.0 Safari/601.1 WP"
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.localstorageenabled"></a>
## *localstorageenabled <sup>property</sup>*

Provides access to the controls the local storage availability.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | boolean | Controls the local storage availability |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.localstorageenabled"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": false
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.localstorageenabled",
    "params": false
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.httpcookieacceptpolicy"></a>
## *httpcookieacceptpolicy <sup>property</sup>*

Provides access to the HTTP cookies accept policy.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| policy | string | HTTP Cookie Accept Policy Type (must be one of the following: *always*, *never*, *onlyfrommaindocumentdomain*, *exclusivelyfrommaindocumentdomain*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.httpcookieacceptpolicy"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "always"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.httpcookieacceptpolicy",
    "params": "always"
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.bridgereply"></a>
## *bridgereply <sup>property</sup>*

Provides access to the response for legacy $badger.

> This property is **write-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| payload | string | base64 encoded JSON string response to be delivered to $badger.callback |

### Example

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.bridgereply",
    "params": "..."
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="property.bridgeevent"></a>
## *bridgeevent <sup>property</sup>*

Provides access to the send legacy $badger event.

> This property is **write-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| payload | string | base64 encoded JSON string response to be delivered to window.$badger.event |

### Example

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebBrowser.1.bridgeevent",
    "params": "..."
}
```

#### Set Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "null"
}
```

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the WebBrowser interface:

WebBrowser interface events:

| Event | Description |
| :-------- | :-------- |
| [loadfinished](#event.loadfinished) | Initial HTML document has been completely loaded and parsed |
| [loadfailed](#event.loadfailed) | Browser failed to load page |
| [urlchange](#event.urlchange) | Signals a URL change in the browser |
| [visibilitychange](#event.visibilitychange) | Signals a visibility change of the browser |
| [pageclosure](#event.pageclosure) | Notifies that the web page requests to close its window |


<a name="event.loadfinished"></a>
## *loadfinished <sup>event</sup>*

Initial HTML document has been completely loaded and parsed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.url | string | The URL that has been loaded |
| params.httpstatus | integer | The response code of main resource request |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.loadfinished",
    "params": {
        "url": "https://example.com",
        "httpstatus": 200
    }
}
```

<a name="event.loadfailed"></a>
## *loadfailed <sup>event</sup>*

Browser failed to load page.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.url | string | The URL that has been failed to load |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.loadfailed",
    "params": {
        "url": "https://example.com"
    }
}
```

<a name="event.urlchange"></a>
## *urlchange <sup>event</sup>*

Signals a URL change in the browser.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.url | string | The URL that has been loaded or requested |
| params.loaded | boolean | loaded (true) or not (false) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.urlchange",
    "params": {
        "url": "https://example.com",
        "loaded": false
    }
}
```

<a name="event.visibilitychange"></a>
## *visibilitychange <sup>event</sup>*

Signals a visibility change of the browser.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hidden | boolean | hidden (true) or visible (false) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.visibilitychange",
    "params": {
        "hidden": false
    }
}
```

<a name="event.pageclosure"></a>
## *pageclosure <sup>event</sup>*

Notifies that the web page requests to close its window.

### Parameters

This event carries no parameters.

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.pageclosure"
}
```

