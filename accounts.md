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
