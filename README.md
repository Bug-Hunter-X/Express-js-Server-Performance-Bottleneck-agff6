# Express.js Server Performance Bottleneck

This repository demonstrates a common performance issue in Node.js Express.js servers: event loop starvation.  The server, under load, becomes unresponsive due to inefficient handling of long-running operations.

The `bug.js` file contains the buggy code that demonstrates the issue. The `bugSolution.js` file contains the solution which addresses event loop starvation using worker threads.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`
3. Run `node bug.js`
4. Open multiple browser tabs and make requests to `http://localhost:3000`. Observe that requests become very slow or timeout.

## Solution
The solution utilizes worker threads to offload time-consuming tasks from the main event loop. This prevents the event loop from being blocked, resulting in improved server responsiveness.