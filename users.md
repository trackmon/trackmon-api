# Users
## Add a new user
To add a new user, send a POST or GET request to `/signup` with the username and the plaintext password in HTTP standard authentication. It is strongly recommended to use HTTPS for this, otherwise your password will be leaked.

`GET/POST /signup`

### Response
If the user does not exist, the server responds with `201 Created` and creates the user. If the user does exist, the server responds with `403 Forbidden`. In case that the request doesn't provide any authentication, the response is `401 Unauthorized`.
