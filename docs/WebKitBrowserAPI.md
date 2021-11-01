<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.WebKit_Browser_API"></a>
# WebKit Browser API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

WebKitBrowser interface for Thunder framework.

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

This document describes purpose and functionality of the WebKitBrowser interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

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

WebKitBrowser JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the WebKitBrowser interface:

WebKitBrowser interface methods:

| Method | Description |
| :-------- | :-------- |
| [delete](#method.delete) | Removes contents of a directory from the persistent storage |


<a name="method.delete"></a>
## *delete <sup>method</sup>*

Removes contents of a directory from the persistent storage.

### Description

Use this method to recursively delete contents of a directory

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.path | string | Path to directory (within the persistent storage) to delete contents of |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 22 | ```ERROR_UNKNOWN_KEY``` | The given path was incorrect |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.delete",
    "params": {
        "path": ".cache/wpe/disk-cache"
    }
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

The following properties are provided by the WebKitBrowser interface:

WebKitBrowser interface properties:

| Property | Description |
| :-------- | :-------- |
| [languages](#property.languages) | User preferred languages |
| [headers](#property.headers) | Headers to send on all requests that the browser makes |

StateControl interface properties:

| Property | Description |
| :-------- | :-------- |
| [state](#property.state) | Running state of the service |


<a name="property.languages"></a>
## *languages <sup>property</sup>*

Provides access to the user preferred languages.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | array | User preferred languages |
| (property)[#] | string |  |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.languages"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "en-US"
    ]
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.languages",
    "params": [
        "en-US"
    ]
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

<a name="property.headers"></a>
## *headers <sup>property</sup>*

Provides access to the headers to send on all requests that the browser makes.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | array | Headers to send on all requests that the browser makes |
| (property)[#] | object |  |
| (property)[#]?.name | string | <sup>*(optional)*</sup> Header name |
| (property)[#]?.value | string | <sup>*(optional)*</sup> Header value |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.headers"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "name": "X-Forwarded-For",
            "value": "::1"
        }
    ]
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.headers",
    "params": [
        {
            "name": "X-Forwarded-For",
            "value": "::1"
        }
    ]
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

<a name="property.state"></a>
## *state <sup>property</sup>*

Provides access to the running state of the service.

Also see: [statechange](#event.statechange)

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | string | Running state of the service (must be one of the following: *resumed*, *suspended*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.state"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "resumed"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "WebKitBrowser.1.state",
    "params": "resumed"
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

The following events are provided by the WebKitBrowser interface:

WebKitBrowser interface events:

| Event | Description |
| :-------- | :-------- |
| [bridgequery](#event.bridgequery) | A Base64 encoded JSON message from legacy $badger bridge |

StateControl interface events:

| Event | Description |
| :-------- | :-------- |
| [statechange](#event.statechange) | Signals a state change of the service |


<a name="event.bridgequery"></a>
## *bridgequery <sup>event</sup>*

A Base64 encoded JSON message from legacy $badger bridge.

> This API is **obsolete**. It is no longer recommended for use in new implementations.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | string |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.bridgequery",
    "params": "..."
}
```

<a name="event.statechange"></a>
## *statechange <sup>event</sup>*

Signals a state change of the service.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.suspended | boolean | Determines if the service has entered suspended state (true) or resumed state (false) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.statechange",
    "params": {
        "suspended": false
    }
}
```

