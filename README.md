# HTTP Server with Panic Recovery

This Go program demonstrates a simple HTTP server that handles panics and recovers from them. The server listens on port 3000 and responds to three different routes:

- /: Returns a simple "Hello!" message.
- /panic/: Triggers a panic and demonstrates how the server recovers from it.
- /panic-after/: Returns a "Hello!" message and then triggers a panic, demonstrating how the server recovers from it even after sending a response.

The server uses a middleware function to recover from panics and return a 500 Internal Server Error response to the client.

# Prerequisites
- Go 1.16
- Internet connection

# Installation
- Clone the repository
```bash
git clone
```
# Routes
- /: Returns a simple "Hello!" message.
- /panic/: Triggers a panic and demonstrates how the server recovers from it.
- /panic-after/: Returns a "Hello!" message and then triggers a panic, demonstrating how the server recovers from it even after sending a response.

# Panic Recovery Mechanism
The recoverMw function is a middleware that wraps the main application handler. It uses a deferred function to catch any panics that occur during the execution of the application handler. If a panic is caught, it logs the error and returns a 500 Internal Server Error response to the client.

# Code Organization
The code is organized into the following functions:

- main: The entry point of the program. It sets up the HTTP server and starts listening on port 3000.
- recoverMw: The panic recovery middleware.
- panicDemo: A handler that triggers a panic immediately.
- panicAfterDemo: A handler that returns a response and then triggers a panic.
- funcThatPanics: A function that simply panics with a message.
- hello: A handler that returns a simple "Hello!" message.

# Running the Server
To run the server, simply execute the Go program:
```bash 
go run main.go
```

Then, open a web browser and navigate to http://localhost:3000/ to see the "Hello!" message. Navigate to http://localhost:3000/panic/ or http://localhost:3000/panic-after/ to trigger a panic and see how the server recovers from it.

# Notes
This implementation is a simple demonstration of panic recovery and may not be suitable for production use without additional error handling and logging mechanisms.
In a real-world scenario, you would want to handle errors more robustly and provide more informative error messages to the client.
