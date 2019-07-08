# Errors

We use the following error codes:

| Code | Description                                      |
| ---- | ------------------------------------------------ |
| 400  | Usually invalid arguments or an invalid state.   |
| 401  | You aren't logged in or lack the required roles. |
| 404  | Something requested can not be found.            |
| 420  | You are being rate limited.                      |
| 500  | Unexpected server error.                         |

<aside class="notice">
The error you receive is somewhat relative to the action you're trying to perform. For example, a 404 might represent an incorrect route or simply a correct route that can't find a resource you're asking it to locate (like a userid that doesn't exist).
</aside>
