## Send Message

> Request `POST /v1/customerservice/inquiries/:inquiryID/message`

```json
{
  "message": "foobar"
}
```

> Response `204 No Content`

**Authentication:** Role Based

Allows an agent to send a message to the client for the inquiry.

### Request Parameters

| Field   | Required | Type   | Notes                                 |
| ------- | -------- | ------ | ------------------------------------- |
| message | yes      | string | Must be between 0 and 2000 characters |

<aside class="success">
  An email notice will be sent to the client upon success.
</aside>

## View messages

> Request `GET /v1/customerservice/inquiries/:inquiryID/messages`

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

**Authentication:** Role Based

View messages for an inquiry.

Results will be paginated serverside. `results` represents the messages for the current qury. `total` represents the total number of results queryable and `page` represents the page the current `results` are from.
