Restful Booker API Automation Project
This project demonstrates the automation of the Restful Booker API using Postman Collection, Newman, and htmlextra reporting.

Technology Used
Postman: Used for collection creation and test case creation.
Newman: Used for automating the collection running.
Jenkins: Used for CI/CD integration.
Chai Library: Used for assertions.
Endpoints
The following endpoints are available in the API:

Create Token

Method: POST
URL: /api-clients/
Description: Creates a token for API authentication.
Request Body:
json
Copy
{
  "clientName": "Postman",
  "clientEmail": "valentin@example.com"
}
Response: The response body will contain the access token.
Get Status

Method: GET
URL: /status
Description: Returns the status of the API.
Get a List of Books

Method: GET
URL: /books
Description: Returns a list of books.
Optional Query Parameters:
type: Fiction or non-fiction.
limit: A number between 1 and 20.
Get a Single Book

Method: GET
URL: /books/:bookId
Description: Retrieves detailed information about a book.
Submit an Order

Method: POST
URL: /orders
Description: Submits a new order. Requires authentication.
Request Body:
json
Copy
{
  "bookId": 1,
  "customerName": "John"
}
Authorization Header: Bearer <YOUR TOKEN>
Response: The response body will contain the order ID.
Get All Orders

Method: GET
URL: /orders
Description: Retrieves all orders. Requires authentication.
Get a Single Order

Method: GET
URL: /orders/:orderId
Description: Retrieves an existing order. Requires authentication.
Update an Order

Method: PATCH
URL: /orders/:orderId
Description: Updates an existing order. Requires authentication.
Request Body:
json
Copy
{
  "customerName": "John"
}
Authorization Header: Bearer <YOUR TOKEN>
Delete an Order

Method: DELETE
URL: /orders/:orderId
Description: Deletes an existing order. Requires authentication.
Authorization Header: Bearer <YOUR TOKEN>
Get After Delete

Method: GET
URL: /orders
Description: Retrieves all orders after a delete operation. Requires authentication.
Testing Instructions
To test the API endpoints, follow these steps:

Import the provided Postman collection into Postman.
Set up the required environment variables, if any, such as YOUR TOKEN.
Execute the test cases in the collection to validate each endpoint's functionality.
Use Newman to run the collection and test cases in an automated manner.
Integrate the collection execution into Jenkins for CI/CD purposes.
Ensure that you have the necessary credentials and tokens for authentication when sending requests to protected endpoints.

Test Coverage - E2E Scenario
The following features are covered by the test cases to implement an end-to-end (E2E) scenario:

Create Token: Tests the creation of an API authentication token.
Get Status: Tests the retrieval of the API status.
Get a List of Books: Tests the retrieval of a list of books.
Get a Fiction Books: Tests the retrieval of fiction books.
Get a Non-fiction Books: Tests the retrieval of non-fiction books.
Get Books with Overlimit: Tests the retrieval of books with a limit exceeding the maximum allowed.
Get a Single Book: Tests the retrieval of detailed information about a single book.
Submit an Order: Tests the submission of a new order.
Get All Orders: Tests the retrieval of all orders.
Get a Single Order: Tests the retrieval of a single order.
Update an Order: Tests the update of an existing order.
Delete an Order: Tests the deletion of an existing order.
Get After Delete: Tests the retrieval of all orders after performing a delete operation.
Please refer to the Postman collection and test cases for detailed implementation and assertions for each feature.

Conclusion
This API documentation and testing guide provide an overview of the API endpoints, instructions for testing using Postman and Newman, and coverage details for an E2E scenario. Use this document as a reference to understand andtest the API's functionality and ensure that all endpoints are working as expected.
