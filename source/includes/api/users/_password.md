## Update Password

> Request `POST /v1/users/password/update`

```json
{
  "oldPassword": "foobar123",
  "newPassword": "bazqux456"
}
```

> Reponse `204 No Content`

Request for the users password to be updated.

### Request Parameters

| Field       | Required | Type   | Notes                        |
| ----------- | -------- | ------ | ---------------------------- |
| oldPassword | yes      | string | Must match existing password |
| newPassword | yes      | string |                              |

<aside class="success">
An email notice will be sent on success.
</aside>
