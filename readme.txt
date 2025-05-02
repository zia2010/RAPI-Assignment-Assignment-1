1. HTTP/0.9 – The Beginning (1991)
📜 Overview:
The first version of HTTP, used by the World Wide Web project by Tim Berners-Lee.

Extremely simple, designed for early experimentation.

🔧 Features:
Only supported the GET method.

Could only fetch raw HTML files (no images, stylesheets, etc.).

No support for headers or status codes.

Responses were plain, unstructured data.

🔍 Limitations:
No way to send metadata or control the response.

No support for multimedia or dynamic content.

Not scalable for growing web needs.

2. HTTP/1.0 – Structured Communication (1996)
📜 Overview:
The first version to be officially documented in an RFC (RFC 1945).

Added support for headers and multiple methods.

🔧 Features:
Supported methods: GET, POST, HEAD.

Response headers introduced (like Content-Type, Content-Length).

Status codes such as 200 OK, 404 Not Found.

Each request opened a new TCP connection, and closed it after the response.

🔍 Limitations:
Opening a new TCP connection for each request added latency.

Poor efficiency for pages with multiple assets (e.g., images, scripts).

No support for virtual hosting.

3. HTTP/1.1 – Persistent Connections & Optimization (1997-1999)
📜 Overview:
Defined in RFC 2068 and revised in RFC 2616.

Most widely used version for over a decade.

🔧 Features:
Persistent connections (keep-alive): Multiple requests over one TCP connection.

Pipelining: Send multiple requests without waiting for responses (though limited by head-of-line blocking).

Host header: Enables virtual hosting (multiple domains on the same IP).

Chunked transfer encoding: Stream data without knowing full size beforehand.

Improved caching, proxy handling, and content negotiation.

🔍 Limitations:
Pipelining wasn’t widely adopted due to implementation issues.

Head-of-line blocking: One slow request blocks others in the queue.

Still text-based and verbose.

4. HTTP/2 – Performance Revolution (2015)
📜 Overview:
Based on Google's SPDY protocol.

Defined in RFC 7540.

Aimed to solve latency and head-of-line blocking in HTTP/1.1.

🔧 Features:
Binary protocol: More efficient parsing and compact representation.

Multiplexing: Multiple streams over a single TCP connection.

Header compression with HPACK: Reduces redundancy.

Server push: Server can send resources before the client asks.

Stream prioritization for better performance.

🔍 Limitations:
Still relies on TCP, which can suffer from head-of-line blocking at the transport layer.

If one packet is lost, TCP must wait for retransmission, blocking all streams in that connection.

5. HTTP/3 – Built on QUIC (2020)
📜 Overview:
Defined in RFC 9114.

Based on Google's QUIC protocol, which uses UDP instead of TCP.

Designed to fix HTTP/2’s transport-level issues.

🔧 Features:
Uses QUIC: Eliminates TCP’s head-of-line blocking.

Built-in TLS 1.3: Security is integrated and always enabled.

Faster connection establishment: Combines handshake and encryption negotiation.

Stream-level multiplexing: Independent streams mean one stream doesn’t block others.

More resilient to network changes (e.g., mobile switching from Wi-Fi to 4G).

🔍 Benefits:
Lower latency and faster load times.

Better suited for modern networks and mobile devices.

Automatically encrypted and secure.

