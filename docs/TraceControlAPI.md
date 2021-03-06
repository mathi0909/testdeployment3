<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Trace_Control_API"></a>
# Trace Control API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

TraceControl interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the TraceControl interface. It includes detailed specification about its methods provided.

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

TraceControl JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the TraceControl interface:

TraceControl interface methods:

| Method | Description |
| :-------- | :-------- |
| [status](#method.status) | Retrieves general information |
| [set](#method.set) | Sets traces |


<a name="method.status"></a>
## *status <sup>method</sup>*

Retrieves general information.

### Description

Retrieves the actual trace status information for targeted module and category, if either category nor module is given, all information is returned. It will retrieves the details about console status and remote address(port and binding address), if these are configured.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.module | string | Module name |
| params.category | string | Category name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.console | boolean | Config attribute (Console) |
| result.remote | object |  |
| result.remote.port | number | Config attribute (port) |
| result.remote.binding | string | Config attribute (binding) |
| result.settings | array |  |
| result.settings[#] | object |  |
| result.settings[#].module | string | Module name |
| result.settings[#].category | string | Category name |
| result.settings[#].state | string | State value (must be one of the following: *enabled*, *disabled*, *tristated*) |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "TraceControl.1.status",
    "params": {
        "module": "Plugin_Monitor",
        "category": "Information"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "console": false,
        "remote": {
            "port": 2200,
            "binding": "0.0.0.0"
        },
        "settings": [
            {
                "module": "Plugin_Monitor",
                "category": "Information",
                "state": "disabled"
            }
        ]
    }
}
```

<a name="method.set"></a>
## *set <sup>method</sup>*

Sets traces.

### Description

Disables/enables all/select category traces for particular module.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.module | string | Module name |
| params.category | string | Category name |
| params.state | string | State value (must be one of the following: *enabled*, *disabled*, *tristated*) |

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
    "method": "TraceControl.1.set",
    "params": {
        "module": "Plugin_Monitor",
        "category": "Information",
        "state": "disabled"
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

