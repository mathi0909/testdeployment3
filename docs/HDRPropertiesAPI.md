<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.HDRProperties_API"></a>
# HDRProperties API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

HDRProperties interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the HDRProperties interface. It includes detailed specification about its properties provided.

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

HDRProperties JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the HDRProperties interface:

HDRProperties interface properties:

| Property | Description |
| :-------- | :-------- |
| [tvcapabilities](#property.tvcapabilities) <sup>RO</sup> | HDR formats supported by TV |
| [stbcapabilities](#property.stbcapabilities) <sup>RO</sup> | HDR formats supported by STB |
| [hdrsetting](#property.hdrsetting) <sup>RO</sup> | HDR format in use |


<a name="property.tvcapabilities"></a>
## *tvcapabilities <sup>property</sup>*

Provides access to the HDR formats supported by TV.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| type | array | HDR formats supported by TV |
| type[#] | string |  (must be one of the following: *HdrOff*, *Hdr10*, *Hdr10Plus*, *HdrHlg*, *HdrDolbyvision*, *HdrTechnicolor*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "HDRProperties.1.tvcapabilities"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "HdrOff"
    ]
}
```

<a name="property.stbcapabilities"></a>
## *stbcapabilities <sup>property</sup>*

Provides access to the HDR formats supported by STB.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| type | array | HDR formats supported by STB |
| type[#] | string |  (must be one of the following: *HdrOff*, *Hdr10*, *Hdr10Plus*, *HdrHlg*, *HdrDolbyvision*, *HdrTechnicolor*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "HDRProperties.1.stbcapabilities"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "HdrOff"
    ]
}
```

<a name="property.hdrsetting"></a>
## *hdrsetting <sup>property</sup>*

Provides access to the HDR format in use.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| type | string | HDR format (must be one of the following: *HdrOff*, *Hdr10*, *Hdr10Plus*, *HdrHlg*, *HdrDolbyvision*, *HdrTechnicolor*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "HDRProperties.1.hdrsetting"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "HdrOff"
}
```

