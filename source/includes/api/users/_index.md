# Users

## Get Connected User

> Request `GET /v1/users`

> Response `200 OK`

```json
{
  "name": {
    "familyName": "foo",
    "givenName": "bar"
  },
  "dateOfBirth": {
    "month": "01",
    "year": "1970",
    "day": "01"
  },
  "emailVerified": false,
  "photo": "https://.../default_profile_photo.png",
  "roles": [],
  "createdOn": "2019-07-03T11:07:25.123Z",
  "updatedOn": "2019-07-03T11:07:25.123Z",
  "deletedOn": null,
  "_id": "5d1c8c79b9f87c1e78c990c1",
  "email": "developers@vmgresorts.com",
  "__v": 0
}
```

**Authentication:** Basic

Returns account information for the user currently logged in.
