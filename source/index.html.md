---
title: VMGResorts Docs

language_tabs: # must be one of https://git.io/vQNgJ

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - api/auth
  - api/users/index
  - api/users/email
  - api/users/password
  - api/listings/index
  - api/inquiries/index
  - api/google/maps
  - api/cs-accounts/index
  - api/cs-inquiries/index
  - api/cs-inquiries/messages
  - api/cs-inquiries/payments
  - errors

search: true
---

# Introduction

Welcome to our API docs!

## Request/Response example

> Request `GET /imaginary/route/:token`

```json
{
  "some": "payload"
}
```

> Response `200 OK`

```json
{
  "_id": "5d1c8c79b9f87c1e78c990c1"
}
```

Each code example will have two sections, each section optionally followed by a sample payload. The first section is the request and the second is the response. The request will always be formatted as `Request <HTTP method> <URL>`. Any sections in the url with a colon (`:token`) are url parameters.

<aside class="notice">
A 204 response code will never send a payload.
</aside>

<aside class="notice">
  All URL's are expected to be prefixed with one of the following: <br />
  <ul>
    <li>
    <code>https://api.dev.vmgresorts.com</code>
  </li>
    <li>
      <code>https://api.vmgresorts.com</code>
    </li>
  </ul>
</aside>

## Authenticated Routes

> Request `GET /imaginary/secret/route`

> Response `401 Unauthorized`

```html
<div style="display: block">
  <div style="text-align: center; margin-top: 5%">
    <h1>These aren't the routes you're looking for</h1>
    <img
      src="https://lumiere-a.akamaihd.net/v1/images/databank_jedimindtrick_01_169_a491266d.jpeg?region=0%2C0%2C1560%2C878&width=960"
    />
  </div>
</div>
```

Some routes require varying levels of authentication.

- **Public** - These routes are always available.
- **Basic** - These routes require that you are logged in to an account, even an unverified one.
- **Email** - These routes require that you are logged in to an account with a verified email address.
- **Role Based** - These routes require that you are logged in to an account that has the specified customer service roles enabled.

<aside class="notice">
Customer service roles can not be enabled via any public API routes. If you need a customer service account, please contact us.
</aside>
