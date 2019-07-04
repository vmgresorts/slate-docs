# Authentication

## Register User

> Request `POST /auth/register`

```json
{
  "familyName": "foo",
  "givenName": "bar",
  "email": "developers@vmgresorts.com",
  "password": "password",
  "dob": "1970-01-01"
}
```

> Response `204 No Content`

Registers a user account for local authentication.

### Request Parameters

| Field      | Required | Type   | Notes                   |
| ---------- | -------- | ------ | ----------------------- |
| email      | yes      | string |                         |
| password   | yes      | string | Must be >= 6 chars      |
| dob        | yes      | string | Must be >= 18 years old |
| familyName | yes      | string |                         |
| givenName  | yes      | string |                         |

## Local Authentication

> Request `POST /auth/login`

```json
{
  "email": "developers@vmgresorts.com",
  "password": "password"
}
```

> Response `200 OK`

```plaintext
00100010 01010100 01101000 01100101 00100000 01100011 01101111 01101101 01110000 01101100 01100101 01111000 01101001 01110100 01111001 00100000 01101111 01100110 00100000 01111001 01101111 01110101 01110010 00100000 01110001 01110101 01100101 01110011 01110100 01101001 01101111 01101110 00100000 01101001 01110011 00100000 01101100 01101001 01101110 01100101 01100001 01110010 00100000 01110100 01101111 00100000 01110100 01101000 01100101 00100000 01110111 01101111 01110010 01100100 01110011 00100000 01111001 01101111 01110101 00100000 01110101 01110011 01100101 01100100 00101110 00100010 00100000 00101101 00100000 01110100 01100101 01100011 01101000 01101100 01100101 01100001 01100100
```

Log in to a user account registered for local authentication.

### Request Parameters

| Field    | Required | Type   |
| -------- | -------- | ------ |
| email    | Yes      | String |
| password | Yes      | String |