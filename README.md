# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation blocking the event loop.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded.  If a request handler performs a long-running synchronous operation (like the 5-second loop in `server.js`), it blocks the event loop, preventing the server from handling other requests. This leads to unresponsiveness and potentially hangs.

## Solution

The solution lies in using asynchronous operations.  Instead of blocking the event loop, asynchronous operations allow the server to continue processing other requests while the long-running task is performed in the background.  The `serverSolution.js` illustrates how to achieve this using `setTimeout`.