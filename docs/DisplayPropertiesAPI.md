<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.DisplayProperties_API"></a>
# DisplayProperties API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

DisplayProperties interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the DisplayProperties interface. It includes detailed specification about its properties provided.

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

DisplayProperties JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the DisplayProperties interface:

DisplayProperties interface properties:

| Property | Description |
| :-------- | :-------- |
| [colorspace](#property.colorspace) <sup>RO</sup> | Provides access to the display's Colour space (chroma subsampling format) |
| [framerate](#property.framerate) <sup>RO</sup> | Provides access to Frame Rate |
| [colourdepth](#property.colourdepth) <sup>RO</sup> | Provides access to display's colour Depth |
| [colorimetry](#property.colorimetry) <sup>RO</sup> | Provides access to display's colorimetry |
| [quantizationrange](#property.quantizationrange) <sup>RO</sup> | Provides access to display's Qauntization Range |
| [eotf](#property.eotf) <sup>RO</sup> | Provides access to display's Electro optical transfer function |


<a name="property.colorspace"></a>
## *colorspace <sup>property</sup>*

Provides access to the provides access to the display's Colour space (chroma subsampling format).

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| cs | string | colour space (must be one of the following: *FormatUnknown*, *FormatOther*, *FormatRgb444*, *FormatYcbcr444*, *FormatYcbcr422*, *FormatYcbcr420*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.colorspace"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "FormatUnknown"
}
```

<a name="property.framerate"></a>
## *framerate <sup>property</sup>*

Provides access to the provides access to Frame Rate.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| rate | string | frame rate (must be one of the following: *FramerateUnknown*, *Framerate23976*, *Framerate24*, *Framerate25*, *Framerate2997*, *Framerate30*, *Framerate47952*, *Framerate48*, *Framerate50*, *Framerate5994*, *Framerate60*, *Framerate11988*, *Framerate120*, *Framerate144*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.framerate"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "FramerateUnknown"
}
```

<a name="property.colourdepth"></a>
## *colourdepth <sup>property</sup>*

Provides access to the provides access to display's colour Depth.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| colour | string | colour depth (must be one of the following: *ColordepthUnknown*, *Colordepth8Bit*, *Colordepth10Bit*, *Colordepth12Bit*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.colourdepth"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "ColordepthUnknown"
}
```

<a name="property.colorimetry"></a>
## *colorimetry <sup>property</sup>*

Provides access to the provides access to display's colorimetry.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| colorimetry | array | display colorimetry |
| colorimetry[#] | string |  (must be one of the following: *ColorimetryUnknown*, *ColorimetryOther*, *ColorimetrySmpte170M*, *ColorimetryBt709*, *ColorimetryXvycc601*, *ColorimetryXvycc709*, *ColorimetrySycc601*, *ColorimetryOpycc601*, *ColorimetryOprgb*, *ColorimetryBt2020Yccbcbrc*, *ColorimetryBt2020RgbYcbcr*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.colorimetry"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        "ColorimetryUnknown"
    ]
}
```

<a name="property.quantizationrange"></a>
## *quantizationrange <sup>property</sup>*

Provides access to the provides access to display's Qauntization Range.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| qr | string | quantization range (must be one of the following: *QuantizationrangeUnknown*, *QuantizationrangeLimited*, *QuantizationrangeFull*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.quantizationrange"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "QuantizationrangeUnknown"
}
```

<a name="property.eotf"></a>
## *eotf <sup>property</sup>*

Provides access to the provides access to display's Electro optical transfer function.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| eotf | string | display's EOTF (must be one of the following: *EotfUnknown*, *EotfOther*, *EotfBt1886*, *EotfBt2100*, *EotfSmpteSt2084*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DisplayProperties.1.eotf"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "EotfUnknown"
}
```

