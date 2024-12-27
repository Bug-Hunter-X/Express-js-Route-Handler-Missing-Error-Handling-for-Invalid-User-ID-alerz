# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer but doesn't handle the case where the parameter is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  It attempts to find a user based on the provided ID, but if the ID is not a number, the `parseInt` function will return `NaN`, causing the `.find()` method to fail silently and potentially lead to errors later in the application.

## Solution

The `bugSolution.js` file demonstrates the corrected code.  It includes explicit error handling to check if the parsed ID is a number and returns a 400 Bad Request response if it's not.