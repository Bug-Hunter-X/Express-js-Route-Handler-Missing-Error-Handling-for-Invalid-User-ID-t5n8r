# Express.js Route Handler Bug: Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling when dealing with user inputs. Specifically, this example showcases a route that retrieves a user by ID but fails to handle cases where the provided ID is not a valid number.

## Bug Description
The `GET /users/:id` route attempts to parse the `id` parameter as an integer using `parseInt()`. However, if the `id` is not a number (e.g., a string), `parseInt()` will return `NaN`, leading to potential issues. The code lacks error handling to gracefully manage this scenario. This can cause the application to crash or return an unexpected response.

## Solution
The solution involves adding error handling to check if `parseInt(userId)` returns a valid number before attempting to access the `users` array.  If the ID is not a number, an appropriate error message should be returned.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Start the server using `node bug.js`.
4. Access the route with an invalid ID (e.g., `/users/abc`). Observe the error.
5. Then, switch to `bugSolution.js` and test with the same invalid ID.