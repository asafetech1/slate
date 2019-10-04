# AC_INSPECTION

## POST | AC_INSPECTION/assign
Assigns user to an existing inspection and creates a new inspection in case when there is no one.

### HTTP Request

`/api/AC_INSPECTION/assign`

> The payload body

```json
{
    "LEG_QR_CODE": "string",
    "USER_ID": "number",
    "HAS_DAMAGE": "boolean",
    "INSPECTION_TYPE_ID": "number",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```  

## PATCH | AC_INSPECTION/awaitResolution
Set inspection status to awaiting resolution.  

### HTTP Request

`/api/AC_INSPECTION/awaitResolution`

> The payload body

```json
{
    "INSPECTION_ID": "number",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```  
## GET | AC_INSPECTION/cleanInspection
it cleans the inspection if the inspection been interrupted(you don't have to call this as it runs automatically before submitting inspection).  

### HTTP Request

`/api/AC_INSPECTION/cleanInspection?QR_CODE=qrCode here`

## PATCH | AC_INSPECTION/complete
Marks an inspection as complete and deletes the corresponding notification.

### HTTP Request

`/api/AC_INSPECTION/complete`

> The payload body

```json
{
    "INSPECTION_ID": "number",
    "QR_CODE": "string",
    "COMPLETED_DATE": "DATE(dd,mm,yy hh:mm:ss)",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```  
## PATCH | AC_INSPECTION/completeWithNoDamage
Called when there is no damage to the leg.
Marks an inspection as complete and set the HAS_DAMAGE to false, or create an inspection if there no one and then completes it. 
It also deletes the corresponding notification if there is one.

### HTTP Request

`/api/AC_INSPECTION/completeWithNoDamage`

> The payload body

```json
{
    "USER_ID": "number",
    "QR_CODE": "string",
    "COMPLETED_DATE": "DATE(dd,mm,yy hh:mm:ss)",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```  
## GET | AC_INSPECTION/inspectionHistory
Return the historical data of an inspection that has been completed. 
### HTTP Request

`/api/AC_INSPECTION/inspectionHistory?INSPECTION_ID=inspectionId here`


## GET | AC_INSPECTION/inspectionSummary
Return the data of an outstanding inspection that is marked as waiting resolution
### HTTP Request

`/api/AC_INSPECTION/inspectionSummary?QR_CODE=qe_code here`
## PATCH | AC_INSPECTION/reset
reset inspection status to pending and user_id to null.

> The payload body

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "date",
    "INSPECTION_ID": "number"
}
``` 

## PATCH | AC_INSPECTION/supercede
supercede an inspection and sets completed_date.

> The payload body  

```json
{
    "UPDATED_BY": "string",
    "UPDATED_DATE": "date",
    "INSPECTION_ID": "number"
}
```

## POST | AC_INSPECTIONS/submitInspection
Submit the inspection and return an object of risk outcome and media payload array.

If the media payload array empty:   
    You can skip calling AC_INSPECTIONS/submitInspectionMedia   
else:    
    Before passing the media payload array to AC_INSPECTIONS/submitInspectionMedia you   
    need to map over the array and replace the image name with the image buffer.

> Payload body  

```json
{
    "json": [],
    "USERNAME": "string",
    "QR_CODE": "string",
    "DATE": "date string"
}
```

> Response body  

```json
{
  "MEDIA": [
    {
      "INSPECTION_RESPONSE_ID": "number",
      "INSPECTION_MEDIA": "Image name",
      "CREATED_BY": "string",
      "CREATED_DATE": "date string",
      "UPDATED_BY": "string",
      "UPDATED_DATE": "date string"
    }
  ],
  "RISK": {
    "OUTCOME": "MAINTENANCE REQUIRED | MINOR DAMAGE | NO DAMAGE",
    "INSPECTION_RISK_LEVEL_ID": "number"
  }
}
```

## POST | AC_INSPECTIONS/submitInspectionMedia
Submit the inspection media and returns "successful" string and 200 statusCode.

> Payload body  

```json
[
    {
      "INSPECTION_RESPONSE_ID": "number",
      "INSPECTION_MEDIA": "buffer",
      "CREATED_BY": "string",
      "CREATED_DATE": "date string",
      "UPDATED_BY": "string",
      "UPDATED_DATE": "date string"
    }
]
```

> Response body  
```json
"successful"
```