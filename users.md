# Users
## Add a new user
To add a new user, send a POST request to `/signup` with the username and the plaintext password in HTTP standard authentication. It is strongly recommended to use HTTPS for this, otherwise your password will be leaked.

`POST`
```
/signup
```
### Response
If the user does not exist, the server responds with `201 Created` and creates the user. If the user does exist, the server responds with `403 Forbidden`. In case that the request doesn't provide any authentication, the response is `401 Unauthorized`.

## Remove a user
To remove a user, send a DELETE request to `/signup/:username` with HTTP standard authentication.

`DELETE`
```
/signup/:username
```

### Response
In case the user exists, the user is the same as the requesting user, and the authentication is correct, the user gets deleted and the server returns a `200 OK`.
When no authentication is given, the server returns `401 Unauthorized`. When the requesting user and the given user aren't the same, the server returns `403 Forbidden`.
