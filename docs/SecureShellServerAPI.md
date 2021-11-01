<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.SecureShell_Server_API"></a>
# SecureShell Server API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

SecureShellServer interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the SecureShellServer interface. It includes detailed specification about its methods provided.

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

SecureShell Server JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the SecureShellServer interface:

SecureShellServer interface methods:

| Method | Description |
| :-------- | :-------- |
| [get active sessions count](#method.get_active_sessions_count) | Get count of currently active SSH client sessions maintained by SecureShell SSH Service |
| [get active sessions info](#method.get_active_sessions_info) <sup>RO</sup> | Get details of currently active SSH client sessions maintained by SecureShell SSH Service |
| [close client session](#method.close_client_session) | Close and active SSH client session |


<a name="method.get_active_sessions_count"></a>
## *get_active_sessions_count <sup>method</sup>*

Get count of currently active SSH client sessions maintained by SecureShell SSH Service.

### Description

With this method SecureShell SSH service shall provide the count of active SSH client sessions.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | number | Number of client sessions count |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | Failed to get client sessions count |
| 2 | ```ERROR_UNAVAILABLE``` | Unknown error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "SecureShellServer.1.get_active_sessions_count"
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

<a name="method.get_active_sessions_info"></a>
## *get_active_sessions_info <sup>method</sup>*

Get details of currently active SSH client sessions maintained by SecureShell SSH Service.

### Description

With this method SecureShell SSH service shall provide the full details of active SSH client sessions.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | array |  |
| result[#] | object |  |
| result[#].pid | number | SSH client process ID |
| result[#].ipaddress | string | SSH client connected from this IP address |
| result[#].timestamp | string | SSH client connected at this timestamp |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | Failed to get client sessions details |
| 2 | ```ERROR_UNAVAILABLE``` | Unknown error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "SecureShellServer.1.get_active_sessions_info"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "pid": 268,
            "ipaddress": "192.168.33.57",
            "timestamp": "Sun Jun 30 21:49:08 2019"
        }
    ]
}
```

<a name="method.close_client_session"></a>
## *close_client_session <sup>method</sup>*

Close and active SSH client session.

### Description

With this method SecureShell an active SSH client session shall be closed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.clientpid | string | SSH client process id |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | Failed to close SSH client session |
| 2 | ```ERROR_UNAVAILABLE``` | Unknown error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "SecureShellServer.1.close_client_session",
    "params": {
        "clientpid": "268"
    }
}
```

