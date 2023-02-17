# Readme-test

<details> 
  <summary><h1>Fines</h1></summary>
  <blockquote>
    <p>[POST] You can create a new fines sending a object like the following /fines/</p>
    <p>[URL] https://api.library.management/api/v1/fines/</p>
    <details>  
      <summary><h2>Create Fines</h2></summary>
      <blockquote>
        <details>
          <summary>Header</summary>
          <blockquote>
            <li><b>Authorization</b>: Bearer {token_librarian_access}</li>
          </blockquote>
        </details>
        <details>
          <summary>Body</summary>
          <blockquote>
          ```json
          {
            "userId": 123,
            "bookId": 12,
            "fineType": "broke",
            "amount": 50
          }
          ```
          </blockquote>
        </details>                
      </blockquote>
    </details>
  </blockquote>  
</details>

