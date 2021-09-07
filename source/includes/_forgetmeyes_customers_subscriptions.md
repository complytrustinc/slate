# Customer subscriptions

## Get All Payments

Get an array of registered payment subscription methods.

> Response

```json
[
  {
    "id": "string, required, UUID of payment subscription method",
    "subscription": "string, payment subscription",
    "status": "string, subscription status",
    "cancel_at": "number",
    "cancel_at_period_end": "bool",
    "collection_method": "string",
    "days_until_due": "number",
    "default_payment_method": "string",
    "off_session": "bool",
    "cancel_at_period_end": "bool",
    "trial_end": "number",
    "subscription_items": [
      {
        "id": "string, UUID of subscription item",
        "email": "string, required",
        "name": "string, required",
        "phone": "string, required",

        "address": {
          "id": "string, required, UUID of billing address",
          "item": "string, required, billing street address",
          "quantity": "number, billing appartment / house number",
          "price": {
            "price": "string",
            "nickname": "string, required",
            "active": "bool, required",
            "currency": "string, required",
            "interval": "string, required",
            "interval_count": "number, required",
            "usage_type": "string, required",
            "type": "string, required",
            "amount": "string, required",
            "product": {
              "id": "string",
              "product": "string",
              "active": "bool, required",
              "name": "string, required"
            }
          }
        }
      }
    ],
    "payment_behavior": "string",
    "customer_id": "string",
    "payment_customer_id": "string"
  }
]
```

### HTTP Request

`GET /v1/customers/{customerid}/subscriptions`

### Request Parameters

The URL contains:

| Parameter  | Description     |
| ---------- | --------------- |
| customerid | customer's UUID |

> 200 - status ok.

## Post Payment

Register a payment subscription method.

> Request body:

```json
{
  "id": "string, required, UUID of payment subscription method",
  "subscription": "string, payment subscription",
  "status": "string, subscription status",
  "cancel_at": "number",
  "cancel_at_period_end": "bool",
  "collection_method": "string",
  "days_until_due": "number",
  "default_payment_method": "string",
  "off_session": "bool",
  "cancel_at_period_end": "bool",
  "trial_end": "number",
  "subscription_items": [
    {
      "id": "string, UUID of subscription item",
      "email": "string, required",
      "name": "string, required",
      "phone": "string, required",
      "address": {
        "id": "string, required, UUID of billing address",
        "item": "string, required, billing street address",
        "quantity": "number, billing appartment / house number",
        "price": {
          "price": "string",
          "nickname": "string, required",
          "active": "bool, required",
          "currency": "string, required",
          "interval": "string, required",
          "interval_count": "number, required",
          "usage_type": "string, required",
          "type": "string, required",
          "amount": "string, required",
          "product": {
            "id": "string",
            "product": "string",
            "active": "bool, required",
            "name": "string, required"
          }
        }
      }
    }
  ],
  "payment_behavior": "string",
  "customer_id": "string",
  "payment_customer_id": "string"
}
```

> Response

```json
{
  "id": "string, required, UUID of payment subscription method",
  "subscription": "string, payment subscription",
  "status": "string, subscription status",
  "cancel_at": "number",
  "cancel_at_period_end": "bool",
  "collection_method": "string",
  "days_until_due": "number",
  "default_payment_method": "string",
  "off_session": "bool",
  "cancel_at_period_end": "bool",
  "trial_end": "number",
  "subscription_items": [
    {
      "id": "string, UUID of subscription item",
      "email": "string, required",
      "name": "string, required",
      "phone": "string, required",
      "address": {
        "id": "string, required, UUID of billing address",
        "item": "string, required, billing street address",
        "quantity": "number, billing appartment / house number",
        "price": {
          "price": "string",
          "nickname": "string, required",
          "active": "bool, required",
          "currency": "string, required",
          "interval": "string, required",
          "interval_count": "number, required",
          "usage_type": "string, required",
          "type": "string, required",
          "amount": "string, required",
          "product": {
            "id": "string",
            "product": "string",
            "active": "bool, required",
            "name": "string, required"
          }
        }
      }
    }
  ],
  "payment_behavior": "string",
  "customer_id": "string",
  "payment_customer_id": "string"
}
```

### HTTP Request

`POST /v1/customers/{customerid}/subscriptions/{subscriptionid}`

### Request Parameters

The URL contains:

| Parameter      | Description         |
| -------------- | ------------------- |
| customerid     | customer's UUID     |
| subscriptionid | subscription's UUID |

> 201 - status created.

## Get Payment

Get a registered payment subscription method by ID.

> Response

```json
{
  "id": "string, required, UUID of payment subscription method",
  "subscription": "string, payment subscription",
  "status": "string, subscription status",
  "cancel_at": "number",
  "cancel_at_period_end": "bool",
  "collection_method": "string",
  "days_until_due": "number",
  "default_payment_method": "string",
  "off_session": "bool",
  "cancel_at_period_end": "bool",
  "trial_end": "number",
  "subscription_items": [
    {
      "id": "string, UUID of subscription item",
      "email": "string, required",
      "name": "string, required",
      "phone": "string, required",
      "address": {
        "id": "string, required, UUID of billing address",
        "item": "string, required, billing street address",
        "quantity": "number, billing appartment / house number",
        "price": {
          "price": "string",
          "nickname": "string, required",
          "active": "bool, required",
          "currency": "string, required",
          "interval": "string, required",
          "interval_count": "number, required",
          "usage_type": "string, required",
          "type": "string, required",
          "amount": "string, required",
          "product": {
            "id": "string",
            "product": "string",
            "active": "bool, required",
            "name": "string, required"
          }
        }
      }
    }
  ],
  "payment_behavior": "string",
  "customer_id": "string",
  "payment_customer_id": "string"
}
```

### HTTP Request

`GET /v1/customers/{customerid}/subscriptions/{subscriptionid}`

### Request Parameters

The URL contains:

| Parameter      | Description         |
| -------------- | ------------------- |
| customerid     | customer's UUID     |
| subscriptionid | subscription's UUID |

> 200 - status ok.

## Put / Patch Payment

Update a payment subscription method.

> Request body:

```json
{
  "id": "string, required, UUID of payment subscription method",
  "subscription": "string, payment subscription",
  "status": "string, subscription status",
  "cancel_at": "number",
  "cancel_at_period_end": "bool",
  "collection_method": "string",
  "days_until_due": "number",
  "default_payment_method": "string",
  "off_session": "bool",
  "cancel_at_period_end": "bool",
  "trial_end": "number",
  "subscription_items": [
    {
      "id": "string, UUID of subscription item",
      "email": "string, required",
      "name": "string, required",
      "phone": "string, required",
      "address": {
        "id": "string, required, UUID of billing address",
        "item": "string, required, billing street address",
        "quantity": "number, billing appartment / house number",
        "price": {
          "price": "string",
          "nickname": "string, required",
          "active": "bool, required",
          "currency": "string, required",
          "interval": "string, required",
          "interval_count": "number, required",
          "usage_type": "string, required",
          "type": "string, required",
          "amount": "string, required",
          "product": {
            "id": "string",
            "product": "string",
            "active": "bool, required",
            "name": "string, required"
          }
        }
      }
    }
  ],
  "payment_behavior": "string",
  "customer_id": "string",
  "payment_customer_id": "string"
}
```

> Response

```

```

> 204 - status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/subscriptions/{subscriptionid}`
`PATCH /v1/customers/{customerid}/subscriptions/{subscriptionid}`

### Request Parameters

The URL contains:

| Parameter      | Description         |
| -------------- | ------------------- |
| customerid     | customer's UUID     |
| subscriptionid | subscription's UUID |

## Delete Payment

Delete a payment subscription method.

> Request body:

```

```

> Response

```

```

> 204 - status no content.

### HTTP Request

`DELETE /v1/customers/{customerid}/subscriptions/{subscriptionid}`

### Request Parameters

The URL contains:

| Parameter      | Description         |
| -------------- | ------------------- |
| customerid     | customer's UUID     |
| subscriptionid | subscription's UUID |
