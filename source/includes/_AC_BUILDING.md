# AC_BUILDING
## GET | AC_BUILDINGS
Returns an array of all the BUILDINGS or BUILDINGS that matches the filter param.

> An example of a query body

```json 
{"limit":1, "where": {"BUILDING_ID": {"inq": [2,3,8,1]}}}

```
> The response body

```json
[
  {
    "BUILDING_ID": "any",
    "BUILDING_NAME": "any",
    "SITE_ID": "any"
  },
  {
    "BUILDING_ID": "any",
    "BUILDING_NAME": "any",
    "SITE_ID": "any"
  },
  {
    "BUILDING_ID": "any",
    "BUILDING_NAME": "any",
    "SITE_ID": "any"
  }
]
```

### HTTP Request

`/api/AC_BUILDINGS?filter={query}`

### CUSTOM KEYS YOU CAN USE TO QUERY THE DATA
Parameter | Default | Description
--------- | ------- | -----------
IPUI | none | Search for BUILDING by RACKEYE IPUI(used in the where param).
QR_CODE | none | Search for BUILDING by building QR_CODE(used in the where param).
GSM_SERIAL_ID | none | Search for BUILDING by gateway GSM_SERIAL_ID(used in the where param).

### Query Parameters

Parameter | Description
--------- | -----------
limit | limiting the result to certain number(must not exceed 100 requests).
where | 	filter the result by certain condition. syntax: {"where": {"column_name": value}}.
inq [ ]| show result for any values that matches the values in the array . syntax: {"column_name": {"inq": [v1, v2, v3]}}.
neq [ ]| show result for any values that that does not match the values in the array . syntax: {"column_name": {"neq": [v1, v2, v3]}}.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## POST | AC_BUILDINGS
Post a new aisle and it returns the new aisle object

### HTTP Request

`/api/AC_BUILDINGS`

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
## GET | AC_BUILDINGS/count
Count instances of the model matched by where from the data source (note you don't need to use "where" clause in your query body)

### HTTP Request

`/api/AC_BUILDINGS/count?where={query}`

> An example of a query body

```json 
{"ZONE_ID": 385, "AISLE_ID": 2381}

```

## GET | AC_BUILDINGS/findOne
Returns the latest instance or you can use the filter param to return certain instance

### HTTP Request

`/api/AC_BUILDINGS/findOne?filter={query}`

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

## PATCH | AC_BUILDINGS/setReSensitivity/{id}
Adjust the warning and alert sensitivity of all the RACKEYE on a giving AC_BUILDINGS.

Parameter | Description
--------- | -----------
id | the id of the AC_BUILDINGS subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_BUILDINGS/setReSensitivity/{123}`  
> The payload body  

```json
{
    "ALERT_SENSITIVITY": "number",
    "WARNING_SENSITIVITY": "number",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```

# PATCH | AC_BUILDINGS/activateRackeye/{id}
Activate Rackeye in a given zone.

Parameter | Description
--------- | -----------
id | the id of the building subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_BUILDINGS/activateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```
# PATCH | AC_BUILDINGS/deactivateRackeye/{id}
deactivate Rackeye in a given zone.

Parameter | Description
--------- | -----------
id | the id of the building subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_BUILDINGS/deactivateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```