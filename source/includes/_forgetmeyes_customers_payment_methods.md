# Customer payment methods

All Customer payment methods require a customer UUID as part of their

## Get Payment Methods

Get an array of registered payment methods.

> Response

```json
[
  {
    "publishable_key": "string",
    "prices": [
      {
        "id": "string, required, UUID of payment method",
        "payment_method": "string, payment method",
        "type": "string, payment type",
        "setup_intent": "string",
        "default_payment_method": "bool",
        "billing_details": {
          "id": "string, UUID of payment billing details",
          "address": {
            "id": "string, required, UUID of billing address",
            "address_1": "string, required, billing street address",
            "address_2": "string, billing appartment / house number",
            "city": "string, required",
            "country": "string, required",
            "state_province_region": "string, required",
            "zip_postal_code": "string, required"
          },
          "email": "string, required",
          "name": "string, required",
          "phone": "string, required"
        },
        "card": {
          "id": "string, required, UUID of card",
          "brand": "string, required",
          "checks": {},
          "country": "string, required",
          "exp_month": "string, required",
          "exp_year": "string, required",
          "funding": "string, required",
          "last4": "string, required"
        },
        "customer_id": "string",
        "payment_customer_id": "string",
        "networks": {
          "id": "string, UUID of payment method card network",
          "available": ["string, required"],
          "preferred": "string, required"
        },
        "three_d_secure_usage": {
          "id": "string, UUID of three digit secure usage",
          "supported": "bool, required"
        },
        "wallet": {
          "id": "string, UUID of payment wallet",
          "dynamic_last4": "string, required",
          "type": "string, required"
        }
      }
    ]
  }
]
```

### HTTP Request

`GET /v1/customers/{customerid}/payment-methods`

### Request Parameters

The URL contains:

| Parameter  | Description     |
| ---------- | --------------- |
| customerid | customer's UUID |

> 200 - status ok.

## Post Payment Method

Registered a payment method.

> Response

```json
{
  "publishable_key": "string",
  "prices": [
    {
      "id": "string, required, UUID of payment method",
      "payment_method": "string, payment method",
      "type": "string, payment type",
      "setup_intent": "string",
      "default_payment_method": "bool",
      "billing_details": {
        "id": "string, UUID of payment billing details",
        "address": {
          "id": "string, required, UUID of billing address",
          "address_1": "string, required, billing street address",
          "address_2": "string, billing appartment / house number",
          "city": "string, required",
          "country": "string, required",
          "state_province_region": "string, required",
          "zip_postal_code": "string, required"
        },
        "email": "string, required",
        "name": "string, required",
        "phone": "string, required"
      },
      "card": {
        "id": "string, required, UUID of card",
        "brand": "string, required",
        "checks": {},
        "country": "string, required",
        "exp_month": "string, required",
        "exp_year": "string, required",
        "funding": "string, required",
        "last4": "string, required"
      },
      "customer_id": "string",
      "payment_customer_id": "string",
      "networks": {
        "id": "string, UUID of payment method card network",
        "available": ["string, required"],
        "preferred": "string, required"
      },
      "three_d_secure_usage": {
        "id": "string, UUID of three digit secure usage",
        "supported": "bool, required"
      },
      "wallet": {
        "id": "string, UUID of payment wallet",
        "dynamic_last4": "string, required",
        "type": "string, required"
      }
    }
  ]
}
```

> 200 - status ok.

### HTTP Request

`GET /v1/customers/{customerid}/payment-methods`

### Request Parameters

The URL contains:

| Parameter  | Description     |
| ---------- | --------------- |
| customerid | customer's UUID |

## Get Payment Method by Id

Get registered payment method by Id.

> Response

```json
{
  "publishable_key": "string",
  "prices": [
    {
      "id": "string, required, UUID of payment method",
      "payment_method": "string, payment method",
      "type": "string, payment type",
      "setup_intent": "string",
      "default_payment_method": "bool",
      "billing_details": {
        "id": "string, UUID of payment billing details",
        "address": {
          "id": "string, required, UUID of billing address",
          "address_1": "string, required, billing street address",
          "address_2": "string, billing appartment / house number",
          "city": "string, required",
          "country": "string, required",
          "state_province_region": "string, required",
          "zip_postal_code": "string, required"
        },
        "email": "string, required",
        "name": "string, required",
        "phone": "string, required"
      },
      "card": {
        "id": "string, required, UUID of card",
        "brand": "string, required",
        "checks": {},
        "country": "string, required",
        "exp_month": "string, required",
        "exp_year": "string, required",
        "funding": "string, required",
        "last4": "string, required"
      },
      "customer_id": "string",
      "payment_customer_id": "string",
      "networks": {
        "id": "string, UUID of payment method card network",
        "available": ["string, required"],
        "preferred": "string, required"
      },
      "three_d_secure_usage": {
        "id": "string, UUID of three digit secure usage",
        "supported": "bool, required"
      },
      "wallet": {
        "id": "string, UUID of payment wallet",
        "dynamic_last4": "string, required",
        "type": "string, required"
      }
    }
  ]
}
```

### HTTP Request

`GET /v1/customers/{customerid}/payment-methods/{paymentmethodid}`

### Request Parameters

The URL contains:

| Parameter       | Description            |
| --------------- | ---------------------- |
| customerid      | customer's UUID        |
| paymentmethodid | payment methods's UUID |

> 200 - status ok.

## Update Payment Method

Update a payment method.

> Request body:

```json
{
  "publishable_key": "string",
  "prices": [
    {
      "id": "string, required, UUID of payment method",
      "payment_method": "string, payment method",
      "type": "string, payment type",
      "setup_intent": "string",
      "default_payment_method": "bool",
      "billing_details": {
        "id": "string, UUID of payment billing details",
        "address": {
          "id": "string, required, UUID of billing address",
          "address_1": "string, required, billing street address",
          "address_2": "string, billing appartment / house number",
          "city": "string, required",
          "country": "string, required",
          "state_province_region": "string, required",
          "zip_postal_code": "string, required"
        },
        "email": "string, required",
        "name": "string, required",
        "phone": "string, required"
      },
      "card": {
        "id": "string, required, UUID of card",
        "brand": "string, required",
        "checks": {},
        "country": "string, required",
        "exp_month": "string, required",
        "exp_year": "string, required",
        "funding": "string, required",
        "last4": "string, required"
      },
      "customer_id": "string",
      "payment_customer_id": "string",
      "networks": {
        "id": "string, UUID of payment method card network",
        "available": ["string, required"],
        "preferred": "string, required"
      },
      "three_d_secure_usage": {
        "id": "string, UUID of three digit secure usage",
        "supported": "bool, required"
      },
      "wallet": {
        "id": "string, UUID of payment wallet",
        "dynamic_last4": "string, required",
        "type": "string, required"
      }
    }
  ]
}
```

> Response

```json

```

> 204 - status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/payment-methods/{paymentmethodid}`

`PATCH /v1/customers/{customerid}/payment-methods/{paymentmethodid}`

### Request Parameters

The URL contains:

| Parameter       | Description            |
| --------------- | ---------------------- |
| customerid      | customer's UUID        |
| paymentmethodid | payment methods's UUID |

## Delete Payment Method

Delete a payment method.

> Response

```json

```

> 204 - status no content.

### HTTP Request

`DELETE /v1/customers/{customerid}/payment-methods/{paymentmethodid}`

### Request Parameters

The URL contains:

| Parameter       | Description            |
| --------------- | ---------------------- |
| customerid      | customer's UUID        |
| paymentmethodid | payment methods's UUID |
