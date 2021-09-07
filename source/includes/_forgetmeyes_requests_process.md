# Process Requests

This collection is in charge of matching found data against all of the query fields.

## Get All Salesforce Object Matches

Retrieve the list of matches found.

> Response

```json
{
  "results": [
    {
      "_id": "string, UUID of object",
      "object_type": "string, Salesforce object type",
      "matched_at": "string, UTC timestamp of match",
      "param_name": ["string, name of query parameter in match"],
      "match_fields": [
        [
          "string, each array corresponds to a match and its elements represent a field that formed part of said match, such as the state, or first name"
        ]
      ]
    }
  ]
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/process`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Perform Query Matching

This method starts the query matching process, it matches the list of records found against the values queried. Each query match and the field where it took place are recorded. This must be executed after the system has been queried, and before generating an ADI.

> Response

```

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/process`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |
