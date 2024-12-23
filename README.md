# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue when working with JSON request bodies in Express.js applications. The problem arises when the client sending the request doesn't include the correct `Content-Type` header, or includes an incorrect one (e.g., `text/plain`). In such cases, Express.js might fail to parse the request body correctly, leading to an empty `req.body` object.

## Bug Description

The provided `bug.js` file contains an Express.js server that expects a JSON request body. However, it doesn't handle cases where the `Content-Type` header is missing or incorrect.  This results in the server logging an empty object for `req.body`, even when the request body contains valid JSON data. 

## Solution

The `bugSolution.js` file provides a fix by using the `express.json()` middleware with an option to handle the error in a more robust way. If the content type is not specified, it will still parse the data.  This ensures that the server can correctly parse the JSON request body regardless of the presence or value of the `Content-Type` header.