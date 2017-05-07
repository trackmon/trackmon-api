# Money Accounts
*This are NOT user accounts! Accounts are used as a money term.*
## Get all accounts from a user
To get all accounts from a user, send a `GET` request with HTTP standard authentication to `/account`.

`GET`
```
/account
```  
### Response
```json
[
  {
    "name": "Cash",
    "amount": 1234.5,
    "currency": "EUR",
  },
  {
    "name": "creditcard",
    "amount": 5432.1,
    "currency": "USD"
  },
  {
    "name": "thebiggestaccountever",
    "amount": 493884.0,
    "currency": "BTC"
  }
]
```
If no authentication is given, the server returns `401 Unauthorized`. If the authentication is wrong, `403 Forbidden` is returned. If all goes well, `200 OK` is returned.

## Add a new account
To add a new account, send a `POST` request with HTTP standard authentication to `/account`.

`POST`
```
/account/:account
```
### Response
If no authentication is given, the server returns `401 Unauthorized`. If the authentication is wrong, `403 Forbidden` is returned. If the account already exists, `400 Bad Request` is returned. If nothing goes wrong, the server returns `201 Created`.

## Get all info about a specific account
To get all info about a specific account, send a `GET` request to `/account/:account`

`GET`
```
/account/:account
```
### Response
```json
[
    {
      "name": "CSGO",
      "id": 4,
      "category": "Entertainment/Games",
      "price": -20.00,
    },
    {
      "name": "Sandwich",
      "id": 3,
      "category": "Food",
      "price": -3.99,
    },
    {
      "name": "Toast",
      "id": 2,
      "category": "Food",
      "price": -2.30,
    },
    {
      "name": "Bank",
      "id": 1,
      "category": "Income",
      "price": 70.00
    }
]
```
