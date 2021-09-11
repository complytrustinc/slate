# Salesforce Requests

## Get All Salesforce Requests

Returns the list of Salesforce requests.

> Response

```json
[
  {
    "id": "string, request",
    "parent": "string, request",
    "query_schema": "string, request",
    "query_document": "string, request",
    "source_id": "string"
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

## Create Salesforce Request

Create a Salesforce request.

> Request body must contain the customer as described below:

```json
{
  "id": "string, request",
  "parent": "string, request",
  "query_schema": "string, request",
  "query_document": "string, request",
  "source_id": "string"
}
```

> Response

```json
{
  "id": "string, request",
  "parent": "string, request",
  "query_schema": "string, request",
  "query_document": "string, request",
  "source_id": "string"
}
```

> 201 - registration successful.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

### Request Body Parameters

Its body contains a customer payload:

| Parameter          | Description                         |
| ------------------ | ----------------------------------- |
| Salesforce Request | Json containing Salesforce request. |

## Get Salesforce Request

Returns a Salesforce request by Id.

> Response

```json
{
  "id": "string, request",
  "parent": "string, request",
  "query_schema": "string, request",
  "query_document": "string, request",
  "source_id": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/{salesforcerequestid}`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

## Update Salesforce Request

Alter a Salesforce request.

> Request body must contain the customer as described below:

```json
{
  "id": "string, request",
  "parent": "string, request",
  "query_schema": "string, request",
  "query_document": "string, request",
  "source_id": "string"
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/{salesforcerequestid}`

`PATCH /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/{salesforcerequestid}`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |

### Request Body Parameters

Its body contains a customer payload:

| Parameter          | Description                         |
| ------------------ | ----------------------------------- |
| Salesforce Request | Json containing Salesforce request. |

## Delete User

Deletes a specific customer.

> Response

```json

```

> 204 - request successful.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/{salesforcerequestid}`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |
