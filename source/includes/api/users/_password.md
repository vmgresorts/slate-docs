## Update Password

> Request `POST /v1/users/password/update`

```json
{
  "oldPassword": "foobar123",
  "newPassword": "bazqux456"
}
```

> Reponse `204 No Content`

**Authentication:** Basic

Request for the users password to be updated.

### Request Parameters

| Field       | Required | Type   | Notes                             |
| ----------- | -------- | ------ | --------------------------------- |
| oldPassword | yes      | string | Must match existing password      |
| newPassword | yes      | string | Must meet complexity requirements |

<aside class="success">
An email notice will be sent on success.
</aside>

## Reset password (step 1)

> Request `POST /v1/users/password/reset`

```json
{
  "email": "foobar123@gmail.com"
}
```

> Reponse `200 OK`

```plaintext
An email has been sent to reset your password
```

**Authentication:** Public

Request for the users password to be reset, without knowing the old one. A reset password token will be attached to the user account.

### Request Parameters

| Field | Required | Type   | Notes                               |
| ----- | -------- | ------ | ----------------------------------- |
| email | yes      | string | Must match an email in the database |

<aside class="success">
An email confirmation will be sent on success. It contains the verification code that is required to complete the "Reset password (step 2)" method.
</aside>

## Reset password (step 2)

> Request `POST /v1/users/password/reset/:token`

```json
{
  "newPassword": "ff2a43gba"
}
```

> Reponse `200 OK`

```plaintext
Password reset successful
```

**Authentication:** Public

Accepts a reset password token and allows a user to set a new password without knowing the old one.

### Request Parameters

| Field       | Required | Type   | Notes                             |
| ----------- | -------- | ------ | --------------------------------- |
| newPassword | yes      | string | Must meet complexity requirements |

<aside class="success">
An email notice will be sent on completion.
</aside>
