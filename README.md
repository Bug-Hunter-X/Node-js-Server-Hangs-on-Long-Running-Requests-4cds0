# Node.js Server Hang Issue

This repository demonstrates a common issue in Node.js servers: hanging on long-running requests.  The `server.js` file shows a server that performs a 5-second blocking operation for each request. This blocks the event loop, preventing other requests from being processed. 

The `serverSolution.js` file provides a solution using asynchronous operations to avoid blocking.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node server.js`.
4. Open multiple browser tabs and make requests to `http://localhost:3000`. You'll observe that only one request is processed at a time, and subsequent requests hang.
5. Run `node serverSolution.js` and repeat step 4 to observe that requests are handled concurrently.

## Solution

The solution involves avoiding blocking operations in the main thread.  Use asynchronous functions to handle long-running tasks.