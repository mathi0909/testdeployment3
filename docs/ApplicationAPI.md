<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Application_API"></a>
# Application API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

Application interface for Thunder framework.

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

This document describes purpose and functionality of the Application interface. It includes detailed specification about its methods and properties provided, as well as notifications sent.

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

Application JSON-RPC interface.

<a name="head.Methods"></a>
# Methods

The following methods are provided by the Application interface:

Application interface methods:

| Method | Description |
| :-------- | :-------- |
| [reset](#method.reset) | Resets application data |


<a name="method.reset"></a>
## *reset <sup>method</sup>*

Resets application data.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| type | string | Type of reset to perform (must be one of the following: *Factory*, *Cache*, *Credentials*, *Recordings*) |

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
    "method": "Application.1.reset",
    "params": "Factory"
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

<a name="head.Properties"></a>
# Properties

The following properties are provided by the Application interface:

Application interface properties:

| Property | Description |
| :-------- | :-------- |
| [identifier](#property.identifier) <sup>RO</sup> | Application-specific identification string |
| [contentlink](#property.contentlink) <sup>WO</sup> | URI of the associated application-specific content |
| [launchpoint](#property.launchpoint) | Application launching point |
| [visible](#property.visible) | Current application visibility |
| [language](#property.language) | Current application user interface language |


<a name="property.identifier"></a>
## *identifier <sup>property</sup>*

Provides access to the application-specific identification string.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | string | Identifier string |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.identifier"
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

<a name="property.contentlink"></a>
## *contentlink <sup>property</sup>*

Provides access to the URI of the associated application-specific content.

> This property is **write-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| link | string | Content URI |

### Example

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.contentlink",
    "params": "https://youtube.com"
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

<a name="property.launchpoint"></a>
## *launchpoint <sup>property</sup>*

Provides access to the application launching point.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| point | string | Application launching point (must be one of the following: *Undefined*, *Dial*, *DedicatedButton*, *DedicatedIcon*, *ApplicationList*, *IntegratedTile*, *SearchResult*, *SearchContinuation*, *VoiceControl*, *VoiceSearchResult*, *VisualGesture*, *TouchGesture*, *EpgGrid*, *ChannelNumber*, *ChannelZap*, *ChannelBar*, *WebBrowser*, *PowerOn*, *PowerOnFromDedicatedButton*, *SuspendedPowerOn*, *Restart*, *SuspendedRestart*, *ResumedFromScreenSaver*, *ResumedFromStandby*, *BannerAd*, *TitleRecommendation*, *ApplicationPromotion*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.launchpoint"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "Undefined"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.launchpoint",
    "params": "Undefined"
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

<a name="property.visible"></a>
## *visible <sup>property</sup>*

Provides access to the current application visibility.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| visiblity | boolean | Current application visibility |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.visible"
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

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.visible",
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

<a name="property.language"></a>
## *language <sup>property</sup>*

Provides access to the current application user interface language.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| language | string | Language string as per RFC5646 |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.language"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "en"
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "Application.1.language",
    "params": "en"
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

The following events are provided by the Application interface:

Application interface events:

| Event | Description |
| :-------- | :-------- |
| [visibilitychange](#event.visibilitychange) | Application visibility changes |


<a name="event.visibilitychange"></a>
## *visibilitychange <sup>event</sup>*

Application visibility changes.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| hidden | boolean | Denotes if application is currently hidden |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.1.visibilitychange",
    "params": false
}
```

