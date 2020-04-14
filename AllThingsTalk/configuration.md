# AllThingsTalk

## Payload

Using the [ABCL](https://docs.allthingstalk.com/developers/data/custom-payload-conversion/) Format we can convert the payload from the LGT-92 gps tracker

```json
{
  "name": "backpack_tracker",
  "comment": "LGT-92-AA GPS Tracker",
  "version": "0.1",
  "sense": [
    {
      "asset": "gps_location",
      "value": {
        "latitude": {
          "byte": 0,
          "bytelength": 4,
          "calculation": "val / 1000000"
        },
        "longitude": {
          "byte": 4,
          "bytelength": 4,
          "calculation": "val / 1000000"
        }
      }
    },
    {
      "asset": "battery_voltage",
      "value": {
        "byte": 8,
        "bit": 2,
        "bitlength": 14,
        "calculation": "val / 1000"
      }
    },
    {
      "asset": "alarm_status",
      "value": {
        "byte": 8,
        "bit": 1,
        "bitlength": 1,
        "type": "boolean"
      }
    }
  ]
}
```

dragino reference payload

| #bytes | 4        | 4          | 2           | 1           | 2    | 2     |
| ------ | -------- | ---------- | ----------- | ----------- | ---- | ----- |
| value  | Latitude | Longtitude | Alarm, Batt | MD, LON, FW | Roll | Pitch |

|
