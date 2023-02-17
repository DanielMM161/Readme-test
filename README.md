# Readme-test
<details> 
  <summary><h1>Fines</h1></summary>
  <blockquote>
    <p>[POST] You can create a new fines sending a object like the following /fines/</p>
    <p>[URL] https://api.library.management/api/v1/fines/</p>
    <details>  
      <summary><h2>Create Fines</h2></summary>
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
    </details>
  </blockquote>  
</details>


