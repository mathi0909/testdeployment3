<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.AVSController_API"></a>
# AVSController API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

AVSController interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the AVSController interface. It includes detailed specification about its methods provided and notifications sent.

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

AVSController JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the AVSController interface:

AVSController interface methods:

| Method | Description |
| :-------- | :-------- |
| [mute](#method.mute) | Mutes the audio output of AVS |
| [record](#method.record) | Starts or stops the voice recording, skipping keyword detection |


<a name="method.mute"></a>
## *mute <sup>method</sup>*

Mutes the audio output of AVS.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| muted | boolean |  |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
|  | ```ERROR_GENERAL``` | when there is a fatal error or authorisation is not possible |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "AVSController.1.mute",
    "params": false
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

<a name="method.record"></a>
## *record <sup>method</sup>*

Starts or stops the voice recording, skipping keyword detection.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| started | boolean |  |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
|  | ```ERROR_GENERAL``` | when there is a fatal error or authorisation is not possible |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "AVSController.1.record",
    "params": false
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

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the AVSController interface:

AVSController interface events:

| Event | Description |
| :-------- | :-------- |
| [dialoguestatechange](#event.dialoguestatechange) | notifies about dialogue state changes |


<a name="event.dialoguestatechange"></a>
## *dialoguestatechange <sup>event</sup>*

notifies about dialogue state changes.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| state | string | The new state (must be one of the following: *Idle*, *Listening*, *Expecting*, *Thinking*, *Speaking*) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.dialoguestatechange",
    "params": "SPEAKING"
}
```

