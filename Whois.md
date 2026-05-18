# 🌐 WHOIS Complete Guide (Beginner → Advanced)

---

# 📌 What is WHOIS?

WHOIS is a tool used to get information about:

* Domain owners
* Registrar details
* Name servers
* Registration & expiry dates
* IP ownership

It helps in:

* Cybersecurity investigations
* OSINT (Open Source Intelligence)
* Reconnaissance
* Bug bounty hunting

---

# ⚙️ Installation

## 🐧 Linux (Kali / Ubuntu)

```bash
sudo apt update
sudo apt install whois -y
```

## 🪟 Windows

Download WHOIS tools from:

https://learn.microsoft.com/en-us/sysinternals/downloads/whois

---

# 🚀 First WHOIS Lookup

```bash
whois google.com
```

---

# 🔍 Understanding Output

## Important Fields

### 🔹 Domain Name

```text
Domain Name: GOOGLE.COM
```

👉 Target domain name

---

### 🔹 Registrar

```text
Registrar: MarkMonitor Inc.
```

👉 Company managing the domain

---

### 🔹 Creation Date

```text
Creation Date: 1997-09-15
```

👉 When domain was registered

---

### 🔹 Expiry Date

```text
Registry Expiry Date: 2028-09-14
```

👉 Domain expiration date

---

### 🔹 Name Servers

```text
Name Server: NS1.GOOGLE.COM
```

👉 DNS servers used by the domain

---

# ❌ Common Error & Fix

## Error:

```bash
whois: command not found
```

## Solution:

```bash
sudo apt install whois -y
```

---

## Error:

```bash
connect: Network is unreachable
```

## Fix:

Check internet connection:

```bash
ping google.com
```

---

# 🎯 Basic WHOIS Commands

## 🔹 Lookup a Domain

```bash
whois example.com
```

---

## 🔹 Lookup an IP Address

```bash
whois 8.8.8.8
```

👉 Finds ISP / organization details

---

## 🔹 Save Output to File

```bash
whois google.com > whois.txt
```

---

# 🔍 Useful Information for Students

WHOIS helps students learn:

* Domain investigation
* Website ownership tracking
* Cyber reconnaissance
* OSINT basics

---

# 🧠 Real-World Use Cases

## 🔹 Bug Bounty

Find:

* Hosting provider
* Contact emails
* Related infrastructure

---

## 🔹 Cybersecurity

Identify:

* Suspicious domains
* Fake websites
* Registrar information

---

## 🔹 OSINT Investigation

Track:

* Domain history
* Organization ownership
* IP ranges

---

# ⚡ WHOIS with IP Addresses

## Example

```bash
whois 1.1.1.1
```

### Output May Show:

* ISP name
* Country
* Organization
* CIDR range

---

# 🔥 Important WHOIS Tips

* WHOIS does NOT hack anything
* It is completely legal for public information
* Some domains use privacy protection
* WHOIS is great for reconnaissance

---

# 🛡️ Privacy Protection

Sometimes output shows:

```text
Registrant Organization: REDACTED FOR PRIVACY
```

👉 Owner details are hidden using privacy protection services

---

# ⚡ Combine WHOIS with Other Tools

## 🔹 WHOIS + NSLOOKUP

```bash
whois example.com
nslookup example.com
```

---

## 🔹 WHOIS + Nmap

```bash
whois example.com
nmap example.com
```

👉 Great for learning reconnaissance workflow

---

# 🧪 Student Practice Targets

Use legal targets for practice:

```bash
whois google.com
whois github.com
whois cloudflare.com
```

---

# ❌ Common Beginner Mistake

## Mistake:

Thinking WHOIS gives passwords or sensitive data

## Reality:

WHOIS only provides public registration information

---

# 💾 Save Clean Output

```bash
whois google.com | tee output.txt
```

👉 Shows output and saves file together

---

# 🧠 Simple Learning Workflow

## Step 1: Get domain info

```bash
whois example.com
```

## Step 2: Find DNS info

```bash
nslookup example.com
```

## Step 3: Scan open ports

```bash
nmap example.com
```

---

# 🔥 Example Recon Workflow

```bash
whois target.com
nslookup target.com
nmap -sV target.com
```

---

# ⚠️ Legal Disclaimer

Use WHOIS only for:

* Learning
* Authorized investigations
* Ethical security research

---

# 🎯 Conclusion

WHOIS is one of the easiest and most important tools for beginners in cybersecurity.

Learning WHOIS helps in:

* OSINT
* Reconnaissance
* Bug bounty
* Cyber investigations

---

🔥 Happy Learning!
