# Requests

Manage your FMY Requests

## Get All Users

Returns the list of requests for a given user.

> Response

```json
[
  {
    "id": "string, required",
    "customer": "string",
    "user": "string",
    "type": "string, required",
    "status": "string, required",
    "subject": "string, required",
    "req_type": "string, required",
    "dsar_type": "string, required",
    "location": "string, required",
    "request_id": "number, required",
    "created": "number, required"
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

## Create Request

Create a new request.

> Request body must contain the request data described below:

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "type": "string, required",
  "status": "string, required",
  "subject": "string, required",
  "req_type": "string, required",
  "dsar_type": "string, required",
  "location": "string, required",
  "request_id": "number, required",
  "created": "number, required"
}
```

> Response

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "type": "string, required",
  "status": "string, required",
  "subject": "string, required",
  "req_type": "string, required",
  "dsar_type": "string, required",
  "location": "string, required",
  "request_id": "number, required",
  "created": "number, required"
}
```

> 201 - registration successful.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

### Request Body Parameters

Its body contains a request payload:

| Parameter | Description                   |
| --------- | ----------------------------- |
| request   | Json containing request data. |

## Get Request

Returns a specific request.

> Response

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "type": "string, required",
  "status": "string, required",
  "subject": "string, required",
  "req_type": "string, required",
  "dsar_type": "string, required",
  "location": "string, required",
  "request_id": "number, required",
  "created": "number, required"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description              |
| ---------- | ------------------------ |
| customerid | UUID of customer.        |
| userid     | UUID of user.            |
| requestid  | UUID of a given request. |

## Update Request

Update a specific request.

> Request body must contain the customer as described below:

```json
{
  "id": "string, required",
  "customer": "string",
  "user": "string",
  "type": "string, required",
  "status": "string, required",
  "subject": "string, required",
  "req_type": "string, required",
  "dsar_type": "string, required",
  "location": "string, required",
  "request_id": "number, required",
  "created": "number, required"
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/requests/{requestid}`

`PATCH /v1/customers/{customerid}/users/{userid}/requests/{requestid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description              |
| ---------- | ------------------------ |
| customerid | UUID of customer.        |
| userid     | UUID of user.            |
| requestid  | UUID of a given request. |

### Request Body Parameters

Its body contains a request payload:

| Parameter | Description                   |
| --------- | ----------------------------- |
| request   | Json containing request data. |

## Delete User

Deletes a specific request.

> Response

```json

```

> 204 - request successful.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/requests/{requestid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description              |
| ---------- | ------------------------ |
| customerid | UUID of customer.        |
| userid     | UUID of user.            |
| requestid  | UUID of a given request. |
