# Readme-test

## API Reference
Take me to [Create Fines](#createFine)
#### <a name="createFine"></a> Create Fine

```http
  POST /api/v1/fines/
```

-  Body
```json
  {
    "userId": 123,
    "bookId": 12,
    "fineType": "broke",
    "amount": 50
   }
```

```json
  Response
  {
    "id": 1,
    "userId": 123,
    "bookId": 12,
    "fineType" "broken",
    "amount": 50
   }
```

