<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.DIAL_Server_API"></a>
# DIAL Server API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

DIALServer interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the DIALServer interface. It includes detailed specification about its properties provided and notifications sent.

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

DIAL Server JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the DIALServer interface:

DIALServer interface properties:

| Property | Description |
| :-------- | :-------- |
| [state](#property.state) | Current application running state |


<a name="property.state"></a>
## *state <sup>property</sup>*

Provides access to the current application running state.

### Description

This property can be used to update the running status of an un-managed application (i.e. running in *passive mode*). For DIALServer-managed applications this property shall be considered *read-only*.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | string | Current application running state (must be one of the following: *Stopped*, *Started*, *Hidden*) |

> The *application name* argument shall be passed as the index to the property, e.g. *DIALServer.1.state@YouTube*.

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 22 | ```ERROR_UNKNOWN_KEY``` | Specified application does not exist |
| 5 | ```ERROR_ILLEGAL_STATE``` | Specified application is running in *active mode* |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DIALServer.1.state@YouTube"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "Stopped"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DIALServer.1.state@YouTube",
    "params": "Stopped"
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

The following events are provided by the DIALServer interface:

DIALServer interface events:

| Event | Description |
| :-------- | :-------- |
| [start](#event.start) | Signals that application launch (or show if previously hidden) was requested over DIAL |
| [stop](#event.stop) | Signals that application stop was requested over DIAL |
| [hide](#event.hide) | Signals that application hide was requested over DIAL |
| [show](#event.show) | Signals that application show was requested over DIAL |
| [change](#event.change) | Signals that application URL change was requested over DIAL |


<a name="event.start"></a>
## *start <sup>event</sup>*

Signals that application launch (or show if previously hidden) was requested over DIAL.

### Description

This event is sent out only for un-managed applications (i.e. in *passive mode*).

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.application | string | Application name |
| params?.parameters | string | <sup>*(optional)*</sup> Additional application-specific parameters |
| params?.payload | string | <sup>*(optional)*</sup> Additional application-specific payload |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.start",
    "params": {
        "application": "YouTube",
        "parameters": "watch?v=zpp045FBbQY",
        "payload": "..."
    }
}
```

<a name="event.stop"></a>
## *stop <sup>event</sup>*

Signals that application stop was requested over DIAL.

### Description

This event is sent out only for un-managed applications (i.e. in *passive mode*).

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.application | string | Application name |
| params?.parameters | string | <sup>*(optional)*</sup> Additional application-specific parameters |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.stop",
    "params": {
        "application": "YouTube",
        "parameters": "watch?v=zpp045FBbQY"
    }
}
```

<a name="event.hide"></a>
## *hide <sup>event</sup>*

Signals that application hide was requested over DIAL.

### Description

This event is sent out only for un-managed applications (i.e. in *passive mode*).

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.application | string | Application name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.hide",
    "params": {
        "application": "YouTube"
    }
}
```

<a name="event.show"></a>
## *show <sup>event</sup>*

Signals that application show was requested over DIAL.

> This API is **deprecated** and may be removed in the future. It is no longer recommended for use in new implementations.

### Description

This event is sent out only for un-managed applications (i.e. in *passive mode*).

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.application | string | Application name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.show",
    "params": {
        "application": "YouTube"
    }
}
```

<a name="event.change"></a>
## *change <sup>event</sup>*

Signals that application URL change was requested over DIAL.

> This API is **deprecated** and may be removed in the future. It is no longer recommended for use in new implementations.

### Description

This event is sent out only for un-managed applications (i.e. in *passive mode*).

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.application | string | Application name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.change",
    "params": {
        "application": "YouTube"
    }
}
```

