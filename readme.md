# 📡 Assignment 1: HTTP Protocol Evolution

This document provides a detailed overview of the evolution of the HTTP protocol from version **0.9 to 3.0**.

---

## 1. HTTP/0.9 – The Beginning (1991)

📜 **Overview**  
The first version of HTTP, used by the **World Wide Web project** by Tim Berners-Lee.  
Extremely simple, designed for early experimentation.

🔧 **Features**  
- Only supported the **GET** method.  
- Could only fetch **raw HTML files** (no images, stylesheets, etc.).  
- No support for **headers** or **status codes**.  
- Responses were plain, unstructured data.

🔍 **Limitations**  
- No way to send **metadata** or control the response.  
- No support for **multimedia** or **dynamic content**.  
- Not scalable for growing web needs.

---

## 2. HTTP/1.0 – Structured Communication (1996)

📜 **Overview**  
The first version to be officially documented in an **RFC (RFC 1945)**.  
Added support for headers and multiple methods.

🔧 **Features**  
- Supported methods: **GET, POST, HEAD**.  
- Response headers introduced (e.g., `Content-Type`, `Content-Length`).  
- Status codes like **200 OK**, **404 Not Found**.  
- Each request opened a **new TCP connection**, closed after the response.

🔍 **Limitations**  
- Opening new TCP connections for each request added **latency**.  
- Poor efficiency for pages with **multiple assets** (e.g., images, scripts).  
- No support for **virtual hosting**.

---

## 3. HTTP/1.1 – Persistent Connections & Optimization (1997–1999)

📜 **Overview**  
Defined in **RFC 2068** and revised in **RFC 2616**.  
Most widely used version for over a decade.

🔧 **Features**  
- **Persistent connections (keep-alive)**: Multiple requests over one connection.  
- **Pipelining**: Send multiple requests without waiting for each response.  
- **Host header**: Enables **virtual hosting** (multiple domains per IP).  
- **Chunked transfer encoding**: Send data without knowing full size.  
- Improved **caching**, **proxy handling**, and **content negotiation**.

🔍 **Limitations**  
- Pipelining had **limited adoption** due to complexity.  
- **Head-of-line blocking**: One slow request could block others.  
- Still **text-based** and verbose.

---

## 4. HTTP/2 – Performance Revolution (2015)

📜 **Overview**  
Based on Google’s **SPDY** protocol.  
Defined in **RFC 7540**.  
Aimed to reduce latency and fix head-of-line blocking issues in HTTP/1.1.

🔧 **Features**  
- **Binary protocol**: Efficient parsing and compact messages.  
- **Multiplexing**: Multiple streams over a single connection.  
- Header compression with **HPACK**.  
- **Server push**: Server sends resources before they're requested.  
- **Stream prioritization** for better performance.

🔍 **Limitations**  
- Still relies on **TCP**, which can suffer from **head-of-line blocking**.  
- One packet loss can delay all streams due to TCP retransmission.

---

## 5. HTTP/3 – Built on QUIC (2020)

📜 **Overview**  
Defined in **RFC 9114**.  
Based on Google’s **QUIC** protocol, using **UDP** instead of TCP.  
Designed to eliminate transport-layer bottlenecks in HTTP/2.

🔧 **Features**  
- Uses **QUIC**: Avoids TCP head-of-line blocking.  
- Built-in **TLS 1.3**: Always encrypted.  
- Faster **connection establishment**.  
- **Stream-level multiplexing**: Streams are independent.  
- Resilient to **network changes** (e.g., mobile handovers).

🔍 **Benefits**  
- Lower **latency**, faster load times.  
- Better suited for **modern networks** and **mobile devices**.  
- Always **encrypted and secure**.

---

## 📈 Summary Table

| Feature                  | HTTP/0.9 | HTTP/1.0           | HTTP/1.1                  | HTTP/2                | HTTP/3                   |
|--------------------------|----------|--------------------|---------------------------|------------------------|---------------------------|
| **Request Methods**      | GET      | GET, POST, HEAD    | + PUT, DELETE, OPTIONS    | All HTTP/1.1 +         | All HTTP/2 +              |
| **Headers Support**      | ❌        | ✅                  | ✅                         | ✅                      | ✅                         |
| **Persistent Connections** | ❌      | ❌                  | ✅                         | ✅                      | ✅                         |
| **Pipelining**           | ❌        | ❌                  | ✅ (limited)              | ✅ (multiplexed)        | ✅ (independent streams)   |
| **Transport Protocol**   | TCP      | TCP                | TCP                       | TCP                    | UDP (via QUIC)            |
| **Encryption (TLS)**     | ❌        | Optional           | Optional                  | Optional               | Mandatory (TLS 1.3)       |
| **Compression**          | ❌        | ❌                  | ✅                         | ✅ (HPACK)              | ✅ (QPACK)                |
| **Server Push**          | ❌        | ❌                  | ❌                         | ✅                      | ✅                         |

---

📘 *End of Assignment 1: HTTP Protocol Evolution*
