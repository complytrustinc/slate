# Requeries

Run or lookup a re-query

## Get All Requeries

Returns a JSON array with the list of requeries for a given request. Each re-query is really an independent query, so for a given requery, the request JSON payload may contain nested request JSON objects for child requeries.

> Response

```json
[
  {
    "id": "string, required",
    "customer": "string",
    "user": "string",
    "subject": "string",
    "type": "string",
    "status": "string",
    "request_number": "string",
    "created": "number",
    "salesforce_requests": [
      {
        "id": "string",
        "query_schema": "string",
        "query_document": "string",
        "source_id": "string",
        "created": "number",
        "salesforce_query": {
          "id": "string",
          "query_result": "string",
          "created": "number"
        }
      }
    ],
    "requeries": ["request object"]
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/requeries`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

## Create Requery

Create a new requery, the contents of the query will be taken from the parent whose ID was provided.

> Response

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "subject": "string",
  "type": "string",
  "status": "string",
  "request_number": "string",
  "created": "number",
  "salesforce_requests": [
    {
      "id": "string",
      "query_schema": "string",
      "query_document": "string",
      "source_id": "string",
      "created": "number",
      "salesforce_query": {
        "id": "string",
        "query_result": "string",
        "created": "number"
      }
    }
  ],
  "requeries": ["will be blank, since this has just been created"]
}
```

> 201 - registration successful.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/requeries`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

## Get Requery

Returns a specific request.

> Response

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "subject": "string",
  "type": "string",
  "status": "string",
  "request_number": "string",
  "created": "number",
  "salesforce_requests": [
    {
      "id": "string",
      "query_schema": "string",
      "query_document": "string",
      "source_id": "string",
      "created": "number",
      "salesforce_query": {
        "id": "string",
        "query_result": "string",
        "created": "number"
      }
    }
  ],
  "requeries": ["will be blank, since this has just been created"]
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/requeries/{requeryid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description              |
| ---------- | ------------------------ |
| customerid | UUID of customer.        |
| userid     | UUID of user.            |
| requestid  | UUID of parent request.  |
| requeryid  | UUID of a given requery. |
