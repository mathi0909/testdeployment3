<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Display_Info_API"></a>
# Display Info API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

DisplayInfo interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the DisplayInfo interface. It includes detailed specification about its properties provided and notifications sent.

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

DisplayInfo JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the DisplayInfo interface:

DisplayInfo interface properties:

| Property | Description |
| :-------- | :-------- |
| [displayinfo](#property.displayinfo) <sup>RO</sup> | Display general information |


<a name="property.displayinfo"></a>
## *displayinfo <sup>property</sup>*

Provides access to the display general information.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Display general information |
| (property).totalgpuram | number | Total GPU DRAM memory (in bytes) |
| (property).freegpuram | number | Free GPU DRAM memory (in bytes) |
| (property).audiopassthrough | boolean | Audio Pass through is support for this device |
| (property).connected | boolean | HDMI display connection status |
| (property).width | number | Width of the connected HDMI display |
| (property).height | number | Height of the connected HDMI display |
| (property).hdcpprotection | string | HDCP Protection (must be one of the following: *Unencrypted*, *HDCP1x*, *HDCP2x*) |
| (property).hdrtype | string | HDR Type used (must be one of the following: *HDROff*, *HDR10*, *HDR10Plus*, *HDRDolbyVision*, *HDRTechnicolor*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayInfo.1.displayinfo"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "totalgpuram": 381681664,
        "freegpuram": 358612992,
        "audiopassthrough": false,
        "connected": true,
        "width": 1280,
        "height": 720,
        "hdcpprotection": "HDCP1x",
        "hdrtype": "HDROff"
    }
}
```

<a name="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the DisplayInfo interface:

DisplayInfo interface events:

| Event | Description |
| :-------- | :-------- |
| [updated](#event.updated) | Notifies about a change/update in the connection |


<a name="event.updated"></a>
## *updated <sup>event</sup>*

Notifies about a change/update in the connection.

### Description

Register to this event to be notified about any change in the connection

### Parameters

This event carries no parameters.

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.updated"
}
```

