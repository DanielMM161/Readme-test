# Resume
 - Create Fines [Create Fines](#Patch Fines)
 - Delete Fines [Delete Fines](#deleteFine)

# Fines

# Create Fine

**[POST]** You can create a new fines sending a object like the following /fines/

**[URL]** https://api.libary.management/api/v1/fines/

### Header

- Authorization: “Bearer {token_librarian_access}”

### Body

```json
{
  "userId": 123,
  "bookId": 12,
  "fineType": "broke",
  "amount": 50
}
```

### Response

```json
{
"id": 1,
"userId": 123,
"bookId": 12,
"fineType" "broken",
"amount": 50
}
```

# Patch Fines

**[PATCH]** The fines endpoint allows changing state of one fine

**[URL]** https://api.libary.management/api/v1/fines/{id}

### Parameter

- **ID (Required):** Unique identifier for a fines

### Header

- Authorization: “Bearer {token_librarian_access}”

### Body

```json
{
	"fineType": "burnt",
	"amount": 100,
}
```

### Response

```json
{
	"id": 1,
	"userId": 123,
	"bookId": 12,
	"fineType" "burnt",
	"amount": 100
}
```

# Delete Fines

**[DELETE]** The fines endpoint allows to delete fines

**[URL]** https://api.libary.management/api/v1/fines/{id}

### Header

- **Authorization**: “Bearer {token_librarian_access}”

### Parameter

- **IDs (Required):** Unique identifier for a fines

### Response

```json
{
	"status_process": true
}
```
