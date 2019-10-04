# PATCH | AC_LEGS/activateRackeye/{QR_CODE}
Activate Rackeye in a given zone.

Parameter | Description
--------- | -----------
QR_CODE | the QR_CODE of the leg subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_LEGS/activateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```
# PATCH | AC_LEGS/deactivateRackeye/{QR_CODE}
deactivate Rackeye in a given zone.

Parameter | Description
--------- | -----------
QR_CODE | the QR_CODE of the leg subjected to the adjustment.

 
### HTTP Request Example
`/api/AC_LEGS/deactivateRackeye/{189}`  
> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```