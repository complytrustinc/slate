# Payments

## Get Payment

Returns payment configuration.

`GET /v1/payments/config`

> Response

```json
{
  "publishable_key": "string",
  "prices": [
    {
      "id": "string, required, UUID of price",
      "nickname": "string, price name",
      "amount": "number, price amount",
      "from": "number, price start date",
      "through": "number, price end date",
      "details": ["string, additional information"]
    }
  ]
}
```

> 200 - status ok.

## Setup Payment

Configures payment.

`POST /v1/payments/setup`

```json
{
  "confirm": "string, required",
  "customer_id": "string, UUID of customer",
  "payment_method_id": "string, UUID of payment method",
  "usage": "string, required"
}
```

> Response

```json
{
  "id": "string",
  "client_secret": "string, UUID of client"
}
```

> 200 - status ok.
