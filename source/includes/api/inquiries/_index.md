# Inquiries

## Start an inqiury

> Request `POST /v1/inquiries`

```json
{
  "listing": "5d0bd329a790372f488fe7c3",
  "checkIn": "2019-07-10",
  "checkOut": "2019-07-20",
  "adults": 1,
  "children": 0,
  "infants": 0
}
```

> Response `200 OK`

```plaintext
"5d26850959c69d343c398eaa"
```

**Authentication:** Basic

Requests that an inquiry be created for a listing.

### Request Parameters

| Field    | Required | Type   | Notes                                |
| -------- | -------- | ------ | ------------------------------------ |
| listing  | yes      | string | Must be a valid listing ID           |
| checkIn  | yes      | string | Must be YYYY-MM-DD on or after today |
| checkOut | yes      | string | Must be YYYY-MM-DD after checkIn     |
| adults   | yes      | number | Must be >= 1                         |
| children | yes      | number | Must be >= 0                         |
| infants  | yes      | number | Must be >= 0                         |

## View all inquiries

> Request `GET /v1/users/inquiries`

> Response `200 OK`

```json
[
  {
    "adults": 1,
    "children": 0,
    "infants": 0,
    "nightlyPrice": 0,
    "minimumPercentDown": 0,
    "grandTotal": 50,
    "status": "created",
    "createdOn": "2019-07-11T00:30:24.574Z",
    "updatedOn": "2019-07-11T00:30:24.574Z",
    "deletedOn": null,
    "_id": "5d26850959c69d343c398eaa",
    "listing": {
      "_id": "5d0bd329a790372f488fe7c3",
      "name": "Wyndham Waikiki Beach 1 Bedroom",
      "images": [
        {
          "index": 1,
          "createdOn": "2019-06-20T18:40:19.124Z",
          "_id": "5d0bd3e8a790372f488fe7c9",
          "url": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
          "thumbURL": "https://...thumbs/f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
          "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
        }
      ]
    },
    "bookedBy": "5d1c8c79b9f87c1e78c990c1",
    "checkIn": "2019-07-10",
    "checkOut": "2019-07-20",
    "costs": [],
    "payments": [],
    "__v": 0
  }
]
```

**Authentication:** Basic

Requests all of the users inquiries.

## View one inquiry

> Request `GET /v1/users/inquiries/:inquiryID`

> Response `200 OK`

```json
{
  "adults": 1,
  "children": 0,
  "infants": 0,
  "nightlyPrice": 0,
  "minimumPercentDown": 0,
  "grandTotal": 50,
  "status": "created",
  "createdOn": "2019-07-11T00:30:24.574Z",
  "updatedOn": "2019-07-11T00:30:24.574Z",
  "deletedOn": null,
  "_id": "5d26850959c69d343c398eaa",
  "listing": {
    "_id": "5d0bd329a790372f488fe7c3",
    "name": "Wyndham Waikiki Beach 1 Bedroom",
    "images": [
      {
        "index": 1,
        "createdOn": "2019-06-20T18:40:19.124Z",
        "_id": "5d0bd3e8a790372f488fe7c9",
        "url": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
        "thumbURL": "https://...thumbs/f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
        "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
      }
    ]
  },
  "bookedBy": "5d1c8c79b9f87c1e78c990c1",
  "checkIn": "2019-07-10",
  "checkOut": "2019-07-20",
  "costs": [],
  "payments": [],
  "__v": 0
}
```

**Authentication:** Basic

Requests one of the users inquiries.

## Submit inquiry

> Request `POST /v1/users/inquiries/:inquiryID/submit`

```json
{
  "amount": 25.0,
  "token": "tok_visa"
}
```

> Response `200 OK`

```plaintext
https://pay.stripe.com/receipts/(receipt_url)
```

**Authentication:** Email

Submit an inquiry with a tokenized credit card and a payment amount. The inquiry must have the "created" status. The payment must satisfy the rules specified by the listing such as minimum payment and balance remaining.

### Request Parameters

| Field  | Required | Type   | Notes                             |
| ------ | -------- | ------ | --------------------------------- |
| amount | yes      | number | Must be a valid payment amount    |
| token  | yes      | string | Must be a chargeable stripe token |

## Submit inquiry payment

> Request `POST /v1/users/inquiries/:inquiryID/payment`

```json
{
  "amount": 25.0,
  "token": "tok_visa"
}
```

> Response `200 OK`

```plaintext
https://pay.stripe.com/receipts/(receipt_url)
```

**Authentication:** Basic

Submit an additional payment for an inquiry. The inquiry must have the "approved" status. The payment must satisfy the rules specified by the listing such as minimum payment and balance remaining.

### Request Parameters

| Field  | Required | Type   | Notes                             |
| ------ | -------- | ------ | --------------------------------- |
| amount | yes      | number | Must be a valid payment amount    |
| token  | yes      | string | Must be a chargeable stripe token |

## Send inquiry message

> Request `POST /v1/users/inquiries/:inquiryID/message`

```json
{
  "message": "foobar"
}
```

> Response `204 No Content`

**Authentication:** Email

Send a message to customer service regarding the inquiry.

### Request Parameters

| Field   | Required | Type   | Notes                         |
| ------- | -------- | ------ | ----------------------------- |
| message | yes      | string | between 0 and 2000 characters |

<aside class="success">
An email notice will be sent to the customer service inbox.
</aside>

## View inquiry messages

> Request `GET /v1/users/inquiries/:inquiryID/messages`

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
      "_id": "5d268b0284189f16243c8fd1",
      "read": false,
      "createdOn": "2019-07-11T01:03:12.042Z",
      "sentBy": {
        "_id": "5d1c8c79b9f87c1e78c990c1",
        "photo": "https://.../profile_photo.png",
        "name": {
          "familyName": "john",
          "givenName": "doe"
        }
      },
      "message": "this is a test"
    }
  ],
  "total": 1,
  "page": 0
}
```

**Authentication:** Email

View messages for an inquiry. Messages will be paginated serverside. `results` represents the messages for the current qury. `total` represents the total number of results queryable and `page` represents the page the current `results` are from.

### Request Parameters

| Field    | Required | default | Type   | Notes                     |
| -------- | -------- | ------- | ------ | ------------------------- |
| page     | false    | 0       | number | >= 0, used for pagination |
| pageSize | false    | 5       | number | >= 0, used for pagination |
