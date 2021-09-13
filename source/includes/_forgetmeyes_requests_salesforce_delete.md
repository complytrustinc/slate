# Request Salesforce Deletion

The purpose of this set of API calls is managing the creation of deletion requests. It does not in any way change data at the source, but rather generates a document and zip file with CSVs that empower the actual data holder to perform this deletion.

## Retrieve All Salesforce Object Matches and Delete Statuses

Returns the list of records that matched against the query. It lists each query match and the field where it took place.

> Response

```json
{
  "results": [
    {
      "_id": "string, required, UUID of object",
      "object_type": "string, required",
      "matched_at": "number, required",
      "delete_status": "bool, required",
      "param_name": ["string, parameter being queried"],
      "match_fields": [["string, field(s) matching query parameter"]]
    }
  ]
}
```

> 201 - status created

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/object/retrieve-all`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Get Delete Status by Object ID

Retrieves a record that has been matched against the query. It lists each query match and the field where it took place.

> Response

```json
{
  "results": [
    {
      "_id": "string, required, UUID of object",
      "object_type": "string, required",
      "matched_at": "number, required",
      "delete_status": "bool, required",
      "param_name": ["string, parameter being queried"],
      "match_fields": [["string, field(s) matching query parameter"]]
    }
  ]
}
```

> 201 - status created

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/object/{objectid}`

### Request Parameters

The URL contains :

| Parameter  | Description              |
| ---------- | ------------------------ |
| customerid | UUID of customer.        |
| userid     | UUID of user.            |
| requestid  | UUID of request.         |
| objectid   | UUID of matching object. |

## Put Delete Status for Object

Change the delete status of an object by Id. If a delete status is specified, the object is set to that value. If it is not specified, the object's delete status is toggled.

> Request body can specify future status or be empty:

```json
[
  {
    "delete_status": "bool"
  }
]
```

> Response

```json
{
  "results": [
    {
      "_id": "string, required, UUID of object",
      "object_type": "string, required",
      "matched_at": "number, required",
      "delete_status": "bool, required",
      "param_name": ["string, parameter being queried"],
      "match_fields": [["string, field(s) matching query parameter"]]
    }
  ]
}
```

> 201 - status created

### HTTP Request

`PUT /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/object/{objectid}`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of parent request. |
| objectid   | UUID of object.         |

## Set Delete Status for Multiple Objects or Collection

You can specify the target state for either a set of objects or the entire collection.

You can set the status of a series of objects by listing their UUIDs in the object_id string array. the new status will be applied to all objects listed.

If no objects are present, the status will applied to the entire collection. If true, every object in the collection will be marked for deletion and included in the deletion request. If false, it clears all objects from deletion - Keep in mind that if no object is selected, no request can be submitted as this would result in an empty request.

> Request body must contain the delete_status, and can optinally include a list of UUID values corresponding to the ID of Objects whose delete status will be updated. This is described below:

```json
[
  {
    "delete_status": "bool, sets the delete status",
    "object_id": ["string, optional, UUID of object"]
  }
]
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/object`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Get ADI Params

Retrieves a bundle of causes and legal justifications for requiring this data to be subject to deletion. These are meant to be used for creating the cover letter of the deletion request.

> Response

```json
{
  "CauseOptions": {
    "withdraw_consent": "string",
    "legal_obligation": "string",
    "no_longer_necessary": "string",
    "unlawfully_processed": "string",
    "child_data": "string"
  },
  "JustificationOptions": {
    "freedom": "string",
    "legal_obligation": "string",
    "legal_claims": "string",
    "public_interest": "string"
  }
}
```

> 201 - status created

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/adi/params`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Submit ADI request

When this method is called, three things happen:

1. An ADI document is generated (Acknowledgement of Deletion Intent) listing all objects where PII data has been identified, listing the criteria (query parameter name) and the fields where PII data was found to match. This file is ecnrypted, stored on encrypted storage and accessed via HTTPS.
2. A Zip file is generated. This file contains CSV files which list the ID's of a particular object and are compatible with data loader, but can also be used with other tooling at the discretion of the data holder to speed up their workflow.
3. All selected matches are moved to permanent storage. However, only the field names and matching parameter are preserved everything else is deleted from the system.

> Request body specifies which ADI parameters to include, and can specify custom causes and justifications:

```json
{
  "cause": {
    "withdraw_consent": "bool",
    "legal_obligation_cause": "bool",
    "no_longer_necessary": "bool",
    "unlawfully_processed": "bool",
    "child_data": "bool",
    "custom_cause": "string"
  },
  "justification": {
    "freedom": "bool",
    "legal_obligation_justification": "bool",
    "legal_claims": "bool",
    "public_interest": "bool",
    "custom_justification": "string"
  }
}
```

> Response

```json

```

> 204 - Status no content.

### HTTP Request

`POST /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/submit`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Get List of Files by Request ID

Lists all files related to the request.

> Response

```json
{
  "Files": [
    {
      "FileName": "string, name of file",
      "UploadTag": "string",
      "FileId": "UUID of file"
    }
  ]
}
```

> 201 - status created

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/adi/files`

### Request Parameters

The URL contains :

| Parameter  | Description       |
| ---------- | ----------------- |
| customerid | UUID of customer. |
| userid     | UUID of user.     |
| requestid  | UUID of request.  |

## Get File by ID

Retrieves a file by its UUID.

> Response - Returns the requested file.

```json

```

> 200 - request successful.

### HTTP Request

`GET /v1/customers/{customerid}/users/{userid}/requests/{requestid}/salesforce/delete/adi/files/{fileid}`

### Request Parameters

The URL contains :

| Parameter  | Description             |
| ---------- | ----------------------- |
| customerid | UUID of customer.       |
| userid     | UUID of user.           |
| requestid  | UUID of request.        |
| fileid     | UUID of requested file. |
