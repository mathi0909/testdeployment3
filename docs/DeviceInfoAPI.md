<!-- Generated automatically, DO NOT EDIT! -->
<a name="head.Device_Info_API"></a>
# Device Info API

**Version: 1.0**

**Status: :black_circle::white_circle::white_circle:**

DeviceInfo interface for Thunder framework.

### Table of Contents

- [Introduction](#head.Introduction)
- [Description](#head.Description)
- [Properties](#head.Properties)

<a name="head.Introduction"></a>
# Introduction

<a name="head.Scope"></a>
## Scope

This document describes purpose and functionality of the DeviceInfo interface. It includes detailed specification about its properties provided.

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

DeviceInfo JSON-RPC interface.

<a name="head.Properties"></a>
# Properties

The following properties are provided by the DeviceInfo interface:

DeviceInfo interface properties:

| Property | Description |
| :-------- | :-------- |
| [capabilities](#property.capabilities) <sup>RO</sup> | Capabilities of the STB |
| [metadata](#property.metadata) |  |
| [systeminfo](#property.systeminfo) <sup>RO</sup> | System general information |
| [addresses](#property.addresses) <sup>RO</sup> | Network interface addresses |
| [socketinfo](#property.socketinfo) <sup>RO</sup> | Socket information |


<a name="property.capabilities"></a>
## *capabilities <sup>property</sup>*

Provides access to the capabilities of the STB.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Capabilities of the STB |
| (property).hdr | boolean | Is HDR supported by this device |
| (property).atmos | boolean | Is Atmos supported by this device |
| (property).cec | boolean | Is CEC supported by this device |
| (property).hdcp | string | HDCP support (must be one of the following: *unavailable*, *hdcp_14*, *hdcp_20*, *hdcp_21*, *hdcp_22*) |
| (property).audio_outputs | array | Audio Output support |
| (property).audio_outputs[#] | string | Audio output supported by the device (must be one of the following: *other*, *rf_modulator*, *analog*, *spdif*, *hdmi*, *displayport*) |
| (property).video_outputs | array | Video Output support |
| (property).video_outputs[#] | string | Video output supported by the device (must be one of the following: *other*, *rf_modulator*, *composite*, *svideo*, *component*, *scart_rgb*, *hdmi*, *displayport*) |
| (property).output_resolutions | array | Supported resolutions |
| (property).output_resolutions[#] | string | Resolution supported by the device (must be one of the following: *unknown*, *480i*, *480p*, *576i*, *576p*, *720p*, *1080i*, *1080p*, *2160p30*, *2160p60*, *4320p30*, *4320p60*) |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.capabilities"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "hdr": false,
        "atmos": false,
        "cec": true,
        "hdcp": "hdcp_20",
        "audio_outputs": [
            "analog"
        ],
        "video_outputs": [
            "displayport"
        ],
        "output_resolutions": [
            "1080p"
        ]
    }
}
```

<a name="property.metadata"></a>
## *metadata <sup>property</sup>*

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object |  |
| (property)?.modelName | string | <sup>*(optional)*</sup> Model Name |
| (property)?.modelYear | number | <sup>*(optional)*</sup> Model Year |
| (property)?.friendlyName | string | <sup>*(optional)*</sup> friendly name |
| (property)?.systemIntegratorName | string | <sup>*(optional)*</sup> system integrator name |
| (property)?.platformName | string | <sup>*(optional)*</sup> platform name |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.metadata"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "modelName": "model A",
        "modelYear": 2020,
        "friendlyName": "my device",
        "systemIntegratorName": "Christophe A",
        "platformName": "linux"
    }
}
```

#### Set Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.metadata",
    "params": {
        "modelName": "model A",
        "modelYear": 2020,
        "friendlyName": "my device",
        "systemIntegratorName": "Christophe A",
        "platformName": "linux"
    }
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

<a name="property.systeminfo"></a>
## *systeminfo <sup>property</sup>*

Provides access to the system general information.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | System general information |
| (property).version | string | Software version (in form *version#hashtag*) |
| (property).uptime | number | System uptime (in seconds) |
| (property).totalram | number | Total installed system RAM memory (in bytes) |
| (property).freeram | number | Free system RAM memory (in bytes) |
| (property).totalswap | number | Total swap space (in bytes) |
| (property).freeswap | number | swap space still available (in bytes) |
| (property).devicename | string | Host name |
| (property).cpuload | string | Current CPU load (percentage) |
| (property).cpuloadavg | object | CPU load average |
| (property).cpuloadavg.avg1min | number | 1min cpuload average |
| (property).cpuloadavg.avg5min | number | 5min cpuload average |
| (property).cpuloadavg.avg15min | number | 15min cpuload average |
| (property).serialnumber | string | Device serial number |
| (property).time | string | Current system date and time |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.systeminfo"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "version": "1.0#14452f612c3747645d54974255d11b8f3b4faa54",
        "uptime": 120,
        "totalram": 655757312,
        "freeram": 563015680,
        "totalswap": 789132680,
        "freeswap": 789132680,
        "devicename": "buildroot",
        "cpuload": "2",
        "cpuloadavg": {
            "avg1min": 789132680,
            "avg5min": 789132680,
            "avg15min": 789132680
        },
        "serialnumber": "WPEuCfrLF45",
        "time": "Mon, 11 Mar 2019 14:38:18"
    }
}
```

<a name="property.addresses"></a>
## *addresses <sup>property</sup>*

Provides access to the network interface addresses.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | array | Network interface addresses |
| (property)[#] | object |  |
| (property)[#].name | string | Interface name |
| (property)[#].mac | string | Interface MAC address |
| (property)[#]?.ip | array | <sup>*(optional)*</sup>  |
| (property)[#]?.ip[#] | string | <sup>*(optional)*</sup> Interface IP address |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.addresses"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "name": "lo",
            "mac": "00:00:00:00:00",
            "ip": [
                "127.0.0.1"
            ]
        }
    ]
}
```

<a name="property.socketinfo"></a>
## *socketinfo <sup>property</sup>*

Provides access to the socket information.

> This property is **read-only**.

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Socket information |
| (property)?.total | number | <sup>*(optional)*</sup>  |
| (property)?.open | number | <sup>*(optional)*</sup>  |
| (property)?.link | number | <sup>*(optional)*</sup>  |
| (property)?.exception | number | <sup>*(optional)*</sup>  |
| (property)?.shutdown | number | <sup>*(optional)*</sup>  |
| (property).runs | number | Number of runs |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.1.socketinfo"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "total": 0,
        "open": 0,
        "link": 0,
        "exception": 0,
        "shutdown": 0,
        "runs": 1
    }
}
```

