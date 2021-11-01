<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Netflix_API"></a>
# Netflix API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

Netflix interface for Thunder framework.

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

This document describes purpose and functionality of the Netflix interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

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

Netflix JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the Netflix interface:

Netflix interface methods:

| Method | Description |
| :-------- | :-------- |
| [factoryreset](#method.factoryreset) | Performs a reset to factory defaults |
| [systemcommand](#method.systemcommand) | Sends a system command to Netflix |


<a name="method.factoryreset"></a>
## *factoryreset <sup>method</sup>*

Performs a reset to factory defaults.

> This API is **deprecated** and may be removed in the future. It is no longer recommended for use in new implementations.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 2 | ```ERROR_UNAVAILABLE``` | Netflix is unavailable |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Netflix.1.factoryreset"
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

<a name="method.systemcommand"></a>
## *systemcommand <sup>method</sup>*

Sends a system command to Netflix.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.command | string | Command to send to Netflix |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 2 | ```ERROR_UNAVAILABLE``` | Netflix is unavailable |
| 22 | ```ERROR_UNKNOWN_KEY``` | Unknown command |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Netflix.1.systemcommand",
    "params": {
        "command": "exit"
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

The following properties are provided by the Netflix interface:

Netflix interface properties:

| Property | Description |
| :-------- | :-------- |
| [esn](#property.esn) <sup>RO</sup> | ESN value |
| [visibility](#property.visibility) <sup>WO</sup> | Current Netflix visibility |

StateControl interface properties:

| Property | Description |
| :-------- | :-------- |
| [state](#property.state) | Running state of the service |


<a name="property.esn"></a>
## *esn <sup>property</sup>*

Provides access to the ESN value.

> This property is **read-only**.

> This API is **deprecated** and may be removed in the future. It is no longer recommended for use in new implementations.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | string | ESN value |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 2 | ```ERROR_UNAVAILABLE``` | Netflix is unavailable |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Netflix.1.esn"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "DADDAUFV2=00000000000000000000000000000001"
}
```

<a name="property.visibility"></a>
## *visibility <sup>property</sup>*

Provides access to the current Netflix visibility.

> This property is **write-only**.

> This API is **deprecated** and may be removed in the future. It is no longer recommended for use in new implementations.

Also see: [visibilitychange](#event.visibilitychange)

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | string | Current Netflix visibility (must be one of the following: *visible*, *hidden*) |

### Example

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Netflix.1.visibility",
    "params": "visible"
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
    "method": "Netflix.1.state"
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
    "method": "Netflix.1.state",
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

The following events are provided by the Netflix interface:

Netflix interface events:

| Event | Description |
| :-------- | :-------- |
| [playbackchange](#event.playbackchange) | Signals playback status change |

StateControl interface events:

| Event | Description |
| :-------- | :-------- |
| [statechange](#event.statechange) | Signals a state change of the service |


<a name="event.playbackchange"></a>
## *playbackchange <sup>event</sup>*

Signals playback status change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.playing | boolean | Determines if the Netflix is in playing mode (true) or not playing (false) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.playbackchange",
    "params": {
        "playing": true
    }
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

