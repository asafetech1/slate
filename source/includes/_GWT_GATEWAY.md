# GWT_GATEWAY

## GWT_GATEWAY/requestRegistration

CHECKS IF THERE IS ANY GATEWAY OPEN ON A SITE  
Case true:  
returns a message indicating that there is a gateway already open and status code 403

Case false:  
opens the gateway and return status code 200

### HTTP Request Example
`/api/GWT_GATEWAY/requestRegistration`  

> Payload body  

```json
{
    "GSM_SERIAL_ID": "string",
    "UPDATED_BY": "string",
    "UPDATED_DATE": "DATE(dd,mm,yy hh:mm:ss)"
}
```