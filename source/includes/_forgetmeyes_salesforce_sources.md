# Salesforce Sources

Manage Salesforce connectors.

## Get Salesforce Source by ID

TODO Review if the Access token & refresh token should be made publicly available.

> Response

```json
{
  "id": "string, required, UUID of source",
  "domain_name": "string, org domain name",
  "access_token": "string",
  "refresh_token": "string",
  "signature": "string",
  "scope": "string",
  "instance_url": "string",
  "token_type": "string",
  "issued_at": "number",
  "expires_in": "number",
  "redirect_url": "string"
}
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Create Salesforce Source

Register a new Salesforce connector

> Request body must contain the customer as described below:

```json
{
  "domain_name": "string",
  "source_id": "string, required, parent source UUID to which this connector will be attached"
}
```

> Response

```json
{
  "id": "string, UUID of registered source",
  "domain_name": "string",
  "redirect_url": "string, this link redirects to salesforce as the user must register and authorize the application as part of the setup process"
}
```

> 201 - successfully created.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Update Salesforce Source

Change connector properties. At the moment only allows updating the label.

> Request body must contain the customer as described below:

TODO review if the source ID should be available before registering?

```json
{
  "domain_name": "string"
}
```

> Response

```

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce`
`PATCH /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Delete Salesforce Source

> Response

```

```

> 204 - Status no content.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Connect to Salesforce Source

> Request body must contain the customer as described below:

```json
{
	"code":"string, required",
	"state":"string, required, UUID",
	"source_id"
}
```

> Response

```

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce/query`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Refresh Salesforce Source

> Response

```json
{
  "bearer_token": "string",
  "sosl_url": "string",
  "soql_url": "string",
  "sobjects_url": "string"
}
```

> 200 - status ok.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce/refresh`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Verify Salesforce Source

> Response

```

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce/verify`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Query Salesforce Source

> Response

```json
{
  "bearer_token": "string",
  "sosl_url": "string",
  "soql_url": "string",
  "sobjects_url": "string"
}
```

> 200 - status ok.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/sources/{sourceid}/salesforce/query`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |
