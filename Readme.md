# 🔐 End-to-End Penetration Testing Lab: Multi-Vector Attack Simulation

## 📌 Overview
This project demonstrates a complete end-to-end penetration testing workflow using Kali Linux against a vulnerable machine (Metasploitable 2). The objective was to simulate real-world attack scenarios in a controlled lab environment by identifying vulnerabilities, exploiting them, and performing post-exploitation analysis across multiple attack vectors.

---

## 🎯 Objectives
- Perform network scanning and service enumeration  
- Identify vulnerable services and versions  
- Exploit vulnerabilities using Metasploit  
- Perform web application attacks (SQL Injection)  
- Gain root-level access  
- Conduct post-exploitation and extract sensitive data  

---

## 🧪 Lab Setup
- Attacker Machine: Kali Linux  
- Target Machine: Metasploitable 2  
- Virtualization Platform: VMware Workstation  
- Network Configuration: Host-Only / NAT  

---

## 🔍 Scanning & Enumeration
Command used:
nmap -A -T4 <target-ip>

### Key Findings:
- FTP (vsftpd 2.3.4)  
- SMB (Samba 3.0.20)  
- HTTP (Apache)  

---

## 💣 Exploitation

### FTP Exploit (VSFTPD)
Exploit:
exploit/unix/ftp/vsftpd_234_backdoor

Result:
- Root shell access  

---

### SMB Exploit (Samba)
Exploit:
exploit/multi/samba/usermap_script

Result:
- Remote command execution  
- Root access  

---

### Web SQL Injection
Payload:
1' OR '1'='1

Result:
- Authentication bypass  
- Data extraction  

---

## 💻 Post Exploitation
Commands used:
whoami  
uname -a  
cat /etc/passwd  

---

## ⚠ Vulnerabilities Identified
- VSFTPD Backdoor  
- Samba CVE-2007-2447  
- SQL Injection  

---

## 🛡 Mitigation
- Update vulnerable services  
- Use input validation  
- Restrict access  

---

## 📊 Impact
- Full system compromise  
- Root access  
- Sensitive data exposure  

---

## 🛠 Tools Used
- Kali Linux  
- Nmap  
- Metasploit  
- DVWA  

---

## ⚠ Disclaimer
This project was performed in a controlled lab environment for educational purposes only.
