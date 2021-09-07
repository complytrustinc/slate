# Customers

## Get All Customers

Returns the list of customers.

> Response

```json
{
  "name": "string",
  "email_address": "string",
  "customer_type_id": "string",
  "customer_type": "string",
  "customer_address": "string",
  "identity_providers": "string",
  "customer_phones": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers`

### Request

Has no URL parameters.

## Create Customer

Returns the list of customers.

> Request body must contain the customer as described below:

```json
{
  "name": "string",
  "email_address": "string",
  "customer_type_id": "string",
  "customer_type": "string",
  "customer_address": "string",
  "identity_providers": "string",
  "customer_phones": "string"
}
```

> Response

```json
[
  {
    "name": "string",
    "email_address": "string",
    "customer_type_id": "string",
    "customer_type": "string",
    "customer_address": "string",
    "identity_providers": "string",
    "customer_phones": "string"
  }
]
```

> 201 - registration successful.

### HTTP Request

`POST /v1/customers`

### Request Body Parameters

Its body contains a customer payload:

| Parameter | Required | Description                        |
| --------- | -------- | ---------------------------------- |
| customer  | true     | Json containing FMY customer data. |

## Get customer

Returns a specific customer.

> Response

```json
{
  "name": "string",
  "email_address": "string",
  "customer_type_id": "string",
  "customer_type": "string",
  "customer_address": "string",
  "identity_providers": "string",
  "customer_phones": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |

## Update customer

Returns a specific customer.

> Request body must contain the customer as described below:

```json
{
  "name": "string",
  "email_address": "string",
  "customer_type_id": "string",
  "customer_type": "string",
  "customer_address": "string",
  "identity_providers": "string",
  "customer_phones": "string"
}
```

> Response

```

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}`
`PATCH /v1/customers/{customerid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |

## Delete customer

Deletes a specific customer.

> Response

```

```

> 204 - request successful.

### HTTP Request

`DELETE /v1/customers/{customerid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
