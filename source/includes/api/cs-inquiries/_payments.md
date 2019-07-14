# Inquiry Payments (CS)

## Create Payment

> Request `POST /v1/customerservice/inquiries/:inquiryID/payment`

```json
{
  "amount": 15.0
}
```

> Response `204 No Content`

**Authentication:** Role Based

Manually create a payment for an inquiry. The payment will be created as already captured.

### Request Parameters

| Field  | Required | Type   | Notes                            |
| ------ | -------- | ------ | -------------------------------- |
| status | yes      | number | must be <= the remaining balance |

## Delete Payment

> Request `DELETE /v1/customerservice/inquiries/:inquiryID/payment/:paymentID`

> Response `204 No Content`

**Authentication:** Role Based

Delete a manually created payment. The payment must not be user created.

## Restore Payment

> Request `PATCH /v1/customerservice/inquiries/:inquiryID/payment/:paymentID/restore`

> Response `204 No Content`

**Authentication:** Role Based

Restore a deleted, manually created payment

## Capture Payment

> Request `PATCH /v1/customerservice/inquiries/:inquiryID/payment/:paymentID/capture`

> Response `204 No Content`

Mark an uncaptured payment as captured. The payment must not be deleted.

## Refund Payment

> Request `PATCH /v1/customerservice/inquiries/:inquiryID/payment/:paymentID/refund`

```json
{
  "amount": 15.0
}
```

> Response `204 No Content`

Refund a user submitted payment. The payment must not be refunded or deleted.

### Request Parameters

| Field  | Required | Type   | Notes                      |
| ------ | -------- | ------ | -------------------------- |
| status | yes      | number | must be <= the amount paid |
