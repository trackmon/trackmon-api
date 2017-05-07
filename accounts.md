# Money Accounts
*This are NOT user accounts! Accounts are used as a money term.*
## Get all accounts from a user
To get all accounts from a user, send a `GET` request with HTTP standard authentication to `/user/:username`.

`GET`
```
/user/:username
```  
### Response
```json
{
  "accounts": [
    {
      "name": "someaccount1",
      "amount": 1234.5,
      "currency": "EUR"
    },
    {
      "name": "someotheraccount2",
      "amount": 5432.1,
      "currency": "USD"
    },
    {
      "name": "thebiggestaccountever",
      "amount": 493884.0,
      "currency": "BTC"
    }
  ]
}
```
If no authentication is given, the server returns `401 Unauthorized`. If the authentication is wrong or the user is not the same as the given username, `403 Forbidden` is returned. If all goes well, `200 OK` is returned.

## Add a new account
To add a new account, send a `POST` request with HTTP standard authentication to `/user/:username/:account`.

`POST`
```
/user/:username/:account
```
### Response
If no authentication is given, the server returns `401 Unauthorized`. If the authentication is wrong or the user is not the same as the given username, `403 Forbidden` is returned. If the account already exists, `400 Bad Request` is returned. If nothing goes wrong, the server returns `201 Created`.
