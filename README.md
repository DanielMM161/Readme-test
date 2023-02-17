# Readme-test

# Resume
 - Create Fines [Create Fines](#createFine)
 - Delete Fines [Delete Fines](#deleteFine)

# FINES
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

#### <a name="deleteFine"></a> Delete Fine


