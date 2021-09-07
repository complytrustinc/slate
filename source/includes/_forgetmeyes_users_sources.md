# User Sources

## Get All Sources for User

Retrieves all of a user's sources.

> Response

```json
[
  {
    "id": "string, required",
    "name": "string, required, tag used to describe the source",
    "type": "string, UUID of source type",
    "status": "string, UUID of source status",
    "customer_id": "string",
    "user_id": "string"
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/sources`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |

## Register a New Source

Register a new source for the given user, all new sources must be created with status c1584f01-e2ba-4230-b313-1be7541c1c46. Returns the created source.

TODO Verify this, if this is so, how can the user be expected to know this? Do they need to know this static value or is there an alias or some other way of retrieving it?

> Request body must contain the customer as described below:

```json
{
  "name": "string, required, tag used to describe the source",
  "type": "string, UUID of source type",
  "status": "string, UUID must be c1584f01-e2ba-4230-b313-1be7541c1c46",
  "customer_id": "string",
  "user_id": "string"
}
```

> Response

```json
{
  "id": "string, required",
  "name": "string, required, tag used to describe the source",
  "type": "string, UUID of source type",
  "status": "string, UUID of source status",
  "customer_id": "string",
  "user_id": "string"
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

## Get Source by ID

Retrieve a spefic user's source by ID.

> Response

```json
[
  {
    "id": "string, required",
    "name": "string, required, tag used to describe the source",
    "type": "string, UUID of source type",
    "status": "string, UUID of source status",
    "customer_id": "string",
    "user_id": "string"
  }
]
```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/sources/{sourceid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Update a Source

Update the values of a given source.

> Request body must contain the customer as described below:

```json
{
  "name": "string, required, tag used to describe the source",
  "type": "string, UUID of source type",
  "status": "string, UUID of status",
  "customer_id": "string",
  "user_id": "string"
}
```

> Response

```

```

> 204 - Status no content.

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/sources/{sourceid}`
`PATCH /v1/customers/{customerid}/users/{userid}/sources/{sourceid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |

## Delete Source by ID

Delete a user's source.

> Response

```

```

> 204 - Status no content.

### HTTP Request

`DELETE /v1/customers/{customerid}/users/{userid}/sources/{sourceid}`

### Request Parameters

The URL contains the following parameters :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| sourceid   | UUID of source.   |
