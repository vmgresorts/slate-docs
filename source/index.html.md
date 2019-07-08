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
  - api/inquiries/index
  - errors

search: true
---

# Introduction

Welcome to our API docs! You can view code examples in the dark area to the right.

This API documentation was created with [Slate](https://github.com/lord/slate).

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

The first section of a code example will always contain the request's HTTP method and the url it will be sent to. Any sections with a colon (`:token`) are url parameters. If there is a payload expected, it will be directly below this section.

The second section will be the response code followed by a payload (if present).

<aside class="notice">
A 204 response code will never send a payload.
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
