# Multithreaded Proxy Web Server

## Project Overview

This project aims to develop a multithreaded proxy web server that can handle multiple client requests concurrently. The server will forward requests from clients to the appropriate web servers and return the responses back to the clients.

## Current Status

The project is currently under active development. Feedback are welcome.

### Completed Tasks

- **Project Setup**: Initialized the project structure and set up the development environment.
- **Basic Proxy Functionality**: Implemented basic proxy functionality to forward HTTP requests and responses.
- **Multithreading**: Added multithreading support to handle multiple client connections simultaneously.
- **Logging**: Implemented basic logging to track incoming requests and server responses.

### In Progress

- **Error Handling**: Improving error handling mechanisms to manage various edge cases and exceptions.
- **Performance Optimization**: Optimizing the server for better performance and resource management.

### To Do

- **HTTPS Support**: Adding support for HTTPS connections.
- **Caching**: Implementing caching mechanisms to improve response times for frequently requested resources.
- **Security**: Enhancing security features to protect against common web vulnerabilities.

## How to Run

1. Clone the repository.
2. Navigate to the project directory.
3. Compile the source code.
4. Run the server executable.

```bash
git clone https://github.com/Sayantan627/Multithreaded-Proxy-Web-Server
cd Multithreaded-Proxy-Web-Server
make
./proxy_server
```
