# 📘 HTTP/1.0 and HTTP/1.1 – The Foundation (1996-1999)

## 🌐 Overview

### **HTTP/1.0 (1996)**

HTTP/1.0, defined in **RFC 1945**, was the first version of HTTP to be formally documented. It introduced basic support for headers, methods like `GET`, `POST`, and `HEAD`, and the concept of status codes. However, it was not efficient enough for the growing needs of the web.

### **HTTP/1.1 (1997-1999)**

HTTP/1.1, defined in **RFC 2616**, became the most widely used version of HTTP for over a decade. It introduced many optimizations, such as persistent connections, chunked transfer encoding, and improved caching mechanisms.

---

## ⚙️ Key Features

| Feature                    | HTTP/1.0                               | HTTP/1.1                                |
|----------------------------|----------------------------------------|-----------------------------------------|
| **Request Methods**         | `GET`, `POST`, `HEAD`                  | `GET`, `POST`, `HEAD`, `PUT`, `DELETE`, `OPTIONS`, `PATCH` |
| **Persistent Connections**  | ❌ (new connection per request)        | ✅ (keep-alive)                         |
| **Chunked Transfer Encoding** | ❌                                    | ✅ (allows streaming response body)     |
| **Host Header**             | ❌                                      | ✅ (supports virtual hosting)          |
| **Cache Control**           | ❌                                      | ✅ (cache control and better caching)   |

---

## 🔥 Benefits of HTTP/1.0 and HTTP/1.1

- 🌐 **Basic Structure**: Standardized communication between clients and servers.
- 🔄 **Caching**: Improved ability to cache resources to reduce redundancy.
- 🔄 **Persistent Connections** (HTTP/1.1): Reduced latency by reusing connections.
- 📝 **Request Methods**: Expanded methods (`PUT`, `DELETE`, etc.) in HTTP/1.1 support various use cases.

---

## 🧪 HTTP/1.x Example in Node.js

### ✅ Simple HTTP/1.1 Server Example

```js
const http = require('http');

// Create HTTP server
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, world!');
});

// Listen on port 8080
server.listen(8080, () => {
  console.log('HTTP/1.1 server running at http://localhost:8080/');
});

```

### 🔄 Limitation of HTTP/1.1
⚖️ Multiple Connections: Even with persistent connections, HTTP/1.1 still suffers from inefficiency in handling many concurrent requests because the connections are limited to the number of requests a browser can make in parallel (usually around 6).

 - 🔴 Head-of-Line Blocking: If one request on a connection is slow, all subsequent requests in the same connection are delayed.

 - 🧑‍💻 Verbose Protocol: Headers can be large and contain redundant data, especially with repeated requests