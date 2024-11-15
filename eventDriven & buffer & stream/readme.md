# Node.js Simple HTTP Server

This project is a simple Node.js application that creates an HTTP server. The server allows users to enter a message through a form, save it to a file, and redirect back to the home page.

## Features

- **Home Page**: Displays a form where you can enter a message.
- **Save Message**: Takes the input message from the form and saves it to a `message.txt` file.
- **Redirection**: After submitting the form, the user is redirected back to the home page.

## How It Works

1. The server listens on port **3000**.
2. When you access the root URL (`/`), it shows a simple HTML form.
3. When the form is submitted, the data is sent to the `/message` endpoint using a `POST` request.
4. The server captures the message, saves it to a `message.txt` file, and then redirects you back to the home page.

## Event-Driven Architecture

This server utilizes Node.js's event-driven, non-blocking I/O model:

1. **HTTP Server**: Creates an HTTP server that listens for incoming requests.

2. **Request Handling**: Each incoming request triggers a callback function.

3. **POST Request Handling**: 
   - `req.on('data')`: Listens for chunks of data from the request body.
   - `req.on('end')`: Triggered when the entire request body has been received.

4. **File Operations**: Uses synchronous file writing, but can be adapted to use asynchronous methods for better performance in high-load scenarios.

5. **Server Listening**: The server listens on port 3000, ready to handle incoming connections.

This event-driven approach allows the server to handle multiple connections efficiently without blocking the main thread.
