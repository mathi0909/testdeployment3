<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.NetworkTools_API"></a>
# NetworkTools API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

NetworkTools interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the NetworkTools interface. It includes detailed specification about its methods provided and notifications sent.

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

NetworkTools JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the NetworkTools interface:

NetworkTools interface methods:

| Method | Description |
| :-------- | :-------- |
| [ping](#method.ping) | Ping the given destination with ICMP packages |
| [traceroute](#method.traceroute) | TraceRoute to the given destination with ICMP packages |


<a name="method.ping"></a>
## *ping <sup>method</sup>*

Ping the given destination with ICMP packages.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.destination | string |  |
| params.timeoutinseconds | integer |  |
| params.count | integer |  |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
|  | ```ERROR_NONE,``` | ERROR_INPROGRES means an icmp check is already in progress . |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "NetworkTools.1.ping",
    "params": {
        "destination": "...",
        "timeoutinseconds": 0,
        "count": 0
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

<a name="method.traceroute"></a>
## *traceroute <sup>method</sup>*

TraceRoute to the given destination with ICMP packages.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.destination | string |  |
| params.timeoutinseconds | integer |  |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
|  | ```ERROR_NONE,``` | ERROR_INPROGRES means an icmp check is already in progress |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "NetworkTools.1.traceroute",
    "params": {
        "destination": "...",
        "timeoutinseconds": 0
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

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the NetworkTools interface:

NetworkTools interface events:

| Event | Description |
| :-------- | :-------- |
| [report](#event.report) | Signals an message from a given host |


<a name="event.report"></a>
## *report <sup>event</sup>*

Signals an message from a given host.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.source | string | is the NodeId of the system that send the metadta presented in the next field |
| params.metadata | string | depending on the tool started, this JSON string will contain additiona information on this notification |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.report",
    "params": {
        "source": "...",
        "metadata": "..."
    }
}
```

