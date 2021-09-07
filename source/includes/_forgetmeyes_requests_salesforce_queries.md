# Query Salesforce

Retrieve or submit a query for a Salesforce connector. All query parameters are optional strings but, it MUST include one of First Name & Lastname, or email, or phone number.

## Get Query results

Retrieve query results.???

TODO Confirm this, seems like this method is just leaking PII data

> Response

```json
{
  "id": "string, UUID of collection",
  "query_result": "string, serialized JSON payload containing findings"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/query`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Create Query

Registers a new Salesforce query.

> Request must contain the query JSON payload:

```json
{
  "customer_id": "string, UUID of customer",
  "user_id": "string, UUID of user",
  "request_id": "string, UUID of request",
  "source_id": "string, UUID of source",
  "query_params": {
    "company_name": "string, optional",
    "first_name": "string, optional",
    "last_name": "string, optional",
    "middle_name": "string, optional",
    "mailing_street": "string, optional",
    "mailing_city": "string, optional",
    "mailing_state_province_region": "string, optional",
    "mailing_zip_postal_code": "string, optional",
    "phone_number": "string, optional",
    "email_address_primary": "string, optional",
    "email_address_secondary": "string, optional",
    "ssn": "string, optional",
    "drivers_license_number": "string, optional",
    "passport_number": "string, optional",
    "alien_registration_number": "string, optional",
    "citizenship": "string, optional",
    "date_of_birth": "string, optional",
    "birth_city": "string, optional",
    "birth_state_province_region": "string, optional",
    "country": "string, optional",
    "mothers_maiden_name": "string, optional",
    "ethnic_affiliation": "string, optional",
    "sexual_orientation": "string, optional",
    "criminal_history": "string, optional",
    "credit_card_number": "string, optional",
    "personal_property_info": "string, optional",
    "medical_account_info": "string, optional",
    "financial_account_number": "string, optional",
    "account_passwords": "string, optional"
  }
}
```

> Response

```

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/query`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |
