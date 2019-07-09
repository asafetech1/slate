# AC_AISLE_MANAGEMENT_V
## GET | AC_AISLE_MANAGEMENT_V
Returns an array of all the aisles or the aisles that matches the filter param.

> An example of a query body

```json 
{"limit":1, "where": {"AISLE_ID": {"inq": [2,3,8,1]}}, "extract": ["LEGS"]}

```
> The response body

```json
[
  {
    "COUNTRY_ID": 235,
    "ORG_ID": 3,
    "SITE_ID": 1,
    "BUILDING_ID": 1,
    "ZONE_ID": 384,
    "AISLE_ID": 8,
    "AISLE_NAME": "A1",
    "AISLE_LEG_COUNT": 2,
    "AISLE_INCIDENT_COUNT": 0,
    "AISLE_LOW_V_COUNT": 0,
    "AISLE_WARN_COUNT": 0,
    "AISLE_ALERT_COUNT": 0,
    "LEGS": [
      {
        "LEG_ID": "any",
        "AISLE_ID": "any",
        "LEG_NAME": "any",
        "QR_CODE": "any",
        "LEG_COORDINATES": "any",
        "LEG_TYPE_ID": "any",
        "RACKEYE_ENABLED": "any",
        "RACKEYE_ID": "any",
        "ACTION": ""
      }
    ]
  }
]
```

### HTTP Request

`/api/AC_AISLE_MANAGEMENT_V?filter={query}`

### CUSTOM KEYS YOU CAN USE TO QUERY THE DATA
Parameter | Default | Description
--------- | ------- | -----------
IPUI | none | Search for aisle by RACKEYE IPUI.
LEGS | none | Used with EXTRACT to extract all the legs on an aisle (please refer to the params table below).

### Query Parameters

Parameter | Description
--------- | -----------
limit | limiting the result to certain number(must not exceed 100 requests).
where | 	filter the result by cirtain condition. syntax: {"where": {"column_name": value}}.
extract [ ]| extracts legs for each aisle. syntax: {"extract":["LEGS"]}.
inq [ ]| show result for any values that matches the values in the array . syntax: {"column_name": {"inq": [v1, v2, v3]}}.
neq [ ]| show result for any values that that does not match the values in the array . syntax: {"column_name": {"neq": [v1, v2, v3]}}.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## GET | AC_AISLE_MANAGEMENT_V/customcount
Count instances of the model matched by where from the data source (note you don't need to use "where" clause in your query body)

### HTTP Request

`/api/AC_AISLE_MANAGEMENT_V/count?where={query}`

> An example of a query body

```json 
{"ZONE_ID": 385, "AISLE_ID": 2381}

```

> The response body

```json
{
  "count": 1
}
```
## GET | AC_AISLE_MANAGEMENT_V/findOne
Returns the latest instance or you can use the filter param to return certain instance

### HTTP Request

`/api/AC_AISLE_MANAGEMENT_V/findOne?filter={query}`

> An example of a query body

```json 
{"where": {"ZONE_ID": 385}}

```

> response body

```json
{
  "COUNTRY_ID": 235,
  "ORG_ID": 3,
  "SITE_ID": 1,
  "BUILDING_ID": 1,
  "ZONE_ID": 385,
  "AISLE_ID": 2560,
  "AISLE_NAME": "Mark's Aisle",
  "AISLE_LEG_COUNT": 13,
  "AISLE_INCIDENT_COUNT": 13,
  "AISLE_LOW_V_COUNT": 0,
  "AISLE_WARN_COUNT": 10,
  "AISLE_ALERT_COUNT": 3
}
```
## GET | AC_AISLE_MANAGEMENT_V/search
Returns the latest instance or you can use the filter param to return certain instance

### HTTP Request

`http://localhost:3019/api/AC_AISLE_MANAGEMENT_V/search?filter={query}`

> An example of a query body

```json 
{"where": {"ZONE_ID": 385}}

```

> response body

```json
{
  "COUNTRY_ID": 235,
  "ORG_ID": 3,
  "SITE_ID": 1,
  "BUILDING_ID": 1,
  "ZONE_ID": 385,
  "AISLE_ID": 2560,
  "AISLE_NAME": "Mark's Aisle",
  "AISLE_LEG_COUNT": 13,
  "AISLE_INCIDENT_COUNT": 13,
  "AISLE_LOW_V_COUNT": 0,
  "AISLE_WARN_COUNT": 10,
  "AISLE_ALERT_COUNT": 3
}
```