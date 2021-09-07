# Authentication

## Email

Validate a user's email address.

> Request body must contain the email address associated with the account as described below:

```json
{
  "email_address": "required, string"
}
```

> Response
> 200 - email is registered, empty response.

### HTTP Request

`POST /v1/auth/customers/email`

### Request

Its body contains the following:

| Parameter     | Required | Description                            |
| ------------- | -------- | -------------------------------------- |
| email_address | true     | Email address associated with account. |

## Signup

Register for a new account. FMY distinguishes between users and a customers. An account will have one customer, but can have multiple users.

> Request body:

```json
{
  "customer": {
    "id": "string",
    "name": "string, required",
    "email_address": "string, required",
    "customer_type": "string, required",
    "address": {
      "id": "string",
      "country": "string, required",
      "address_1": "string, required",
      "address_2": "string",
      "city": "string, required",
      "state_province_region": "string, required",
      "zip_postal_code": "string, required"
    },
    "phones": [
      {
        "id": "string",
        "phone_number": "string, required",
        "phone_type": "string, required, UUID"
      }
    ]
  },
  "user": {
    "id": "string",
    "first_name": "string, required",
    "last_name": "string, required",
    "user_name": "string, required, email",
    "phones": [
      {
        "id": "string",
        "phone_number": "string, required",
        "phone_type": "string, required, UUID"
      }
    ],
    "aws_user": {
      "id": "string",
      "access_key": "string",
      "secret_access": "string",
      "cmk_id": "string",
      "region": "string",
      "private_key": "string",
      "public_key": "string",
      "user_arn": "string"
    }
  }
}
```

> Response

```json
{
  "customer_id": "string"
}
```

> 200 - registration successful.

### HTTP Request

`POST /v1/auth/signup`

### Request

Its body contains the following:

| Parameter | Required | Description   |
| --------- | -------- | ------------- |
| customer  | true     | FMY customer. |
| user      | true     | FMY user.     |

## Start Login

> 200 - successful.

```json
{
  "idp_url": "string, required",
  "has_idp": "boolean"
}
```

idp_url

First step in authorization process. Followed by a call to Login for e-mail based authentication, or a redirect to authorizing via a given SAML provider.

### HTTP Request

`POST /v1/auth/startlogin`

## Login

Email based login. Start login must be perfomed before this call.

> Request body:

````json
{
  "code": "string, required",
  "state": "string, required"

}```

> Response

```json
{
  "access_token": "string, required",
  "refresh_token": "string, required",
  "access_key": "string, required",
  "customer_id": "string, required",
  "user_id": "string, required"
}
````

> 200 - login successful.

### HTTP Request

`POST /v1/auth/login`

### Request Body

Its body contains the following:

| Parameter | Required | Description   |
| --------- | -------- | ------------- |
| code      | true     | FMY customer. |
| state     | true     | FMY user.     |

## Logout

Close your FMY session.

> Request will use the cookie stored on the browser, no need for a payload.

```

```

> Response

```json
{
  "logout_url": "string"
}
```

> 200 - logout successful.

### HTTP Request

`POST /v1/auth/logout`

## Refresh

Refresh auth token.

> Request will use the cookie stored on the browser, no need for a payload.

```

```

> Response

```json
{
  "access_token": "string, required",
  "refresh_token": "string, required",
  "access_key": "string, required",
  "customer_id": "string, required",
  "user_id": "string, required"
}
```

> 200 - refresh successful.

### HTTP Request

`POST /v1/auth/refresh`
