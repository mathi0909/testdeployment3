<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.ConnectionProperties_API"></a>
# ConnectionProperties API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

ConnectionProperties interface for Thunder framework.

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

This document describes purpose and functionality of the ConnectionProperties interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

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

ConnectionProperties JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the ConnectionProperties interface:

ConnectionProperties interface methods:

| Method | Description |
| :-------- | :-------- |
| [edid](#method.edid) | TV's Extended Display Identification Data |
| [widthincentimeters](#method.widthincentimeters) | Horizontal size in centimeters |
| [heightincentimeters](#method.heightincentimeters) | Vertical size in centimeters |


<a name="method.edid"></a>
## *edid <sup>method</sup>*

TV's Extended Display Identification Data.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.length | integer |  |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.length | integer |  |
| result.data | string |  |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.edid",
    "params": {
        "length": 0
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "length": 0,
        "data": "..."
    }
}
```

<a name="method.widthincentimeters"></a>
## *widthincentimeters <sup>method</sup>*

Horizontal size in centimeters.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| width | integer | width in cm |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.widthincentimeters"
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

<a name="method.heightincentimeters"></a>
## *heightincentimeters <sup>method</sup>*

Vertical size in centimeters.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| heigth | integer |  |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.heightincentimeters"
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

<a name="head.Properties"></a>
# Properties

The following properties are provided by the ConnectionProperties interface:

ConnectionProperties interface properties:

| Property | Description |
| :-------- | :-------- |
| [isaudiopassthrough](#property.isaudiopassthrough) <sup>RO</sup> | Current audio passthrough status on HDMI |
| [connected](#property.connected) <sup>RO</sup> | Current HDMI connection status |
| [width](#property.width) <sup>RO</sup> | Horizontal resolution of TV |
| [height](#property.height) <sup>RO</sup> | Vertical resolution of TV |
| [verticalfreq](#property.verticalfreq) <sup>RO</sup> | Vertical Frequency |
| [hdcpprotection](#property.hdcpprotection) | HDCP protocol used for transmission |
| [portname](#property.portname) <sup>RO</sup> | Video output port on the STB used for connection to TV |


<a name="property.isaudiopassthrough"></a>
## *isaudiopassthrough <sup>property</sup>*

Provides access to the current audio passthrough status on HDMI.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| passthru | boolean | enabled/disabled |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.isaudiopassthrough"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": false
}
```

<a name="property.connected"></a>
## *connected <sup>property</sup>*

Provides access to the current HDMI connection status.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| isconnected | boolean | connected/disconnected |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.connected"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": false
}
```

<a name="property.width"></a>
## *width <sup>property</sup>*

Provides access to the horizontal resolution of TV.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| width | integer |  width of TV in pixels |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.width"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0
}
```

<a name="property.height"></a>
## *height <sup>property</sup>*

Provides access to the vertical resolution of TV.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| height | integer |  height of TV in pixels |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.height"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0
}
```

<a name="property.verticalfreq"></a>
## *verticalfreq <sup>property</sup>*

Provides access to the vertical Frequency.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| vf | integer | vertical freq |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.verticalfreq"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0
}
```

<a name="property.hdcpprotection"></a>
## *hdcpprotection <sup>property</sup>*

Provides access to the HDCP protocol used for transmission.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| value | string | protocol (must be one of the following: *HdcpUnencrypted*, *Hdcp1X*, *Hdcp2X*, *HdcpAuto*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.hdcpprotection"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "HdcpUnencrypted"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.hdcpprotection",
    "params": "HdcpUnencrypted"
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

<a name="property.portname"></a>
## *portname <sup>property</sup>*

Provides access to the video output port on the STB used for connection to TV.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| name | string | video output port name |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "ConnectionProperties.1.portname"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "..."
}
```

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the ConnectionProperties interface:

ConnectionProperties interface events:

| Event | Description |
| :-------- | :-------- |
| [updated](#event.updated) |  |


<a name="event.updated"></a>
## *updated <sup>event</sup>*

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.event | string |  (must be one of the following: *PreResolutionChange*, *PostResolutionChange*, *HdmiChange*, *HdcpChange*) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.updated",
    "params": {
        "event": "PreResolutionChange"
    }
}
```

