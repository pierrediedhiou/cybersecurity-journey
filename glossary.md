# Cybersecurity Glossary

## A
- **Active Directory** — Centralized repository to store credentials and
manage users and devices on a network
- **ADDS** — Active Directory Domain Service, the main Active Directory service
- **AES** — Advanced Encryption Standard, a widely used encryption algorithm
- **ASCII** — American Standard Code for Information Interchange, the most
basic text format for plain readable text files

## B
- **Bash** (Bourne Again Shell) — Most common shell on Linux, default on Kali Linux
- **Bind Shell** — Shell that listens on a port on the target waiting for attacker
- **Burp Suite** — Popular web security testing tool used to intercept web traffic

## C
- **cat** — Linux command meaning concatenate, used to display file contents
- **Censys** — Search engine for Internet-connected hosts, websites, certificates,
and other Internet assets
- **chmod** — Linux command to change file permissions
- **CIA Triad** — Confidentiality, Integrity, Availability — core security principles
- **CLI** — Command-Line Interface, text-based interface to interact with
a computer
- **Cookie** — Small data stored in a browser to maintain sessions
- **Crontab** — Special file used by the cron process to schedule automated
tasks at specified times
- **CSRF** — Cross-Site Request Forgery, tricks users into performing unwanted actions
- **CTF** — Capture The Flag, a cybersecurity competition to practice hacking skills
- **CVE** — Common Vulnerabilities and Exposures, a standardized ID for known
vulnerabilities (ex: CVE-2024-3094)

## D
- **Daemon** — A background service running on Linux
- **Delegation** — Process of granting privileges to a user over an OU
or other Active Directory object
- **Directory** — A container (folder) that organizes and stores files
  - Examples: /home/tryhackme/ | /var/log/
- **Domain Controller** — Server in charge of running Active Directory services

## E
- **Encryption** — Process of encoding data so only authorized parties can read it
- **Enumeration** — Systematically gathering information about a target system
- **Exploit** — Code or technique that takes advantage of a vulnerability

## F
- **File** — A unit of stored data (text, code, image, config, etc).
Everything in Linux is technically a file
  - Examples: /etc/passwd | flag.txt | /var/log/auth.log
- **Firewall** — Security system that monitors and controls network traffic
- **Fish** — User friendly Linux shell with autocompletion features
- **FTP** — File Transfer Protocol, used to transfer files over a network (Port 21)

## G
- **GPO** — Group Policy Objects, collection of settings applied to
Organizational Units in Active Directory
- **GUI** — Graphical User Interface, visual interface for interacting
with a computer

## H
- **Hash** — A fixed-length string generated from data, used to verify integrity
- **Have I Been Pwned** — Tool that tells you if an email address has appeared
in a leaked data breach
- **Heartbleed** — Critical OpenSSL vulnerability (CVE-2014-0160) that leaked
server memory
- **Honeypot** — A decoy system designed to attract and detect attackers

## I
- **Injection** — Attack inserting malicious code into an input field
- **IP Address** — Internet Protocol Address, a unique numerical label assigned
to every device on a network
- **ipconfig** — Windows command for Internet Protocol Configuration, shows
network information. Full path: C:\Windows\System32\ipconfig.exe
- **IPv4** — Internet Protocol version 4, format: 192.168.0.18
- **IPv6** — Internet Protocol version 6, format: 2a02:a31a:a4b8:7800:...
- **ISP** — Internet Service Provider, the company providing your internet connection

## K
- **KDC** — Key Distribution Center, service installed on the Domain
Controller that creates Kerberos tickets on the network

## L
- **Linux Distributions** — Different versions of Linux built for different purposes:
  - **General Purpose:** Ubuntu | Debian | Fedora | Linux Mint
  - **Cybersecurity:** Kali Linux | Parrot OS | BlackArch | REMnux
  - **Server/Enterprise:** CentOS | RHEL | Alpine Linux
- **Localhost** — The IP address 127.0.0.1, always refers to your own machine

## M
- **Machine Account** — Windows computer account, always ends with $ symbol
- **Malware** — Malicious software designed to damage or gain unauthorized access
- **Meterpreter** — Advanced shell built into Metasploit, runs in memory
- **Metasploit** — Popular penetration testing framework for exploiting vulnerabilities
- **MITM** — Man In The Middle attack, intercepting communication between
two parties

## N
- **NAT** — Network Address Translation, maps private IPs to a public IP
- **Nmap** — Network scanning tool used to discover open ports and services
- **NTFS** — New Technology File System, the standard file system used by Windows

## O
- **Open Port** — A port actively accepting connections on a device
- **OpenSSL** — Cryptographic library that powers HTTPS encryption
- **OSI Model** — 7-layer framework describing how data travels over a network
- **OUs** — Organizational Units, container objects in Active Directory
used to classify users and machines

## P
- **Packet** — Small unit of data transmitted over a network
- **Patch** — A software update that fixes a security vulnerability
- **Payload** — Malicious code delivered to a target during an attack
- **Pentest** — Penetration Test, an authorized simulated attack on a system
- **Phishing** — A social engineering attack using fake emails to steal credentials
- **Ping** — Command to test if a host is reachable on a network
- **Port** — A virtual endpoint for network communication
- **PowerShell** — Advanced Windows shell, widely used by admins and attackers
- **Privilege Escalation** — Gaining higher access than originally permitted
- **Process** — A program that is currently running in memory, each with a
unique PID (Process ID). Temporary, disappears when the program stops
  - Commands: ps aux (view) | kill PID (terminate)
- **Protocol** — A set of rules for communication between devices

## R
- **Ransomware** — Malware that encrypts files and demands payment for decryption
- **RCE** — Remote Code Execution, running code on a target system remotely
- **RDP** — Remote Desktop Protocol, allows graphical remote access to Windows
machines (Port 3389)
- **Reconnaissance** — Information gathering phase before an attack
- **Reverse Shell** — Shell sent from target back to attacker giving remote control
- **Root** — The highest privilege user in Linux, like admin on Windows
- **RPC** — Remote Procedure Call, allows programs to request services from
other programs on a network
- **RPCSS** — Remote Procedure Call Subsystem, Windows service running on Port 135
- **rwx** — Read, Write, Execute — Linux file permissions:
  - r (Read) = 4
  - w (Write) = 2
  - x (Execute) = 1
  - Example: rwx = 4+2+1 = 7

## S
- **Service** — A process that runs continuously in the background, starts
automatically at boot, runs without user interaction
  - Examples: SSH server | Web server | Database server
  - Commands: systemctl start/stop/status servicename
- **Session Token** — A unique ID used to authenticate a logged-in user
- **Shell** — Interface between the user and the operating system that
interprets and executes commands
- **Shellcode** — Small piece of code used as a payload in exploitation
- **Shells (Common Types):**
  - **Bash** — Most common on Linux, default on Kali
  - **Zsh** — Default on modern Macs, similar to Bash
  - **sh** — The original Unix shell, lightweight and basic
  - **Fish** — User friendly shell with autocompletion
  - **cmd.exe** — Basic Windows command-line interpreter
  - **PowerShell** — Advanced Windows shell
  - **Web Shell** — Malicious script giving browser-based shell access
  - **Meterpreter** — Advanced shell built into Metasploit
  - How to check current shell — Linux/Mac: echo $0 | Windows: echo %COMSPEC%
- **Shodan** — Search engine for devices connected to the Internet
- **SMB** — Server Message Block, Windows file sharing protocol (Port 445)
- **Snake Oil** — Bogus or fraudulent cryptographic product or method
- **SPN** — Service Principal Name, indicates the service and server name
to access
- **SQL Injection** — Attack inserting SQL code into a database query
- **SSH** — Secure Shell, a protocol for securely connecting to remote computers
(Port 22)
- **Sudo** — Command that grants temporary root privileges
- **Sysmon** — System Monitor, part of Microsoft Sysinternals Suite, monitors
and logs system activity to the Windows Event Log
- **Sysinternals** — Microsoft toolkit for monitoring and managing Windows systems
- **SYSVOL** — Network share used to distribute GPOs to domain machines

## T
- **Telnet** — Insecure remote access protocol (Port 23), replaced by SSH
- **TGT** — Ticket Granting Ticket, allows users to request tickets to
access specific services, encrypted using the krbtgt account password hash
- **TPM** — Trusted Platform Module, hardware security chip on Windows
- **Tree** — Group of Windows domains sharing the same namespace
- **Trojan** — Malware disguised as legitimate software
- **Trust Relationship** — Administrative and communication link between
two domains allowing authentication and authorization across domains
- **Two-Factor Authentication (2FA)** — Security method requiring two forms
of verification

## U
- **UAC** — User Account Control, Windows security feature that controls
administrative privileges

## V
- **VirusTotal** — Virus-scanning service that scans files and URLs against
multiple antivirus engines and website scanners in a single operation
- **VPN** — Virtual Private Network, encrypts internet traffic and hides your
real public IP address
- **VSS** — Volume Shadow Copy Service, Windows service for backup and
restore of files
- **Vulnerability** — A weakness in a system that can be exploited

## W
- **Web Shell** — Malicious script uploaded to a web server giving
browser-based shell access

## X
- **XSS** — Cross-Site Scripting, injecting malicious scripts into web pages
- **XZ Utils** — Linux compression tool targeted by a supply chain attack
(CVE-2024-3094)

## Z
- **Zero-Day** — A vulnerability unknown to the software vendor with no
available patch
- **Zsh** (Z Shell) — Default shell on modern Macs, similar to Bash

## Linux Filesystem Reference
| Directory | Description |
|-----------|-------------|
| `/etc` | System configuration files |
| `/var` | Variable data, frequently changing files |
| `/root` | Home directory for the root user |
| `/tmp` | Temporary files, cleared on restart |
| `/var/log` | All Linux system log files |

## Common Ports Reference
| Port | Service | Description |
|------|---------|-------------|
| 21 | FTP | File Transfer Protocol |
| 22 | SSH | Secure Shell |
| 23 | Telnet | Insecure remote access |
| 80 | HTTP | Web traffic |
| 135 | RPCSS | Windows Remote Procedure Call |
| 443 | HTTPS | Secure web traffic |
| 445 | SMB | Windows file sharing |
| 3389 | RDP | Remote Desktop Protocol |

## Linux File Commands Reference
- `echo "password123" > passwords` — Overwrites the file "passwords" with
"password123"
- `echo "tryhackme" >> passwords` — Appends "tryhackme" to the file "passwords"
while keeping existing content

## Windows Command Line Reference
- `cmd.exe` — Default command-line interpreter in Windows
- `cls` — Clear the Command Prompt screen
- `help` — Get help information for a specific command
- `ipconfig` — Check network information (IP address, subnet mask, gateway)
- `ipconfig /all` — Look up detailed network info including physical MAC address
- `more` — Display long output one page at a time
- `netstat` — Display current network connections and listening ports
- `netstat -h` — Display the netstat help page
- `nslookup` — Look up a host or domain and return its IP address
- `ping target_name` — Check if a host is reachable on the network
- `set` — Check your system path from the command line
- `systeminfo` — List system information including OS, processor and memory
- `tracert target_name` — Trace the network route to reach a target
- `ver` — Determine the Windows operating system version
