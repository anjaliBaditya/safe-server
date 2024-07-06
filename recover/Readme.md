# Panic Demo App
This is a simple Go web application that demonstrates how to handle panics in a web server. The app has three endpoints:

- /panic/: This endpoint will panic immediately and return an error response.
- /panic-after/: This endpoint will write a response to the client and then panic. In a development environment, this will return a detailed error response with a stack trace. In a production environment, it will return a generic error response.
- /: This endpoint will return a simple "Hello!" response.

# How it Works
The app uses a custom middleware function recoverMw to catch and handle panics. This function wraps the main application handler and recovers from any panics that occur. If a panic occurs, it logs the error and stack trace, and returns an error response to the client.

In a development environment, the error response includes a detailed stack trace. In a production environment, it returns a generic error response.

# Running the App
To run the app, simply execute the following command:

```bash 
go run main.go
```

This will start the web server on port 3000. You can access the app by visiting http://localhost:3000 in your web browser.

# Endpoints
- http://localhost:3000/panic/: Panic immediately
- http://localhost:3000/panic-after/: Write response and then panic
- http://localhost:3000/: Hello world response
