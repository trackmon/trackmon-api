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
    "id": 2,
    "name": "Cash",
    "amount": 1234.5,
    "currency": "EUR",
  },
  {
    "id": 1,
    "name": "Credit card",
    "amount": 5432.1,
    "currency": "USD"
  },
  {
    "id": 0,
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
/account
```
```json
{
  "accountname": "thenewaccountname",
  "currency": "EUR",
  "initialamount": 50
}
```

### Response
If no authentication is given, the server returns `401 Unauthorized`. If the authentication is wrong, `403 Forbidden` is returned. If the account already exists, `400 Bad Request` is returned. If nothing goes wrong, the server returns `201 Created`.

`201 Created`
```json
{
  "newaccountid": 2
}
```
## Modify Accounts
You can modify accounts by sending a `PUT` request containing the updated JSON.

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
      "time": "1990-12-31T23:59:60Z"
    },
    {
      "name": "Sandwich",
      "id": 3,
      "category": "Food",
      "price": -3.99,
      "time": "1932-12-31T00:22:21Z"
    },
    {
      "name": "Toast",
      "id": 2,
      "category": "Food",
      "price": -2.30,
      "time": "1937-01-01T12:00:27.87+00:20"
    },
    {
      "name": "Bank",
      "id": 1,
      "category": "Income",
      "price": 70.00,
      "time": "1985-04-12T23:20:50.52Z"
    }
]
```

## Modify history
You can modify history by sending a `PUT` request containing the updated JSON.
