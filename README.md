# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `server.js` file shows the problematic code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded and relies on the event loop to handle requests.  Synchronous operations that take a long time block the event loop, preventing the server from processing other requests. This leads to unresponsiveness and poor performance.

## Solution

The solution involves using asynchronous operations to avoid blocking the event loop.  This allows other requests to be processed concurrently.

## How to reproduce

1. Clone the repository.
2. Run `node server.js`.
3. Send multiple requests to the server. You'll notice it becomes unresponsive.
4. Then, run `node serverSolution.js` and test again.  It should handle concurrent requests effectively. 