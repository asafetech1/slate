# AC_AISLE
## GET | AC_AISLES
Returns an array of all the aisles or the aisles that matches the filter param.

> An example of a query body

```json 
{"limit":1, "where": {"AISLE_ID": {"inq": [2,3,8,1]}}, "extract": ["LEGS"]}

```
> The response body

```json
[
  {
    "AISLE_ID": "any",
    "AISLE_NAME": "any",
    "ZONE_ID": "any",
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

`/api/AC_AISLES?filter={query}`

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

## POST | AC_AISLES
Post a new aisle and it returns the new aisle object

### HTTP Request

`/api/AC_AISLES`

> The payload body

```json
{
    "AISLE_NAME": "string",
    "ZONE_ID": "number",
    "CREATED_BY": "string",
    "CREATED_DATE": "DATE(dd,mm,yy hh:mm:ss)",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```
## GET | AC_AISLES/count
Count instances of the model matched by where from the data source (note you don't need to use "where" clause in your query body)

### HTTP Request

`/api/AC_AISLES/count?where={query}`

> An example of a query body

```json 
{"ZONE_ID": 385, "AISLE_ID": 2381}

```

## GET | AC_AISLES/findOne
Returns the latest instance or you can use the filter param to return certain instance

### HTTP Request

`/api/AC_AISLES/findOne?filter={query}`

> An example of a query body

```json 
{"where": {"ZONE_ID": 385}}

```

> response body

```json
{
  "AISLE_ID": 2381,
  "AISLE_NAME": "A1",
  "ZONE_ID": 384,
  "BUILDING_ID": 1
}
```
## PATCH | AC_AISLES/clearAllRackEyes/{id}
Clear all events on the RACKEYE on a giving aisle and clear any notification related to the event.

Parameter | Description
--------- | -----------
id | the id of the aisle subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_AISLES/clearAllRackEyes/{189}`  
> The payload body  

```json
{
    "USER_ID": "number",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```
## PATCH | AC_AISLES/setReSensitivity/{id}
Adjust the warning and alert sensitivity of all the RACKEYE on a giving aisle.

Parameter | Description
--------- | -----------
id | the id of the aisle subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_AISLES/setReSensitivity/{6}`  
> The payload body  

```json
{
    "ALERT_SENSITIVITY": "number",
    "WARNING_SENSITIVITY": "number",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```

# PATCH | AC_AISLES/activateRackeye/{id}
Activate Rackeye in a given aisle.

Parameter | Description
--------- | -----------
id | the id of the aisle subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_AISLES/activateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```
# PATCH | AC_AISLES/deactivateRackeye/{id}
deactivate Rackeye in a given aisle.

Parameter | Description
--------- | -----------
id | the id of the aisle subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_AISLES/deactivateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```