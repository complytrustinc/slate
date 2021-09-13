# User Queries

## Get All User Queries

Returns the list of user queries.

> Response

```json
[
  {
    "id": "string",
    "name": "string",
    "example_payload": "string",
    "query_schema": "string",
    "user_id": "string"
  }
]
```

> 200 - request successful.

### HTTP Request

`/v1/customers/{customerid}/users/{userid}/queries`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

## Create User Query

Creates a new customer query.

> Request body must contain the customer as described below:

```json
{
  "id": "string",
  "name": "string",
  "example_payload": "string",
  "query_schema": "string",
  "user_id": "string"
}
```

> Response

```json
{
  "id": "string",
  "name": "string",
  "example_payload": "string",
  "query_schema": "string",
  "user_id": "string"
}
```

> 201 - successfully created.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/queries`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

### Request Body Parameters

Its body contains a user query payload:

| Parameter | Description                      |
| --------- | -------------------------------- |
| query     | Json containing user query data. |

## Get User Query

Returns a user query.

> Response

```json
{
  "id": "string",
  "name": "string",
  "example_payload": "string",
  "query_schema": "string",
  "user_id": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/queries/{queryid}`

### Request Parameters

The URL contains :

| Parameter  | Description         |
| ---------- | ------------------- |
| customerid | UUID of customer.   |
| userid     | UUID of user.       |
| queryid    | UUID of user query. |

## Update User Query

Updates a customer query.

> Request body must contain the customer as described below:

```json
{
  "id": "string",
  "name": "string",
  "example_payload": "string",
  "query_schema": "string",
  "user_id": "string"
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/queries/{queryid}`

`PATCH /v1/customers/{customerid}/users/{userid}/queries/{queryid}`

### Request Parameters

The URL contains :

| Parameter  | Description         |
| ---------- | ------------------- |
| customerid | UUID of customer.   |
| userid     | UUID of user.       |
| queryid    | UUID of user query. |

### Request Body Parameters

Its body contains a user query payload:

| Parameter | Description                      |
| --------- | -------------------------------- |
| query     | Json containing user query data. |

## Delete User Query

Deletes a specific customer query.

> Response

```json

```

> 204 - request successful.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/queries/{queryid}`

### Request Parameters

The URL contains :

| Parameter  | Description         |
| ---------- | ------------------- |
| customerid | UUID of customer.   |
| userid     | UUID of user.       |
| queryid    | UUID of user query. |
