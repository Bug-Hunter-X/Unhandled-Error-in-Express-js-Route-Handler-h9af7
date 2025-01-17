# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the provided code attempts to access a user based on an ID passed as a route parameter. However, it fails to handle cases where the ID is not a valid integer, resulting in potential crashes or unexpected behavior.

The `bug.js` file contains the erroneous code.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug

The primary issue is that `parseInt(userId)` might return `NaN` if `userId` is not a valid integer.  Using this `NaN` value in the `users.find()` method can lead to unexpected results and potential crashes. The code lacks explicit checks for `NaN` and does not provide graceful error handling.