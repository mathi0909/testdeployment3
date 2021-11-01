<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.PlayerProperties_API"></a>
# PlayerProperties API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

PlayerProperties interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Methods](#head.Methods)
- [Properties](#head.Properties)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the PlayerProperties interface. It includes detailed specification about its methods and properties provided.

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

PlayerProperties JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the PlayerProperties interface:

PlayerProperties interface methods:

| Method | Description |
| :-------- | :-------- |
| [audiocodecs](#method.audiocodecs) |  |
| [videocodecs](#method.videocodecs) |  |


<a name="method.audiocodecs"></a>
## *audiocodecs <sup>method</sup>*

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| codec | array |  |
| codec[#] | string |  (must be one of the following: *AudioUndefined*, *AudioAac*, *AudioAc3*, *AudioAc3Plus*, *AudioDts*, *AudioMpeg1*, *AudioMpeg2*, *AudioMpeg3*, *AudioMpeg4*, *AudioOpus*, *AudioVorbisOgg*, *AudioWav*) |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "PlayerProperties.1.audiocodecs"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "AudioUndefined"
    ]
}
```

<a name="method.videocodecs"></a>
## *videocodecs <sup>method</sup>*

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| codec | array |  |
| codec[#] | string |  (must be one of the following: *VideoUndefined*, *VideoH263*, *VideoH264*, *VideoH265*, *VideoH26510*, *VideoMpeg*, *VideoVp8*, *VideoVp9*, *VideoVp10*) |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "PlayerProperties.1.videocodecs"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "VideoUndefined"
    ]
}
```

<a name="head.Properties"></a>
# Properties

The following properties are provided by the PlayerProperties interface:

PlayerProperties interface properties:

| Property | Description |
| :-------- | :-------- |
| [resolution](#property.resolution) <sup>RO</sup> | Current Video playback resolution |
| [isaudioequivalenceenabled](#property.isaudioequivalenceenabled) <sup>RO</sup> | Checks Loudness Equivalence in platform |


<a name="property.resolution"></a>
## *resolution <sup>property</sup>*

Provides access to the current Video playback resolution.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| res | string | resolution (must be one of the following: *ResolutionUnknown*, *Resolution480I24*, *Resolution480I25*, *Resolution480I30*, *Resolution480I50*, *Resolution480I*, *Resolution480P24*, *Resolution480P25*, *Resolution480P30*, *Resolution480P50*, *Resolution480P*, *Resolution576I24*, *Resolution576I25*, *Resolution576I30*, *Resolution576I50*, *Resolution576I*, *Resolution576P24*, *Resolution576P25*, *Resolution576P30*, *Resolution576P50*, *Resolution576P*, *Resolution720P24*, *Resolution720P25*, *Resolution720P30*, *Resolution720P50*, *Resolution720P*, *Resolution1080I24*, *Resolution1080I25*, *Resolution1080I30*, *Resolution1080I50*, *Resolution1080I*, *Resolution1080P24*, *Resolution1080P25*, *Resolution1080P30*, *Resolution1080P50*, *Resolution1080P*, *Resolution2160P24*, *Resolution2160P25*, *Resolution2160P30*, *Resolution2160P50*, *Resolution2160P60*, *Resolution2160P*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "PlayerProperties.1.resolution"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "ResolutionUnknown"
}
```

<a name="property.isaudioequivalenceenabled"></a>
## *isaudioequivalenceenabled <sup>property</sup>*

Provides access to the checks Loudness Equivalence in platform.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| ae | boolean | enabled/disabled |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "PlayerProperties.1.isaudioequivalenceenabled"
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

