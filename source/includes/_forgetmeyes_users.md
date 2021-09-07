# Users

## Get All Users

Returns the list of users.

> Response

```json
[
  {
    "firstname": "string",
    "lastname": "string",
    "username": "string",
    "password": "string",
    "aws_user": {
      "access_key": "string",
      "secret_access": "string",
      "cmk_id": "string",
      "region": "string",
      "private_key": "string",
      "public_key": "string",
      "user_arn": "string",
      "user_id": "string, Foreign key to User (Belongs To)"
    },
    "customer_phones": [
      {
        "PhoneNumber": "string",
        "PhoneTypeID": "string, Foreign key to PhoneType (Belongs To)",
        "PhoneType": {
          "Name": "string",
          "Description": "string"
        },
        "UserID": "string, Foreign key to User (Has Many)"
      }
    ],
    "customer_id": "string, Foreign key to Customer (Has Many)",
    "identity_provider_id": "string, Foreign key to IdentityProvider (Belongs To)",
    "identity_provider": {
      "name": "string",
      "url": "string",
      "response_type": "string",
      "app_client": "string",
      "app_client_secret": "string",
      "redirect_url": "string",
      "key_url": "string",
      "customer_id": "string, Foreign key to Customer (Has Many)"
    }
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |

## Create User

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

`POST /v1/customers/{customerid}/users`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |

### Request Body Parameters

Its body contains a customer payload:

| Parameter | Description                        |
| --------- | ---------------------------------- |
| customer  | Json containing FMY customer data. |

## Get User

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

`GET /v1/customers/{customerid}/users/{userid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

## Update User

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

`PUT /v1/customers/{customerid}/users/{userid}`
`PATCH /v1/customers/{customerid}/users/{userid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

### Request Body Parameters

Its body contains a customer payload:

| Parameter | Description                        |
| --------- | ---------------------------------- |
| customer  | Json containing FMY customer data. |

## Delete User

Deletes a specific customer.

> Response

```

```

> 204 - request successful.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
