---
title: WTFPortal Docs

language_tabs: # must be one of https://git.io/vQNgJ

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - contributing/index
  - hosting/index
  - hosting/locally
  - hosting/publically
  - hosting/mysql

search: true
---

# Introduction

Welcome to our API docs!

Most API routes will have request/response examples available. The first section is always the request, and the second is always the response. The request will always be formatted with `Request <HTTP method> <URL>`. Any sections in the url with a colon (`:token`) are url parameters, and any with a question mark (`:token?`) are optional.

If you are unsure what the HTTP status codes mean, refer to [this guide](https://www.restapitutorial.com/httpstatuscodes.html).

<aside class="notice">
  All URL's are expected to be prefixed with one of the following: <br />
  <ul>
    <li>
      <code>https://api.wtfportal.com</code>
    </li>
    <li>
      <code>http://localhost</code>
    </li>
  </ul>
</aside>
