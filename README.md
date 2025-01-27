# Unhandled Promise Rejection in Express.js

This example demonstrates an uncommon error in Express.js applications: unhandled promise rejections within asynchronous request handlers.  Failing to handle errors in asynchronous functions can lead to unexpected behavior, particularly in production environments where error logging might be insufficient. The bug lies in the missing error handling for the promise returned by `someAsyncOperation()`. 

**How to reproduce:** Run the `bug.js` file. The server will start, but if you make a request to the `/` endpoint, the server will throw an error silently.  No useful response will be sent to the client, and the error will likely only appear in the console if you are running the server directly.  This makes debugging difficult.