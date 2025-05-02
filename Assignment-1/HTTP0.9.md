# 📘 HTTP/0.9 – The Beginning (1991)

## 🌐 Overview

HTTP/0.9, the first version of the HTTP protocol, was introduced in 1991 as part of Tim Berners-Lee's **World Wide Web** project. It was extremely simple and designed for early experimentation with web technologies. Unlike later versions of HTTP, HTTP/0.9 was very basic and had a limited set of features.

It was essentially a bare-bones protocol for transferring raw HTML files between clients (typically browsers) and servers.

---

## ⚙️ Key Features

| Feature                | Description |
|------------------------|-------------|
| **Request Method**      | Only supports `GET` method. |
| **Response**            | Plain HTML response, no headers or status codes. |
| **File Type**           | Only raw HTML files could be served, no multimedia, images, or scripts. |
| **No Metadata**         | No support for headers, cookies, or status codes. |

---

## 🔥 Limitations of HTTP/0.9

- 📄 **No Headers**: HTTP/0.9 does not support headers, meaning there is no way to send metadata about the response (like content type or length).
- 🎨 **Limited Content Types**: It could only serve raw HTML content, meaning no images, CSS, JavaScript, or other multimedia.
- 🔒 **No Encryption**: HTTP/0.9 was designed in an era before security and encryption were considered important, so it lacked any form of encryption or secure connection.
- ⚠️ **No Status Codes**: There were no status codes (such as `200 OK` or `404 Not Found`), so there was no way to provide feedback about the success or failure of requests.
- 🚫 **No Scalability**: With no support for multiple methods or headers, HTTP/0.9 wasn't scalable for more complex web applications.

---

## 🧪 Example of HTTP/0.9 Request and Response

### ✅ HTTP/0.9 Request

A typical HTTP/0.9 request would look like this:

```plaintext
GET /index.html
```

### ✅ HTTP/0.9 Response
The server would simply send back the raw HTML content without any headers or status codes:

```plaintext

<HTML>
  <HEAD><TITLE>Welcome to HTTP/0.9</TITLE></HEAD>
  <BODY>
    <H1>HTTP/0.9 Example</H1>
    <P>Simple request-response without headers.</P>
  </BODY>
</HTML>

```

### 🔄 Limitations of HTTP/0.9
 - No Support for HTTP Methods: Only the GET method was supported, making it inadequate for more complex operations such as form submission (POST), data retrieval (PUT), and deletion (DELETE).

 - No Metadata or Caching: With no support for headers, caching, or cookies, HTTP/0.9 lacked the mechanisms that modern HTTP protocols use to manage resources efficiently.

 - No Status Codes: Without status codes, it was impossible to determine whether a request succeeded or failed, which was a significant limitation as the web grew in complexity.
