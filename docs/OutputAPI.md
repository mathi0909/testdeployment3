<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Output_API"></a>
# Output API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

Output interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)
- [Notifications](#head.Notifications)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the Output interface. It includes detailed specification about its properties provided and notifications sent.

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

Output JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the Output interface:

Dolby Output interface properties:

| Property | Description |
| :-------- | :-------- |
| [dolby atmosmetadata](#property.dolby_atmosmetadata) <sup>RO</sup> | Atmos capabilities of Sink |
| [dolby soundmode](#property.dolby_soundmode) <sup>RO</sup> | Sound Mode - Mono/Stereo/Surround |
| [dolby enableatmosoutput](#property.dolby_enableatmosoutput) <sup>WO</sup> | Enable Atmos Audio Output |
| [dolby mode](#property.dolby_mode) | Dolby Mode |


<a name="property.dolby_atmosmetadata"></a>
## *dolby_atmosmetadata <sup>property</sup>*

Provides access to the atmos capabilities of Sink.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| supported | boolean | Atmos capabilities of Sink |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Output.1.dolby_atmosmetadata"
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

<a name="property.dolby_soundmode"></a>
## *dolby_soundmode <sup>property</sup>*

Provides access to the sound Mode - Mono/Stereo/Surround.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| mode | string | Sound Mode - Mono/Stereo/Surround (must be one of the following: *Unknown*, *Mono*, *Stereo*, *Surround*, *Passthru*, *SoundmodeAuto*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Output.1.dolby_soundmode"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "Unknown"
}
```

<a name="property.dolby_enableatmosoutput"></a>
## *dolby_enableatmosoutput <sup>property</sup>*

Provides access to the enable Atmos Audio Output.

> This property is **write-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enable | boolean | enable/disable |

### Example

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Output.1.dolby_enableatmosoutput",
    "params": false
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

<a name="property.dolby_mode"></a>
## *dolby_mode <sup>property</sup>*

Provides access to the dolby Mode.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| mode | string | dolby mode type (must be one of the following: *DigitalPcm*, *DigitalPlus*, *DigitalAc3*, *Auto*, *DigitalPassthrough*, *Ms12*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Output.1.dolby_mode"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "DigitalPcm"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Output.1.dolby_mode",
    "params": "DigitalPcm"
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

The following events are provided by the Output interface:

Dolby Output interface events:

| Event | Description |
| :-------- | :-------- |
| [dolby audiomodechanged](#event.dolby_audiomodechanged) |  |


<a name="event.dolby_audiomodechanged"></a>
## *dolby_audiomodechanged <sup>event</sup>*

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.mode | string |  (must be one of the following: *Unknown*, *Mono*, *Stereo*, *Surround*, *Passthru*, *SoundmodeAuto*) |
| params.enabled | boolean |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.dolby_audiomodechanged",
    "params": {
        "mode": "Unknown",
        "enabled": false
    }
}
```

