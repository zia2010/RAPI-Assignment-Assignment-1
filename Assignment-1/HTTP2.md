# 📘 HTTP/2 – Performance Revolution (2015)

## 🌐 Overview

HTTP/2, standardized in **RFC 7540**, is a major revision of the HTTP protocol based on Google's experimental **SPDY** protocol. It was introduced to address the performance limitations of HTTP/1.1, especially its inefficiency in handling multiple concurrent requests.

Unlike HTTP/1.1, HTTP/2 uses a **binary** framing layer and supports true **multiplexing**, allowing multiple streams to be sent over a single connection.

---

## ⚙️ Key Features

| Feature               | Description |
|------------------------|-------------|
| **Binary Protocol**    | Faster and more efficient than HTTP/1.1's text-based format |
| **Multiplexing**       | Multiple requests/responses in parallel over a single connection |
| **Header Compression** | Uses HPACK to compress HTTP headers |
| **Server Push**        | Server can proactively send resources to the client |
| **Stream Prioritization** | Allows prioritizing important resources |

---

## 🔥 Benefits of HTTP/2

- 🧵 **Parallel Requests**: No need to open multiple TCP connections.
- 🗜️ **Smaller Headers**: Compression reduces redundant data.
- 🚚 **Server Push**: Reduces round trips by preloading needed assets.
- 🚀 **Improved Performance**: Lower latency and better throughput.

---

## 🧪 HTTP/2 in Node.js

Node.js has built-in support for HTTP/2 using the `http2` module (available from Node.js v8.4.0+).

### ✅ Basic HTTP/2 Server Example

```js
const http2 = require('http2');
const fs = require('fs');

// Load TLS certificate and key
const server = http2.createSecureServer({
  key: fs.readFileSync('server.key'),
  cert: fs.readFileSync('server.crt')
});

server.on('stream', (stream, headers) => {
  stream.respond({
    'content-type': 'text/html',
    ':status': 200
  });
  stream.end('<h1>Hello from HTTP/2 Server</h1>');
});

server.listen(8443, () => {
  console.log('HTTP/2 server listening on https://localhost:8443');
});
