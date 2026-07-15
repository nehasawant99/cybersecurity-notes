#  Log Analysis Notes

## Log Types Breakdown

###  1. Authentication Logs

* **Purpose:** Records who tried to log in, when, from where, and the outcome (Success/Failure). Think of it as a computer's attendance register.
* **Examples & Parsing:**
* **Successful Login:** `Jul 27 09:00:10 sshd: Accepted password for neha from 192.168.1.10`
* *Meaning:* User `neha` successfully logged in via SSH from IP `192.168.1.10` at 09:00:10.


* **Failed Login:** `Jul 27 09:05:15 sshd: Failed password for root from 203.0.113.5`
* *Meaning:* Someone tried to log in as `root` with an incorrect password from IP `203.0.113.5`.
*  *Threat Indicator:* Potential **Brute-Force Attack**.





###  2. System Logs

* **Purpose:** Records events related to the Operating System (OS)—the computer's internal diary. Tracks boots, shutdowns, errors, driver issues, and service statuses.
* **Examples:**
* `Jul 27 08:00:01 systemd: Started Apache Web Server` $\rightarrow$ OS successfully started the Apache service.
* `Jul 27 08:05:30 Kernel: CPU Temperature High` $\rightarrow$ OS detected a hardware/thermal threshold issue.



###  3. Application Logs

* **Purpose:** Records activities, transactions, and errors specific to software applications (e.g., Chrome, databases, web servers, custom code).
* **Examples:**
* `User neha uploaded report.pdf` $\rightarrow$ Application tracked a specific user file upload.
* `Database Connection Failed` $\rightarrow$ Application error indicating a backend connection drop.



###  4. Firewall Logs

* **Purpose:** Monitors and records network traffic at the boundary. Acts like a security guard deciding to **ALLOW** or **BLOCK** connections based on rules.
* **Examples:**
* `ALLOW TCP 192.168.1.5 → 8.8.8.8 Port 443`
* *Meaning:* Internal IP `192.168.1.5` successfully established a secure web connection (HTTPS/443) to Google's DNS (`8.8.8.8`).


* `BLOCK TCP 185.20.10.15 → 192.168.1.20 Port 22`
* *Meaning:* An inbound SSH (`Port 22`) request from an external IP was dropped by the firewall.
*  *Threat Indicator:* Unauthorised access attempt or SSH scanning.





###  5. Web Server Logs

* **Purpose:** Records every inbound HTTP request made to a hosted website—a visitor book for the web server.
* **Examples:**
* `192.168.1.15 - - [27/Jul/2026:10:15:20] "GET /index.html HTTP/1.1" 200`
* *Meaning:* Visitor requested the home page; server responded with `200 OK` (Success).


* `GET /admin 403`
* *Meaning:* A user tried to open the administration panel; server responded with `403 Forbidden`.
* *Analyst Note:* Investigate if this is reconnaissance/directory brute-forcing.





###  6. Antivirus Logs

* **Purpose:** Records malware detections, file scans, and mitigation actions taken by endpoint security tools.
* **Examples:**
* `Threat Detected: Trojan.Win32 | Action: Quarantined` $\rightarrow$ Malicious file isolated before execution.
* `File: invoice.pdf.exe | Action: Deleted`
*  *Threat Indicator:* The file uses a **double extension** (`.pdf.exe`) to trick users into running an executable masquerading as a PDF.





###  7. DNS Logs

* **Purpose:** Records domain name resolutions (converting website names to IP addresses). The internet's phonebook requests.
* **Examples:**
* `Laptop01 → google.com` $\rightarrow$ Normal business traffic querying a standard domain.
* `Laptop01 → freegift-malware.xyz`
*  *Threat Indicator:* Command and Control (C2) callback or malicious redirection.
*  *Analyst Action:* Cross-reference domain with Threat Intel (e.g., VirusTotal).





###  8. Proxy Logs

* **Purpose:** Records outbound web traffic passing through the organisation’s network exit point. Used for URL filtering and compliance checks.
* **Examples:**
* `User: Neha | Visited: github.com` $\rightarrow$ Normal development activity.
* `User: Neha | Visited: free-movies-download.xyz`
*  *Risk:* High probability of hosting malware, phishing kits, or violating company policy.





###  9. VPN Logs

* **Purpose:** Records remote connection attempts to the internal corporate network.
* **Examples:**
* `User: Neha | Connected | Mumbai | 09:00 AM` $\rightarrow$ Normal remote work scenario.
* `User: Neha | Connected | London | 09:10 AM`
*  *Threat Indicator:* **Impossible Travel**. A single user cannot physically travel from Mumbai to London in 10 minutes. Indicates compromised credentials or account sharing.




---

##  2. Log Correlation & Incident Timeline

A SOC analyst rarely looks at a single log source. Security incidents are reconstructed by stitching different log files together chronologically to tell a complete story.

### Case Study: Chronological Incident Timeline

| Time | Log Type | Event Description | Analyst Assessment |
| --- | --- | --- | --- |
| **09:00** | Authentication | 5 failed logins from `185.20.10.15` | Brute-force attempt underway. |
| **09:02** | Authentication | Successful login from same IP | Account compromised (Breach). |
| **09:05** | DNS | User queries `malicious-update.xyz` | Attacker trying to fetch tools. |
| **09:06** | Proxy | Browser accesses `malicious-update.xyz` | Payloads downloading to endpoint. |
| **09:07** | Antivirus | `Trojan` detected and quarantined | Endpoint defense handles payload. |
| **09:08** | Firewall | Outbound connection blocked | C2 beacon blocked by boundary rules. |
| **09:10** | **SOC Analyst** | **Incident Escalated** | Containment and remediation initiated. |

---

##  3. The Analyst's Checklist 

When analysing any correlated security event, always answer the following foundational questions:

* **What** happened? (What was the attack vector?)
* **When** did it happen? (Establish an accurate timeline)
* **Who** was involved? (Targeted usernames, source IPs, malicious actors)
* **Which** systems were affected? (Identify the blast radius)
* **Is it malicious** or normal activity? (Rule out false positives)
* **What next?** (Isolate the host, reset credentials, update firewall rules)
