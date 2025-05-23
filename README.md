# 🛡 Network Penetration Testing with Real-World Exploits and Security Remediation
---
## Project Overview

This project focuses on simulating real-world network exploitation and defense scenarios using common tools and methods used in the field of cybersecurity. The objective is to provide hands-on experience in identifying vulnerabilities, exploiting them, and implementing security measures to remediate the identified risks.

## 📖 Introduction

In the era of digital transformation, the security of networks and systems is of paramount importance. This project enables learners to understand and execute various penetration testing techniques in a controlled environment. By simulating attacks on vulnerable systems, the project aims to bridge the gap between theoretical knowledge and practical cybersecurity skills.

## 💡 Theory about the Project

Network penetration testing is a proactive approach to uncovering security weaknesses within a network or system before they are exploited by malicious entities. The project uses Kali Linux as the attacking machine and Metasploitable as the target machine. It includes tasks such as network scanning, enumeration, exploitation of vulnerable services, privilege escalation, password cracking, and proposing appropriate remediation strategies. The goal is to not only exploit vulnerabilities but also to understand how to secure systems effectively.



## 🚀 Project Flow -

| 🔍 Phase               | 🛠 Task                              | 💡 Description                                      |
|------------------------|-------------------------------------|-----------------------------------------------------|
| **Network Scanning**    | Basic Network Scan (`nmap -v`)      | Identify devices, IPs, and open ports on the network |
| **Reconnaissance**      | Hidden Ports Scan (`nmap -v -p-`)   | Discover hidden ports and running services          |
|                        | Service Version Detection (`-sV`)    | Find service versions on open ports                 |
|                        | OS Detection (`-O`)                  | Detect target operating system                      |
| **Enumeration**         | Information Gathering               | Collect details: OS, MAC, open & hidden ports       |
| **Exploitation**        | Service Exploitation (3 services)   | Exploit identified vulnerabilities                  |
| **Privilege Escalation**| Create Root User (`adduser`)        | Create privileged user and retrieve hash            |
| **Password Cracking**   | Crack Password (`john --show`)      | Crack password hashes using John the Ripper         |
| **Remediation**         | Research & Patch                    | Suggest updates and patches with references         |

---

## 💡 Visual Flowchart

```plaintext
[ Network Scanning ] → [ Reconnaissance ] → [ Enumeration ] → [ Exploitation ]
            ↓                  ↓                  ↓                 ↓
   Basic Scan (nmap)   Hidden Ports, OS, Service  Info Gathering  Exploit 3 Services
            ↓
[ Privilege Escalation ] → [ Password Cracking ] → [ Remediation ]
     ↓                             ↓                     ↓
 Create Root User            Crack Hashes          Recommend Fixes

```
--

## ⚙ Project Requirements

- **Operating Systems:**
  - Kali Linux (Attacking Machine)
  - Metasploitable (Target Machine)

- **Tools Used:**
  - Nmap
  - John the Ripper
  - Metasploit Framework
  - Other enumeration and exploitation tools

---
## 🌐 Network Scanning

### ✅ Task 1: Basic Network Scan

1. Open a terminal on your Kali Linux machine.
2. Run a basic scan on your local network:
   ```bash
   nmap -v YOUR_IP_RANGE

## 🔎 Reconnaissance
### ✅ Task 1: Scanning for Hidden Ports

Scan all ports on the targeted IP address:
```bash
nmap -v -p- YOUR_TARGET_IP_ADDRESS
```
### ✅ Task 2: Service Version Detection
Detect the version of services running on open ports:
```bash
nmap -v -sV YOUR_TARGET_IP_ADDRESS
```

### ✅ Task 3: Operating System Detection
Detect the operating system of target devices:
```bash
nmap -v -O YOUR_TARGET_IP_ADDRESS
```

## 📋 Enumeration
Target IP Address: ENTER_YOUR_TARGET_IP_ADDRESS

Operating System Details: ADD_YOUR_TARGET_OS_DETAILS

MAC Address: 00:0C:29:5D:FE:0B (VMware)

Device Type: General purpose

Running: Linux 2.6.X

OS CPE: cpe:/o:linux:linux_kernel:2.6

OS Details: Linux 2.6.9 - 2.6.33

### Services Version (excluding hidden ports)
| PORT   | STATE | SERVICE | VERSION                             |
| ------ | ----- | ------- | ----------------------------------- |
| 21/tcp | open  | ftp     | vsftpd 2.3.4                        |
| 22/tcp | open  | ssh     | OpenSSH 4.7p1 Debian 8ubuntu1 (2.0) |

### Hidden Ports with Service Versions
| PORT      | STATE | SERVICE  | VERSION                                        |
| --------- | ----- | -------- | ---------------------------------------------- |
| 8787/tcp  | open  | drb      | Ruby DRb RMI (Ruby 1.8; /usr/lib/ruby/1.8/drb) |
| 47436/tcp | open  | mountd   | 1-3 (RPC #100005)                              |
| 50918/tcp | open  | java-rmi | GNU Classpath grmiregistry                     |
| 59995/tcp | open  | nlockmgr | 1-4 (RPC #100021)                              |
| 60004/tcp | open  | status   | 1 (RPC #100024)                                |

## Exploitation of Services
Exploit at least 3 services from the discovered services list.

## 🔑 Create User with Root Permission

### Create a new user:
```bash
adduser your_name
```
Set a simple password (e.g., 12345, hello, 987654321).

### Get user details:
```bash
cat /etc/passwd
```

### Get password hash:
```bash
cat /etc/shadow
```

🔓 Cracking Password Hashes
Store the password hash in a text file (e.g., hashes.txt).

### Crack the hash using John the Ripper:
```bash
john hashes.txt
```
### Display the cracked password:
```bash
john hashes.txt --show
```

## 🛡 Remediation
Research vulnerabilities discovered during scanning and exploitation.

Recommend proper fixes and patches.

Provide references.

If services are outdated, include:

- Current version used in the system.
- Latest secure version for comparison.
