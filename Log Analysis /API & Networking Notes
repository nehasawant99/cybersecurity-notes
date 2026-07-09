# API, Port Numbers & HTTP Status Codes

---

# 1. What is an API?

**API = Application Programming Interface**

Think of an API as a **waiter in a restaurant**.

```text
Customer → Waiter → Kitchen → Waiter → Customer
```

| Component | Represents          |
| --------- | ------------------- |
| Customer  | Your app or browser |
| Waiter    | API                 |
| Kitchen   | Server / Database   |

You don't go into the kitchen yourself. You ask the waiter (API), who brings back the response.

## Example

You open a weather app.

The app asks:

> "What's today's weather?"

It sends an API request.

The server replies:

```json
{
  "city": "Mumbai",
  "temperature": 30
}
```

The API delivers this information to your app.

---

# 2. What is a Port Number?

Imagine a company building.

* **IP Address = Building address**
* **Port = Door number**

The IP tells you **which computer**.

The port tells you **which service** on that computer.

## Example

```text
Computer
IP Address: 192.168.1.10

Door 22  → SSH
Door 80  → HTTP
Door 443 → HTTPS
Door 25  → SMTP
```

A single computer can run many services at the same time because each service uses a different port.

---

# Common Port Numbers (Very Important)

| Port   | Protocol | Purpose                   |
| ------ | -------- | ------------------------- |
| 20, 21 | FTP      | File Transfer             |
| 22     | SSH      | Secure Remote Login       |
| 23     | Telnet   | Remote Login (Not Secure) |
| 25     | SMTP     | Send Email                |
| 53     | DNS      | Domain Name Lookup        |
| 67, 68 | DHCP     | Automatic IP Assignment   |
| 80     | HTTP     | Websites (Not Secure)     |
| 110    | POP3     | Receive Email             |
| 143    | IMAP     | Receive Email             |
| 161    | SNMP     | Network Device Monitoring |
| 389    | LDAP     | Directory Services        |
| 443    | HTTPS    | Secure Websites           |
| 445    | SMB      | Windows File Sharing      |
| 3389   | RDP      | Remote Desktop            |

> 🎯 **Remember these:** **20/21, 22, 25, 53, 80, 443, 445, 3389**

---

# 3. What are HTTP Status Codes?

When your browser requests a web page, the server replies with a **status code**.

## Example

```text
Browser
   │
   ▼
GET /index.html

Server
   │
   ▼
200 OK
```

The number tells you what happened.

---

# 1xx – Informational

The server is processing the request.

### Example

```text
100 Continue
```

**Note:** Not commonly asked in fresher interviews.

---

# 2xx – Success ✅

Everything worked.

## 200 OK

### Example

```text
GET /index.html
        │
        ▼
     200 OK
```

**Meaning:**

The page loaded successfully.

---

## 201 Created

### Example

```text
POST /users
      │
      ▼
 201 Created
```

**Meaning:**

A new user was created successfully.

---

## 204 No Content

**Meaning:**

The request succeeded, but there's nothing to return.

---

# 3xx – Redirection ↪️

The browser needs to go somewhere else.

## 301 Moved Permanently

**Meaning:**

The page has permanently moved to a new location.

---

## 302 Found

**Meaning:**

Temporary redirect.

---

# 4xx – Client Errors ❌

The problem is with the request sent by the client.

---

## 400 Bad Request

### Example

```text
GET /????
    │
    ▼
   400
```

**Meaning:**

The request is invalid.

---

## 401 Unauthorized

**Meaning:**

Authentication is required.

### Example

```text
You need to log in first.
```

---

## 403 Forbidden

### Example

```text
GET /admin
     │
     ▼
403 Forbidden
```

**Meaning:**

The server understands your request but refuses access.

### Example

You're logged in as a normal user but trying to access the admin page.

---

## 404 Not Found

### Example

```text
GET /abc.html
      │
      ▼
     404
```

**Meaning:**

The requested page doesn't exist.

This is one of the most common status codes.

---

# 5xx – Server Errors ⚠️

The problem is on the server side.

---

## 500 Internal Server Error

**Meaning:**

The server encountered an unexpected problem.

---

## 502 Bad Gateway

**Meaning:**

Often happens when one server gets an invalid response from another server.

---

## 503 Service Unavailable

**Meaning:**

The server is temporarily unavailable.

**Possible reasons:**

* Maintenance
* Too much traffic
* Server overload

---

# Example Web Server Log

```text
192.168.1.15 - - [27/Jul/2026:10:15:20] "GET /index.html HTTP/1.1" 200
192.168.1.15 - - [27/Jul/2026:10:15:30] "GET /admin HTTP/1.1" 403
192.168.1.15 - - [27/Jul/2026:10:15:35] "GET /login HTTP/1.1" 200
192.168.1.15 - - [27/Jul/2026:10:15:40] "GET /secret.html HTTP/1.1" 404
```

## Let's Read It

| Request        |  Status | Meaning                  |
| -------------- | :-----: | ------------------------ |
| `/index.html`  | **200** | Page opened successfully |
| `/admin`       | **403** | Access denied            |
| `/login`       | **200** | Login page opened        |
| `/secret.html` | **404** | Page not found           |

---

# Interview Questions

### Q1. What does Port 22 do?

**Answer:**

Port **22** is used by **SSH (Secure Shell)** for secure remote login.

---

### Q2. What is the difference between Port 80 and Port 443?

**Answer:**

* **Port 80 → HTTP (Not Encrypted)**
* **Port 443 → HTTPS (Encrypted using TLS/SSL)**

---

### Q3. What does 404 mean?

**Answer:**

The requested web page or resource was **not found** on the server.

---

### Q4. What does 403 mean?

**Answer:**

The server understood the request but refused access due to **insufficient permissions**.

---

### Q5. What does 500 mean?

**Answer:**

An **Internal Server Error** occurred. The issue is on the **server side**, not the client side.

---

# Quick Cheat Sheet (Memorize)

## Important Ports

| Port  | Service |
| ----- | ------- |
| 20/21 | FTP     |
| 22    | SSH     |
| 25    | SMTP    |
| 53    | DNS     |
| 80    | HTTP    |
| 443   | HTTPS   |
| 445   | SMB     |
| 3389  | RDP     |

---

## Important HTTP Status Codes

| Code    | Meaning                       |
| ------- | ----------------------------- |
| **200** | OK (Success)                  |
| **201** | Created                       |
| **301** | Moved Permanently             |
| **302** | Temporary Redirect            |
| **400** | Bad Request                   |
| **401** | Unauthorized (Login Required) |
| **403** | Forbidden (No Permission)     |
| **404** | Not Found                     |
| **500** | Internal Server Error         |
| **502** | Bad Gateway                   |
| **503** | Service Unavailable           |
