# Inquiries (CS)

## Get All Inquiries

> Request `GET /v1/customerservice/inquiries`

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
      "_id": "5d26850959c69d343c398eaa",
      "grandTotal": 50,
      "status": "pending",
      "createdOn": "2019-07-11T00:30:24.574Z",
      "updatedOn": "2019-07-11T00:30:24.574Z",
      "deletedOn": null,
      "listing": {
        "_id": "5d0bd329a790372f488fe7c3",
        "name": "Wyndham Waikiki Beach 1 Bedroom",
        "images": [
          {
            "index": 1,
            "thumbURL": "https://.../thumbs/f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
            "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
          }
        ]
      },
      "bookedBy": {
        "_id": "5d1c8c79b9f87c1e78c990c1",
        "photo": "https://.../default_profile_photo.png",
        "name": {
          "familyName": "John",
          "givenName": "Doe",
          "fullName": "Doe John"
        }
      },
      "checkIn": "2019-07-10",
      "checkOut": "2019-07-20",
      "payments": [
        {
          "deletedOn": null,
          "amount": 25
        }
      ]
    },
    {
      "_id": "5d0be263f05efb3a30d7c314",
      "grandTotal": 50,
      "status": "approved",
      "createdOn": "2019-06-20T19:45:04.224Z",
      "updatedOn": "2019-06-22T09:22:04.961Z",
      "deletedOn": null,
      "listing": {
        "_id": "5d0bd329a790372f488fe7c3",
        "name": "Wyndham Waikiki Beach 1 Bedroom",
        "images": [
          {
            "index": 1,
            "thumbURL": "https://.../thumbs/f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
            "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
          }
        ]
      },
      "bookedBy": {
        "_id": "5d0bd15abddf313cf8973f8e",
        "photo": "https://.../default_profile_photo.png",
        "name": {
          "familyName": "Doe",
          "givenName": "John",
          "fullName": "John Doe"
        }
      },
      "checkIn": "2019-06-20",
      "checkOut": "2019-06-30",
      "payments": [
        {
          "deletedOn": null,
          "amount": 25,
          "refunded": 25
        },
        {
          "deletedOn": null,
          "amount": 20
        }
      ]
    }
  ],
  "total": 2,
  "page": 0
}
```

**Authentication:** Role Based

View all existing inquiries.

Results will be paginated serverside. `results` represents the messages for the current query. `total` represents the total number of results queryable and `page` represents the page the current `results` are from.

<aside class="notice">
  This was designed to function with <a href="https://www.npmjs.com/package/material-table">Material Table</a>. For more details, it would be best to view their docs or ask us directly for some assistance. We have working examples readily available.
</aside>

<aside class="notice">
  The <code>bookedBy.name.fullName</code> field is a field returned only for this query, for the sake of searching and filtering.
</aside>

## Get One Inquiry

> Request `GET /v1/customerservice/inquiries/:inquiryID`

> Response `200 OK`

```json
{
  "adults": 1,
  "children": 0,
  "infants": 0,
  "nightlyPrice": 0,
  "minimumPercentDown": 0,
  "grandTotal": 50,
  "status": "approved",
  "createdOn": "2019-06-20T19:45:04.224Z",
  "updatedOn": "2019-06-22T09:22:04.961Z",
  "deletedOn": null,
  "_id": "5d0be263f05efb3a30d7c314",
  "listing": {
    "_id": "5d0bd329a790372f488fe7c3",
    "name": "Wyndham Waikiki Beach 1 Bedroom",
    "images": [
      {
        "index": 1,
        "url": "https://.../f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
        "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
      }
    ]
  },
  "bookedBy": {
    "name": {
      "familyName": "Doe",
      "givenName": "John"
    },
    "photo": "https://.../default_profile_photo.png",
    "_id": "5d0bd15abddf313cf8973f8e"
  },
  "checkIn": "2019-06-20",
  "checkOut": "2019-06-30",
  "costs": [],
  "payments": [
    {
      "method": "stripe",
      "deletedOn": null,
      "_id": "5d0be288f05efb3a30d7c316",
      "amount": 25,
      "chargeToken": "<TOKEN>",
      "receipt": "https://pay.stripe.com/receipts/(receipt_url)",
      "refunded": 25,
      "refundedBy": {
        "name": {
          "familyName": "Doe",
          "givenName": "John"
        },
        "photo": "https://.../default_profile_photo.png",
        "_id": "5d0bd15abddf313cf8973f8e"
      },
      "refundedOn": "2019-06-20T19:46:36.373Z"
    },
    {
      "method": "manual",
      "deletedOn": null,
      "_id": "5d0df34b25444a18a0d6ca0c",
      "amount": 20,
      "capturedOn": "2019-06-22T09:22:19.220Z",
      "createdBy": {
        "name": {
          "familyName": "Doe",
          "givenName": "John"
        },
        "photo": "https://.../default_profile_photo.png",
        "_id": "5d0bd15abddf313cf8973f8e"
      }
    }
  ],
  "__v": 2
}
```

**Authentication:** Role Based

Returns information for one inquiry. This is intended for viewing an inquiry in the customer service section of the application.

## Set Inquiry Status

> Request `PATCH /v1/customerservice/inquiries/:inquiryID/status`

```json
{
  "status": "approved"
}
```

> Response `204 No Content`

**Authentication:** Role Based

Updates the status of an inquiry to a given value.

### Request Parameters

| Field  | Required | Type   | Notes                                                                                                                  |
| ------ | -------- | ------ | ---------------------------------------------------------------------------------------------------------------------- |
| status | yes      | string | Must be one of: ["created", "pending", "withdrawn", "approved", "denied", "paid", "user_cancelled", "agent_cancelled"] |
