# Library System Endpoints

# Fines

# Get All Fines

**[GET]** The F******ines****** endpoint return **Fines** listed, allowing queries bases on **********Fines********** purpose

**[URL]** https://api.libary.management/api/v1/fines

### Header

- **Authorization**: Bearer {api_key_librarian}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Parameter

| Parameter | Type | Description |
| --- | --- | --- |
| user_id | Number | Id of the user |
| book_id | Number | Id of the book |
| fine_type | String | Type of the fines “burnt” | “broken” |
| fine_amount | Number | Amount of the fine |

### Response

```json
[
	{
		"id": 6,
		"userId": 25,
		"bookId": 30,
		"fineType" "broken",
		"amount": 50
	},
	{
		"id": 7,
		"userId": 15,
		"bookId": 20,
		"fineType" "burnt",
		"amount": 100
	}
]
```

# Get One Fine

**[GET]** The F******ines****** endpoint return one ********Fine********, allowing queries bases on **********Fines********** purpose

**[URL]** https://api.libary.management/api/v1/fines/{id}

### Header

- **Authorization**: Bearer {api_key_librarian}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Parameter

| Parameter | Type | Description | Required |
| --- | --- | --- | --- |
| id | Number | Indentifier of Fine | Yes |

### Response

```json
{
	"id": 5,
	"userId": 10,
	"bookId": 15,
	"fineType" "broken",
	"amount": 30
}
```

# Create Fine

**[POST]** You can create a new fines sending a object like the following /fines/

**[URL]** https://api.libary.management/api/v1/fines/

### Header

- **Authorization**: Bearer {api_key_librarian}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

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

**[PATCH]** The ************Fines************ endpoint allows changing state of one ********Fine********

**[URL]** https://api.libary.management/api/v1/fines/{id}

### Header

- **Authorization**: Bearer {api_key_librarian}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Parameter

- **ID (Required):** Unique identifier for a fines

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

**[MULTIPLE DELETES]** Adds the ids separate by **‘,’:**  https://api.libary.management/api/v1/fines/1,2,3

### Header

- **Authorization**: Bearer {api_key_librarian}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Parameter

| Parameter | Type | Description | Required |
| --- | --- | --- | --- |
| id | Number | Required. Id fine | Yes |

### Response

```json
{
	"status_process": true
}
```

# **************************Books Actions**************************

# Borrow A Book

**[POST]** You can borrow a book sending a object like the following

**[URL]** https://api.libary.management/api/v1/book/action/borrow

### Header

- **Authorization**: Bearer {api_key}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Body

```json
{
	"bookCopyId": 30,
	"userId": 25,
}
```

### Response

```json
{
	"id": 1,
	"bookCopyId": 30,
	"userId": 25,
	"startDate": "17/02/2023"
	"endDate": "03/03/2023"
	"isReturned" false
}
```

# Return A Book

**[PUT]** You can return a book sending a object like the following

**[URL]** https://api.libary.management/api/v1/book/action/return/{book_copy_id}

### Header

- **Authorization**: Bearer {api_key}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Body

```json
{
	"book_copy_id": 30,
	"user_id": 25,
}
```

### Response

```json
{
	"id": 1,
	"bookCopyId": 30,
	"userId": 25,
	"startDate": "17/02/2023"
	"endDate": "03/03/2023"
	"isReturned" true
}
```

# Extend Return Time

**[PATCH]** You can return a book sending a object like the following

**[URL]** https://api.libary.management/api/v1/book/action/return/{book_copy_id}

### Header

- **Authorization**: Bearer {api_key}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Body

```json
{
	"endDate": "07/03/2023"
}
```

### Response

```json
{
	"id": 1,
	"bookCopyId": 30,
	"userId": 25,
	"startDate": "17/02/2023"
	"endDate": "07/03/2023"
	"isReturned" false
}
```

# Auth JWT

# Authentication

**[POST]** You can do login sending an object like the following

**[URL]** https://api.libary.management/api/v1/auth/login

### Body

```json
{
	"email": "team2@mail.com",
	"password": "team2",
}
```

### Response

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOjEsImlhdCI6MTY3Mjc2NjAyOCwiZXhwIjoxNjc0NDk0MDI4fQ.kCak9sLJr74frSRVQp0_27BY4iBCgQSmoT3vQVWKzJg"
}
```

# Get User Session

**[POST]** You can get the profile the current user with session if in the headers include the token of the 

**[URL]** https://api.libary.management/api/v1/auth/profile

### Header

- **Authorization**: Bearer {api_key}

| Parameter | Type | Description |
| --- | --- | --- |
| api_key | string | Required. Your API key |

### Response

```json
{
 "id": 1,
  "firstName": "Team 2",
  "lastName": "The greatest",
  "email": "team2@mail.com",
  "phoneNumber": "047877546",
  "creationDate": "17/02/2023"
}
```
