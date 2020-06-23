# Agent API
The following are endpoints that can be used to interact with the xConnect Agent. 

**As of current release, the API is only bound to localhost or 127.0.0.1 and cannot be 
accessed by any other networked machines.** If a remote device needs to access the API, please contact
support for an HTTPS version of the API. 
        

## Get Latest Sensor Data

Used to collect the latest sensor data from all xConnect Agent sensor points

**URL** : `http://localhost:8886/getSensorLatest`

**Method** : `GET`

**Auth required** : NO

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
  {
    "SensorID": 1,
    "SensorSource": "WMI",
    "SensorName": "Network NIC1 MaxLinkSpeed",
    "SensorUnit": null,
    "SensorFullKey": "Network_NIC1_MaxLinkSpeed",
    "DataType": "Integer",
    "LatestValue": "492",
    "LocalSensorThreshold": null,
    "LocalStrictOperator": null,
    "DashboardEnabled": null,
    "GaugeEnabled": null
  },
  ... repeated list of arrays for all sensors
]
```

## Error Response

**Condition** : If route is incorrect, you will receive a not found response.

**Code** : `404 NOT FOUND`

## Submit Telemetry to xConnect

Used to collect telemetry from 3rd party applications that can POST a formed JSON object. The API
will consume this object and submit it to the xConnect Gateway and appear on your cloud dashboard.

**URL** : `http://localhost:8886/submitTelemetry`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

`uid` value should be a unique UUID per device or object. These can be generated at:
https://www.uuidgenerator.net/version4

`type` value will drive how the device is categorized on the cloud dashboard

`name` value is what the friendly name of the device will be on the cloud dashboard

`telemetry` value is a list that can be a single object or multiple objects. Each object must contain
3 "categories" that are used to assemble the telemetry key
    
Each `telemetry` list object needs to have a `primaryCategory`, `secondaryCategory`, and `tertiaryCategory` specified 
or you will receive a malformed JSON response

```json
{
  "xconnect": {
    "uid": "[unique UID per device or object]",
    "type": "[Device or Asset Type]",
    "name": "[Device Name that is human friendly]",
    "telemetry": [
      {
        "primaryCategory": "[First Value of Telemetry Key]",
        "secondaryCategory": "[Second Value of Telemetry Key]",
        "tertiaryCategory": "[Third Value of Telemetry Key]",
        "value": "[1920x1080]"
      }
    ]
  }
}
```

**Data example**

```json
{
  "xconnect": {
    "uid": "2bf2aa37-fb9c-460b-8f49-5d671017bec4",
    "type": "Display",
    "name": "Device1234567",
    "telemetry": [
      {
        "primaryCategory": "Display",
        "secondaryCategory": "Model1234",
        "tertiaryCategory": "Resolution",
        "value": "1920x1080"
      },
      {
        "primaryCategory": "Display",
        "secondaryCategory": "Model1234",
        "tertiaryCategory": "Power State",
        "value": "Standby"
      }
    ]
  }
}
```

## Success Response

**Code** : `201 OK`
