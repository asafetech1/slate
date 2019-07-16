# AC_ORGANISATIONS  
## POST | AC_ORGANISATIONS
Post a new Organisation and it returns the new Organisation object

### HTTP Request

`/api/AC_ORGANISATIONS`

> The payload body

```json
{
  "ORG_ID": "number",
  "COUNTRY_ID": "number",
  "ORG_NAME": "string",
  "CURRENCY_ID": "number",
  "CUSTOMER_ID": "number",
  "LANGUAGE_ID": "number",
  "ORG_LOGO": "buffer",
  "APPLICATION_SKIN_ID": "number",
  "UPDATED_BY": "string",
  "UPDATED_DATE": "date"
}
```

## PATCH | AC_ORGANISATIONS
Update an existing Organisation and it returns the updated Organisation object

### HTTP Request

`/api/AC_ORGANISATIONS`

> The payload body

```json
{
  "ORG_ID": "number",
  "COUNTRY_ID": "number",
  "ORG_NAME": "string",
  "CURRENCY_ID": "number",
  "CUSTOMER_ID": "number",
  "LANGUAGE_ID": "number",
  "APPLICATION_SKIN_ID": "number",
  "UPDATED_BY": "string",
  "UPDATED_DATE": "date"
}
```