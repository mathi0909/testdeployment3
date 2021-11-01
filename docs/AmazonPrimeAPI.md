<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.AmazonPrime_API"></a>
# AmazonPrime API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

AmazonPrime interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the AmazonPrime interface. It includes detailed specification about its methods provided and notifications sent.

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

AmazonPrime JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the AmazonPrime interface:

AmazonPrime interface methods:

| Method | Description |
| :-------- | :-------- |
| [send](#method.send) | Send a message over the message bus to ignition |


<a name="method.send"></a>
## *send <sup>method</sup>*

Send a message over the message bus to ignition.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| message | string |  |

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
    "method": "AmazonPrime.1.send",
    "params": "..."
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

The following events are provided by the AmazonPrime interface:

AmazonPrime interface events:

| Event | Description |
| :-------- | :-------- |
| [receive](#event.receive) | Receive a message from the generic message bus |


<a name="event.receive"></a>
## *receive <sup>event</sup>*

Receive a message from the generic message bus.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| message | string |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.receive",
    "params": "..."
}
```

