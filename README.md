Product API – Week 2 Assignment
This project is a simple RESTful API built using Express.js to manage a collection of products. The API supports full CRUD (Create, Read, Update, Delete) operations, with data stored in memory for simplicity. Additionally, the server implements middleware for request logging, authentication, and error handling to ensure secure and maintainable code.

All API requests require an Authorization header with a token for access. The expected token is:

makefile
Copy
Edit
Authorization: Bearer mysecrettoken
You can modify this token in the server.js file if needed.

The API exposes five main endpoints. First, GET /api/products returns a list of all available products, each represented with fields like id, name, description, price, category, and inStock status. Second, GET /api/products/:id retrieves a specific product by its unique ID, returning a 404 error if the product does not exist.

To add a new product, clients can use POST /api/products by providing product details in the request body. On success, the API responds with the created product including a new unique ID. Updating an existing product is handled by PUT /api/products/:id, allowing clients to send partial or complete updates for product fields. If the product is not found, a 404 response is returned. Finally, DELETE /api/products/:id removes a product by ID, returning the deleted product's information or a 404 error if not found.

The middleware setup includes request logging, which outputs the HTTP method and request path with timestamps to the console for monitoring. Authentication middleware verifies the presence and correctness of the token in the Authorization header, rejecting unauthorized requests with a 401 status. An error-handling middleware catches unexpected server errors, logging them and returning a 500 response with a generic message.

To run this API locally, clone the repository, install the dependencies using npm install, and start the server with node server.js. The server listens on port 3000 by default. You can test the API endpoints using tools like Postman or curl, making sure to include the required authorization token in your requests.

Error responses are clearly handled: 401 Unauthorized if authentication fails, 404 Not Found if the product ID is missing, and 500 Internal Server Error for unexpected issues.

This project fulfills the assignment requirements by implementing all required API endpoints, middleware for logging, authentication, and error handling, and is accompanied by documentation including example requests and responses.

