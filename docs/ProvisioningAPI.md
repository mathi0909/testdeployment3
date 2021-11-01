<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Provisioning_API"></a>
# Provisioning API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

Provisioning interface for Thunder framework.

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

This document describes purpose and functionality of the Provisioning interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

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

Provisioning JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the Provisioning interface:

Provisioning interface methods:

| Method | Description |
| :-------- | :-------- |
| [provision](#method.provision) | Trigers platform provision process |
| [index](#method.index) | Set the index for a provisioning key |


<a name="method.provision"></a>
## *provision <sup>method</sup>*

Trigers platform provision process.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 12 | ```ERROR_INPROGRESS``` | Provisioning in progress |
| 2 | ```ERROR_UNAVAILABLE``` | Provisioning Back Office Client not available |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Provisioning.1.provision"
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

<a name="method.index"></a>
## *index <sup>method</sup>*

Set the index for a provisioning key.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.label | string | <sup>*(optional)*</sup> The label name for which the index should be changed |
| params?.index | number | <sup>*(optional)*</sup> Index to be used for the key |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | Always null |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 2 | ```ERROR_UNAVAILABLE``` | Provisioning Back Office Client not available |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Provisioning.1.index",
    "params": {
        "label": "cobalt",
        "index": 0
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

The following properties are provided by the Provisioning interface:

Provisioning interface properties:

| Property | Description |
| :-------- | :-------- |
| [id](#property.id) <sup>RO</sup> | Provision ID |
| [state](#property.state) <sup>RO</sup> | Platform provision state |


<a name="property.id"></a>
## *id <sup>property</sup>*

Provides access to the provision ID.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | string | Provision ID |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Provisioning.1.id"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "WPE00000uCfrLF45"
}
```

<a name="property.state"></a>
## *state <sup>property</sup>*

Provides access to the platform provision state.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Platform provision state |
| (property).id | string | Provision ID value |
| (property).status | number | Provision status |
| (property).tokens | array | List of provisioned systems |
| (property).tokens[#] | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 2 | ```ERROR_UNAVAILABLE``` | Provisioning Back Office Client not available |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Provisioning.1.state"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "id": "WPE00000uCfrLF45",
        "status": 200,
        "tokens": [
            "netflix, playready"
        ]
    }
}
```

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the Provisioning interface:

Provisioning interface events:

| Event | Description |
| :-------- | :-------- |
| [provisioningchange](#event.provisioningchange) | Signals a provisioning change |


<a name="event.provisioningchange"></a>
## *provisioningchange <sup>event</sup>*

Signals a provisioning change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.status | number | Provision status |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.provisioningchange",
    "params": {
        "status": 200
    }
}
```

