# 🔍 Nmap Complete Guide (Beginner → Advanced)

---

# 📌 What is Nmap?

Nmap (Network Mapper) is a powerful open-source tool used for:

* Network discovery
* Port scanning
* Service & version detection
* OS fingerprinting
* Security testing

---

# ⚙️ Installation

## 🐧 Linux (Kali / Ubuntu)

```bash
sudo apt update
sudo apt install nmap -y
```

## 🪟 Windows

Download: https://nmap.org/download.html

---

# 🚀 First Scan (Start Here)

```bash
nmap 192.168.1.1
```

### 🔍 Output Meaning:

* **PORT** → Open ports
* **STATE** → open / closed / filtered
* **SERVICE** → running service (http, ssh, ftp)

---

# ❌ Common Error & Fix

## Error:

```bash
nmap: command not found
```

## Solution:

```bash
sudo apt install nmap -y
```

---

## Error:

```bash
WARNING: Host seems down
```

## Solution:

```bash
nmap -Pn <target>
```

👉 Skips ping check (useful in CTFs)

---

## Error:

```bash
You requested a scan type which requires root privileges
```

## Solution:

```bash
sudo nmap <target>
```

---

# 🎯 Port Scanning

## 🔹 Scan specific ports

```bash
nmap -p 80,443 192.168.1.1
```

## 🔹 Scan all ports (IMPORTANT)

```bash
nmap -p- 192.168.1.1
```

👉 `-p-` = scan all 65535 ports

---

# ⚡ Scan Types

## 🔹 TCP Connect Scan

```bash
nmap -sT <target>
```

## 🔹 SYN Scan (Stealth)

```bash
sudo nmap -sS <target>
```

## 🔹 UDP Scan

```bash
sudo nmap -sU <target>
```

---

# ❌ Error (UDP Scan Slow)

## Problem:

UDP scan takes too long

## Fix:

```bash
sudo nmap -sU --top-ports 100 <target>
```

---

# 🔍 Service & Version Detection

```bash
nmap -sV <target>
```

👉 Finds:

* Software version
* Helps in finding exploits

---

# 🧠 OS Detection

```bash
sudo nmap -O <target>
```

---

# ⚡ Aggressive Scan (All-in-One)

```bash
sudo nmap -A <target>
```

👉 Includes:

* OS detection
* Version detection
* Script scanning

---

# ❌ Error (Slow Scan)

## Fix:

```bash
nmap -T4 <target>
```

👉 Faster scanning

---

# 🧪 NSE (Nmap Scripting Engine)

## 🔹 Default scripts

```bash
nmap -sC <target>
```

## 🔹 Run vulnerability scripts

```bash
nmap --script vuln <target>
```

## 🔹 Example

```bash
nmap --script http-title <target>
```

---

# ❌ Error (Script Not Found)

## Fix:

```bash
ls /usr/share/nmap/scripts/
```

👉 Check available scripts

---

# 📡 Host Discovery

```bash
nmap -sn 192.168.1.0/24
```

👉 Finds live hosts only

---

# 💾 Save Output

```bash
nmap -oN scan.txt <target>
```

---

# ❌ Error (Permission Denied Saving File)

## Fix:

```bash
sudo nmap -oN /root/scan.txt <target>
```

---

# 🧠 Real-World Workflow (CTF / TryHackMe)

## Step 1: Scan all ports

```bash
nmap -p- -T4 <target>
```

## Step 2: Service detection

```bash
nmap -sV -p <ports> <target>
```

## Step 3: Run scripts

```bash
nmap -sC -sV <target>
```

---

# 🔥 Example (Full Attack Flow)

```bash
nmap -p- -T4 10.10.10.10
nmap -sC -sV 10.10.10.10
```

---

# ⚡ Pro Tips

* Always scan all ports first
* Use `-T4` for speed
* Use `-Pn` if host not responding
* Combine commands:

```bash
nmap -sC -sV -p- -T4 <target>
```

---

# ⚠️ Legal Disclaimer

Use only on authorized systems.

---

# 🎯 Conclusion

Nmap is the **most important tool in cybersecurity**.
Mastering it will help you in:

* CTFs
* Bug bounty
* Penetration testing

---

🔥 Happy Hacking!
