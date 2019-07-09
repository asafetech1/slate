# RET_RACKEYE  

## GET | RET_RACKEYE/getReSensitivity
Get rackeye warning and alert sensitivity.

Parameter | Description
--------- | -----------
IPUI | (string) the IPUI for the requested rackeye.

### HTTP Request Example
`/api/RET_RACKEYE/getReSensitivityIPUI='IPUI HERE'`  

> Response body  

```json
{
  "ALERT_SENSITIVITY": 50,
  "WARNING_SENSITIVITY": 10
}
```
## POST | RET_RACKEYE/manageAssetEvent
THIS ENDPOINT BEHAVES DIFFERENTLY DEPENDING ON EACH CASE BELOW:  
  
Case Low Battery  
1-it creates a new notification
2-add a record to leg history

Case Battery Replaced  
1-remove the related notification
2-add a record to leg history

Case Warning  
1-creates an inspection if there is no one  
2-it creates a new notification
3-add a record to leg history

Case Alert  
1-creates an inspection if there is no one 2-it creates a new notification
3-add a record to leg history

Case Offline  
1-it creates a new notification
2-add a record to leg history

Case Online  
1-remove the related notification
2-add a record to leg history

### HTTP Request Example
`/api/RET_RACKEYE/manageAssetEvent`  

> Response body  

```json
{
"IPUI": "string",
"CREATED_BY": "string",
"CREATED_DATE": "date",
"UPDATED_BY": "string",
"UPDATED_DATE":"date",
"ASSET_EVENT_NOTIF_TYPE_ID": "number",
"AS_EVT_NOTIF_TYPE_CAUSE_ID":"number"
}
```
## GET | RET_RACKEYE/resetInspection
Set rackeye event status to no event.


### HTTP Request Example
`/api/RET_RACKEYE/resetInspection`  

> Payload body  

```json
{
    "QR_CODE": "string",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```