

# Restful Booker API Automation Project

This project demonstrates the automation of the Restful Booker API using Postman Collection, Newman, and htmlextra reporting.


## Technology Used

- Postman: Used for collection creation and test case creation.
- Newman: Used for automating the collection running.
- Jenkins: Used for CI/CD integration.
- Chai Library: Used for assertions.

## Endpoints

The following endpoints are available in the API:

1. **Create Token**
   - Method: POST
   - URL: `/api-clients/`
   - Description: Creates a token for API authentication.
   - Request Body:
     ```json
     {
       "clientName": "Postman",
       "clientEmail": "valentin@example.com"
     }
     ```
   - Response: The response body will contain the access token.

2. **Get Status**
   - Method: GET
   - URL: `/status`
   - Description: Returns the status of the API.

3. **Get a List of Books**
   - Method: GET
   - URL: `/books`
   - Description: Returns a list of books.
   - Optional Query Parameters:
     - `type`: Fiction or non-fiction.
     - `limit`: A number between 1 and 20.

4. **Get a Single Book**
   - Method: GET
   - URL: `/books/:bookId`
   - Description: Retrieves detailed information about a book.

5. **Submit an Order**
   - Method: POST
   - URL: `/orders`
   - Description: Submits a new order. Requires authentication.
   - Request Body:
     ```json
     {
       "bookId": 1,
       "customerName": "John"
     }
     ```
   - Authorization Header: Bearer `<YOUR TOKEN>`
   - Response: The response body will contain the order ID.

6. **Get All Orders**
   - Method: GET
   - URL: `/orders`
   - Description: Retrieves all orders. Requires authentication.

7. **Get a Single Order**
   - Method: GET
   - URL: `/orders/:orderId`
   - Description: Retrieves an existing order. Requires authentication.

8. **Update an Order**
   - Method: PATCH
   - URL: `/orders/:orderId`
   - Description: Updates an existing order. Requires authentication.
   - Request Body:
     ```json
     {
       "customerName": "John"
     }
     ```
   - Authorization Header: Bearer `<YOUR TOKEN>`

9. **Delete an Order**
   - Method: DELETE
   - URL: `/orders/:orderId`
   - Description: Deletes an existing order. Requires authentication.
   - Authorization Header: Bearer `<YOUR TOKEN>`

10. **Get After Delete**
    - Method: GET
    - URL: `/orders`
    - Description: Retrieves all orders after a delete operation. Requires authentication.

## Testing Instructions

To test the API endpoints, follow these steps:

1. Import the provided Postman collection into Postman.
2. Set up the required environment variables, if any, such as `YOUR TOKEN`.
3. Execute the test cases in the collection to validate each endpoint's functionality.
4. Use Newman to run the collection and test cases in an automated manner.
5. Integrate the collection execution into Jenkins for CI/CD purposes.

Ensure that you have the necessary credentials and tokens for authentication when sending requests to protected endpoints.

## Test Coverage - E2E Scenario

The following features are covered by the test cases to implement an end-to-end (E2E) scenario:

1. Create Token: Tests the creation of an API authentication token.
2. Get Status: Tests the retrieval of the API status.
3. Get a List of Books: Tests the retrieval of a list of books.
4. Get a Fiction Books: Tests the retrieval of fiction books.
5. Get a Non-fiction Books: Tests the retrieval of non-fiction books.
6. Get Books with Overlimit: Tests the retrieval of books with a limit exceeding the maximum allowed.
7. Get a Single Book: Tests the retrieval of detailed information about a single book.
8. Submit an Order: Tests the submission of a new order.
9. Get All Orders: Tests the retrieval of all orders.
10. Get a Single Order: Tests the retrieval of a single order.
11. Update an Order: Tests the update of an existing order.
12. Delete an Order: Tests the deletion of an existing order.
13. Get After Delete: Tests the retrieval of all orders after performing a delete operation.

Please refer to the Postman collection and test cases for detailed implementation and assertions for each feature.

## Conclusion

This API documentation and testing guide provide an overview of the API endpoints, instructions for testing using Postman and Newman, and coverage details for an E2E scenario. Use this document as a reference to understand andtest the API's functionality and ensure that all endpoints are working as expected.
