# Proxy Server with Caching

This project is a multi-threaded proxy server implemented in C that supports caching, allowing efficient retrieval and delivery of web content. The server handles HTTP requests by forwarding them to the requested server, caching responses for future requests to reduce latency and resource usage.

## Features

- **Proxy Server**: Forwards HTTP requests to the destination server and relays the responses to the client.
- **Caching**: Caches HTTP responses for frequently requested resources, improving response times.
- **Concurrency**: Uses multi-threading to handle multiple client requests concurrently.
- **Request Parsing**: Interprets and processes incoming HTTP requests to determine if a response can be served from cache or needs forwarding.

## Prerequisites

- **C Compiler**: Make sure you have `gcc` installed for compilation.
- **POSIX Threads (pthreads)**: The server is implemented using pthreads for concurrency.
- **Libraries**: Ensure the necessary system libraries (such as `<pthread.h>`, `<semaphore.h>`, `<netinet/in.h>`) are available.

## Compilation and Setup

To compile and set up the project:

1. Clone the repository or download the files to your local machine.
2. Open a terminal in the project directory and run:

   ```bash
   gcc -g -Wall -o proxy server_with_cache.c -lpthread
   ```

   This will compile the source file with debugging information and link the pthread library.

3. Run the server with:

   ```bash
   ./proxy <port>
   ```

   Replace `<port>` with the port number you want the server to listen on (e.g., 8080).

## Usage

To test the proxy server:

1. Start the server on a specific port (e.g., 8080):

   ```bash
   ./proxy 8080
   ```

2. Open a web browser or use a command-line tool (e.g., `curl`) to send an HTTP request via the proxy:

   ```bash
   curl -x http://localhost:8080/https://www.cs.princeton.edu/
   ```

   The server will:

   - Check if the requested content is in the cache.
   - Fetch the content from the destination if it's not cached.
   - Cache the new content for future requests.

### Example

```bash
curl -x http://localhost:8080/https://example.com
```

This sends a request for `https://example.com` through the proxy, and the server will return the response, storing it in the cache if applicable.

## Troubleshooting

- **"Bad Request" Response**: Ensure the request URL follows the format `http://localhost:<port>/<URL>` without any extra schemas.
- **Permission Errors**: Ensure you have appropriate permissions to bind the server to the chosen port.
- **Cache Invalidation**: If stale data is served, ensure cache entries are properly invalidated or refreshed.
