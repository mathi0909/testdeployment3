<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Butler_API"></a>
# Butler API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

Butler interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the Butler interface. It includes detailed specification about its properties provided and notifications sent.

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

Butler JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the Butler interface:

Butler interface properties:

| Property | Description |
| :-------- | :-------- |
| [orphans](#property.orphans) <sup>RO</sup> | List of devices not attached to any nodes |
| [device](#property.device) <sup>RO</sup> | Device specific information |
| [value](#property.value) | Set or Get the value of the device |
| [group](#property.group) | Get the names  part of a group |
| [link](#property.link) | link an external ID to a node |
| [move](#property.move) | move a node to another location |
| [branch](#property.branch) | create a new group |
| [delete](#property.delete) | destroy an existing, empty group |


<a name="property.orphans"></a>
## *orphans <sup>property</sup>*

Provides access to the list of devices not attached to any nodes.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | array | List of devices not attached to any nodes |
| (property)[#] | object |  |
| (property)[#].id | integer | Identifier of the device |
| (property)[#].name | string | Name given to this device |
| (property)[#]?.callsign | string | <sup>*(optional)*</sup> The callsign that owns this external |
| (property)[#].basic | string | Basic description of the device (measure or control) (must be one of the following: *control*, *measure*) |
| (property)[#].specific | string | More eleborated description of the device (must be one of the following: *general*, *electricity*, *water*, *gas*, *air*, *smoke*, *carbonMonoxide*, *carbonDioxide*, *temperature*, *accessControl*, *burglar*, *powerManagement*, *system*, *emergency*, *clock*) |
| (property)[#].dimension | string | What is the dimension of the value that is returned by the device (must be one of the following: *logic*, *percentage*, *kwh*, *kvah*, *pulses*, *degrees*, *units*) |
| (property)[#].minimum | integer | Minimum value that the device can reach |
| (property)[#].decimals | integer | Number of digits that should be considered fractional |
| (property)[#].maximum | integer | Maximum value that the device can reach |
| (property)[#]?.value | number | <sup>*(optional)*</sup>  |

> The *module index* argument shall be passed as the index to the property, e.g. *Butler.1.orphans@[ {}, {}, {} ]*. 0 = any module, >0 orphans from the requested module.

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Butler.1.orphans@[ {}, {}, {} ]"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "id": 123456,
            "name": "/kitchen/ceiling/dimmer",
            "callsign": "VirtualControl",
            "basic": "measure",
            "specific": "electricity",
            "dimension": "logic",
            "minimum": -80,
            "decimals": 0,
            "maximum": 200,
            "value": 1
        }
    ]
}
```

<a name="property.device"></a>
## *device <sup>property</sup>*

Provides access to the device specific information.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Device specific information |
| (property).id | integer | Identifier of the device |
| (property).name | string | Name given to this device |
| (property)?.callsign | string | <sup>*(optional)*</sup> The callsign that owns this external |
| (property).basic | string | Basic description of the device (measure or control) (must be one of the following: *control*, *measure*) |
| (property).specific | string | More eleborated description of the device (must be one of the following: *general*, *electricity*, *water*, *gas*, *air*, *smoke*, *carbonMonoxide*, *carbonDioxide*, *temperature*, *accessControl*, *burglar*, *powerManagement*, *system*, *emergency*, *clock*) |
| (property).dimension | string | What is the dimension of the value that is returned by the device (must be one of the following: *logic*, *percentage*, *kwh*, *kvah*, *pulses*, *degrees*, *units*) |
| (property).minimum | integer | Minimum value that the device can reach |
| (property).decimals | integer | Number of digits that should be considered fractional |
| (property).maximum | integer | Maximum value that the device can reach |
| (property)?.value | number | <sup>*(optional)*</sup>  |

> The *device name* argument shall be passed as the index to the property, e.g. *Butler.1.device@The name of the device or the Id of the device*.

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 22 | ```ERROR_UNKNOWN_KEY``` | Unknown device |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Butler.1.device@The name of the device or the Id of the device"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "id": 123456,
        "name": "/kitchen/ceiling/dimmer",
        "callsign": "VirtualControl",
        "basic": "measure",
        "specific": "electricity",
        "dimension": "logic",
        "minimum": -80,
        "decimals": 0,
        "maximum": 200,
        "value": 1
    }
}
```

<a name="property.value"></a>
## *value <sup>property</sup>*

Provides access to the set or Get the value of the device.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | number | Set or Get the value of the device |

> The *device name* argument shall be passed as the index to the property, e.g. *Butler.1.value@The name of the device (name) or the numerical identifier of the device*.

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 22 | ```ERROR_UNKNOWN_KEY``` | Unknown device |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Butler.1.value@The name of the device (name) or the numerical identifier of the device"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 1
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Butler.1.value@The name of the device (name) or the numerical identifier of the device",
    "params": 1
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

<a name="property.group"></a>
## *group <sup>property</sup>*

Provides access to the get the names  part of a group.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Get the names  part of a group |
| (property)?.parent | integer | <sup>*(optional)*</sup> Identifier of the group to wich this group belongs |
| (property)?.id | integer | <sup>*(optional)*</sup> Identifier of this group |
| (property)?.base | string | <sup>*(optional)*</sup> Path identifier leading up to this group |
| (property)?.members | array | <sup>*(optional)*</sup>  |
| (property)?.members[#] | object | <sup>*(optional)*</sup>  |
| (property)?.members[#]?.name | string | <sup>*(optional)*</sup> Name of a room or sensor |
| (property)?.members[#]?.id | integer | <sup>*(optional)*</sup> Identifier of this memeber |
| (property)?.members[#]?.type | string | <sup>*(optional)*</sup> Type ot this member |
| (property)?.members[#]?.callsign | string | <sup>*(optional)*</sup> The callsign that owns this external |
| (property)?.members[#]?.basic | string | <sup>*(optional)*</sup> Basic description of the device (measure or control) (must be one of the following: *control*, *measure*) |
| (property)?.members[#]?.value | number | <sup>*(optional)*</sup> Set or Get the value of the device |
| (property)?.members[#]?.children | integer | <sup>*(optional)*</sup> number of children, this element has |

