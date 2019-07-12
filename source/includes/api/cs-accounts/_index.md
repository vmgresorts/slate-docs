# Accounts (CS)

## Get All Users

> Request `GET /v1/customerservice/accounts`

```json
{
  "page": 0,
  "pageSize": 20
}
```

> Response `200 OK`

```json
{
  "results": [
    {
      "_id": "5d1c8c79b9f87c1e78c990c1",
      "emailVerified": true,
      "photo": "https://.../default_profile_photo.png",
      "roles": [],
      "createdOn": "2019-07-03T11:07:25.123Z",
      "updatedOn": "2019-07-03T11:07:25.123Z",
      "deletedOn": null,
      "email": "JohnDoe@gmail.com",
      "name": {
        "familyName": "John",
        "givenName": "Doe",
        "fullName": "Doe John"
      },
      "dateOfBirth": {
        "month": "01",
        "year": "1970",
        "day": "01"
      }
    },
    {
      "_id": "5d0bd15abddf313cf8973f8e",
      "emailVerified": true,
      "photo": "https://.../default_profile_photo.png",
      "roles": [
        {
          "CS": true
        }
      ],
      "createdOn": "2019-06-20T18:32:53.638Z",
      "updatedOn": "2019-06-20T18:32:53.638Z",
      "deletedOn": null,
      "email": "JohnSmith@vmgresorts.com",
      "name": {
        "familyName": "Smith",
        "givenName": "John",
        "fullName": "John Smith"
      }
    }
  ],
  "total": 2,
  "page": 0
}
```

**Authentication:** Role Based

View all registered accounts.

Results will be paginated serverside. `results` represents the messages for the current query. `total` represents the total number of results queryable and `page` represents the page the current `results` are from.

<aside class="notice">
  This was designed to function with <a href="https://www.npmjs.com/package/material-table">Material Table</a>. For more details, it would be best to view their docs or ask us directly for some assistance. We have working examples readily available.
</aside>

<aside class="notice">
  The <code>name.fullName</code> field is a field returned only for this query, for the sake of searching and filtering.
</aside>

## Get One User

> Request `GET /v1/customerservice/accounts/:accountID`

> Response `200 OK`

```json
{
  "name": {
    "familyName": "John",
    "givenName": "Doe"
  },
  "dateOfBirth": {
    "month": "01",
    "year": "1970",
    "day": "01"
  },
  "emailVerified": true,
  "photo": "https://.../default_profile_photo.png",
  "roles": [],
  "createdOn": "2019-07-03T11:07:25.123Z",
  "updatedOn": "2019-07-03T11:07:25.123Z",
  "deletedOn": null,
  "_id": "5d1c8c79b9f87c1e78c990c1",
  "email": "JohnDoe@vmgresorts.com",
  "__v": 0
}
```

**Authentication:** Role Based

Returns account information for one user. This is intended for viewing an account in the customer service section of the application.
