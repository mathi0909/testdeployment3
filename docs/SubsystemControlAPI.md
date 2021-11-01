<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Subsystem_Control_API"></a>
# Subsystem Control API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

SubsystemControl interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the SubsystemControl interface. It includes detailed specification about its methods provided.

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

SubsystemControl JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the SubsystemControl interface:

SubsystemControl interface methods:

| Method | Description |
| :-------- | :-------- |
| [activate](#method.activate) | Activates a subsystem |
| [deactivate](#method.deactivate) | Deactivates a subsystem |


<a name="method.activate"></a>
## *activate <sup>method</sup>*

Activates a subsystem.

### Description

This method allows a subsystem to be activated from the outside. This is usefull in case Thunder can not determine the availability of a subsystem but it needs to be triggered from the outside.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.system | string | Subsystem to activate (must be one of the following: *platform*, *network*, *internet*, *time*, *security*, *location*, *identifier*, *provisioning*, *decryption*, *bluetooth*, *websource*, *graphics*, *streaming*) |
| params?.configuration | string | <sup>*(optional)*</sup> A JSON string that holds the information applicable to the subsystem to be activated |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | number | The result of the activating anythin unequal to 0 means somthing failed |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "SubsystemControl.1.activate",
    "params": {
        "system": "network",
        "configuration": "..."
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0
}
```

<a name="method.deactivate"></a>
## *deactivate <sup>method</sup>*

Deactivates a subsystem.

### Description

This method allows a subsystem to be deactivated from the outside. This is usefull in case Thunder can not determine the availability of a subsystem but it needs to be triggered from the outside.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | string | Subsystem to deactivate (must be one of the following: *platform*, *network*, *internet*, *time*, *security*, *location*, *identifier*, *provisioning*, *decryption*, *bluetooth*, *websource*, *graphics*, *streaming*) |

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
    "method": "SubsystemControl.1.deactivate",
    "params": "network"
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

