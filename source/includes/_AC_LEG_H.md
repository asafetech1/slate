# AC_LEG_H
## GET| api/AC_LEG_H

Parameter | Description
--------- | -----------
target | (string) available targets are INTERNAL and REPORT by default the endpoint returns the UI and All levels.

> query example  

```json
{
  "target": "REPORT"
}
```

> Response Example

```json
[
  {
    "LEG_H_ID": "Number",
    "LEG_ID": "Number",
    "LEG_NAME": "String",
    "QR_CODE": "String",
    "H_EVENT_ID": "Number",
    "ACTION_DATE": "Date",
    "USER_ID": "Number",
    "AISLE_ID": "Number",
    "ZONE_ID": "Number",
    "BUILDING_ID": "Number",
    "ORG_ID": "Number",
    "RACKEYE_ID": "Number",
    "INSPECTION_ID": "Number/null",
    "TIMEZONE_NAME": "String",
    "EVENT": "String (the event itself)",
    "CONTEXT": "String(the context where the event took place)"
  }
]
```
### HTTP Request Example
`/api/AC_LEG_H/`  
