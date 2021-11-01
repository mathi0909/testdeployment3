<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.BrowserSecurity_API"></a>
# BrowserSecurity API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

BrowserSecurity interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the BrowserSecurity interface. It includes detailed specification about its properties provided.

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

BrowserSecurity JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the BrowserSecurity interface:

BrowserSecurity interface properties:

| Property | Description |
| :-------- | :-------- |
| [securityprofile](#property.securityprofile) | Security profile for secure connections |
| [mixedcontentpolicy](#property.mixedcontentpolicy) | Mixed content policy |


<a name="property.securityprofile"></a>
## *securityprofile <sup>property</sup>*

Provides access to the security profile for secure connections.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| profile | string | Security profile for secure connections |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "BrowserSecurity.1.securityprofile"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "compatible"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "BrowserSecurity.1.securityprofile",
    "params": "compatible"
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

<a name="property.mixedcontentpolicy"></a>
## *mixedcontentpolicy <sup>property</sup>*

Provides access to the mixed content policy.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| policy | string | Mixed content policy type (must be one of the following: *allowed*, *blocked*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "BrowserSecurity.1.mixedcontentpolicy"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "allowed"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "BrowserSecurity.1.mixedcontentpolicy",
    "params": "allowed"
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

