### **# Practice 1: Failed Login**

```text
Jul 27 08:10:01 sshd: Failed password for root from 203.0.113.5
Jul 27 08:10:05 sshd: Failed password for root from 203.0.113.5
Jul 27 08:10:10 sshd: Failed password for root from 203.0.113.5

```

#### **Questions & Answers:**

* **Which IP is suspicious?**
* `203.0.113.5`


* **Which account is being targeted?**
* `root`


* **What attack does this resemble?**
* It's a brute force attack trying to log in to the system.


* **What would you investigate next?**
* Check the log activity and the user activity. If I find something suspicious toward the IP, I would inform the lead and document it.



---

### **# Practice 2: Password Spraying**

```text
Jul 27 09:00:01 sshd: Failed password for alice from 203.0.113.20
Jul 27 09:00:03 sshd: Failed password for bob from 203.0.113.20
Jul 27 09:00:05 sshd: Failed password for admin from 203.0.113.20
Jul 27 09:00:07 sshd: Failed password for guest from 203.0.113.20

```

#### **Questions & Answers:**

* **What attack is this?**
* Password spraying, where the attacker's IP remains the same while trying to guess passwords across multiple accounts.


* **Why is it different from brute force?**
* In brute force, the attacker tries to guess one specific account's password. In password spraying, they try to target multiple accounts using a common list of passwords; if successful, it is a jackpot for the attacker and a major compromise for the system.



---

### **# Practice 3: DNS Logs**

```text
Laptop01 queried google.com
Laptop01 queried microsoft.com
Laptop01 queried abc123-malware.xyz

```

#### **Questions & Answers:**

* **Which domain is suspicious?**
* The domain `abc123-malware.xyz` queried by `Laptop01` is suspicious.


* **What would you check?**
* Check the domain link on VirusTotal to verify if it is safe or not.


* **Which threat intelligence source could help?**
* VirusTotal and reputation check tools, as unsafe websites or redirected pages can compromise the device or system.
