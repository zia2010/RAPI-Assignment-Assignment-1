# 📘 HTTP/3 – Over QUIC (UDP, TLS 1.3)

## 🌐 Overview

HTTP/3 is the latest version of the HTTP protocol, defined in RFC 9114. It is built on top of **QUIC**, a transport protocol developed by Google, which uses **UDP** instead of TCP and includes **TLS 1.3** by default.

This protocol is designed to address the limitations of HTTP/2, especially the head-of-line blocking caused by TCP.

---

## ⚙️ Key Features

| Feature                | Description |
|------------------------|-------------|
| **Transport Layer**    | Uses UDP + QUIC instead of TCP |
| **Encryption**         | Always encrypted (TLS 1.3 is mandatory) |
| **Multiplexing**       | Multiple independent streams with no blocking |
| **Fast Handshake**     | Combines transport and TLS handshakes into 1 or 0 RTT |
| **Resilience**         | Can maintain sessions across IP/network changes (e.g., Wi-Fi to 4G) |

---

## 🔥 Benefits of HTTP/3

- 🚀 **Faster Page Loads**: Eliminates TCP-level blocking.
- 📱 **Mobile-Friendly**: Robust against network switches.
- 🔒 **Secure by Default**: Always encrypted with TLS 1.3.
- 🔄 **Efficient Stream Handling**: Streams don't interfere with each other.

---

## 🧪 Testing HTTP/3 in Practice

### ✅ Option 1: Using `curl` with HTTP/3 Support

You can test HTTP/3 requests using `curl` compiled with HTTP/3 support.

```bash
curl --http3 https://cloudflare.com

### ✅ Option 2: Node.js Code to Run curl (HTTP/3 via QUIC)

```bash
const { exec } = require('child_process');

exec('curl --http3 https://cloudflare.com', (error, stdout, stderr) => {
  if (error) {
    console.error(`Error: ${error.message}`);
    return;
  }
  console.log(stdout);
});