# Shopify Sources

Manage Shopify connectors.

## Get Shopify Source by ID

> Response

```json
{
  "id": "string, required,UUID of store",
  "org_name": "string, required, store name",
  "access_token": "string",
  "scope": "string",
  "expire_in": "number",
  "associated_user_scope": "string",
  "redirect_url": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Create Shopify Source

Register a new Shopify connector.

> Request body must contain the customer as described below:

```json
{
  "store_name": "string",
  "user_source_id": "string, required, parent source UUID to which this connector will be attached"
}
```

> Response

```json
{
  "id": "string, UUID of registered source",
  "store_name": "string",
  "redirect_url": "string, this link redirects to Shopify as the user must register and authorize the application as part of the setup process"
}
```

> 200 - request successful.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Update Shopify Source

Change connector properties. At the moment only allows updating the label.

> Request body must contain the customer as described below:

```json
{
  "store_name": "string"
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify`

`PATCH /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Delete Salesforce Source

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Connect to Shopify Source

> Request body must contain the customer as described below:

```json
{
  "code": "string, required",
  "host": "string, required",
  "state": "string, required, UUID",
  "source_id": "string"
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify/connect`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Verify Salesforce Shopify

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/shopify/verify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |
