# Cybersecurity Glossary

## A
- **Active Directory** — Centralized repository to store credentials and
manage users and devices on a network
- **ADDS** — Active Directory Domain Service, the main Active Directory service
- **AES** — Advanced Encryption Standard, a widely used encryption algorithm
- **ASCII** — American Standard Code for Information Interchange, the most
basic text format for plain readable text files
- **ASCII** (in networking context) — Human readable text format used
to display packet data in tools like tcpdump and Wireshark
- **AES** — Advanced Encryption Standard, adopted in 2001, key sizes
of 128, 192 or 256 bits. Current industry standard for symmetric
encryption
- **Asymmetric Encryption** — Encryption that uses two keys: a public
key (shared with everyone) and a private key (kept secret). Examples:
RSA, Diffie-Hellman, ECC
- **Amazon S3 Bucket** — A cloud storage container on Amazon Web
Services. Misconfigured S3 buckets are a common security vulnerability
that can expose sensitive data publicly
## B
- **Bash** (Bourne Again Shell) — Most common shell on Linux, default on Kali Linux
- **Bind Shell** — Shell that listens on a port on the target waiting for attacker
- **Burp Suite** — Popular web security testing tool used to intercept web traffic
- **Brute-Force Attack** — Attack method that tries every possible
key or password combination until the correct one is found
- **bcrypt** — A password hashing function based on the Blowfish
cipher, commonly used on OpenBSD, FreeBSD and Linux systems.
Prefix: $2b$, $2y$, $2a$
- **Boolean** — A data type that can only be true or false,
used in conditions and control flow in programming
- **Burp Suite** — A Java-based web application penetration testing
framework that intercepts, inspects and modifies HTTP/HTTPS traffic
between a browser and web server. Key tools include Proxy, Repeater,
Intruder, Decoder, Comparer and Sequencer
- **Brute Force Attack** — An attack method that systematically tries
every possible combination of credentials until the correct one is
found
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
- **Cipher** — An algorithm or method used to convert plaintext into
ciphertext and back. Usually developed by a mathematician
- **Ciphertext** — The scrambled, unreadable version of a message
after encryption. No information about the original plaintext should
be recoverable without the key
- **Cryptography** — The practice and study of techniques for secure
communication and data protection in the presence of adversaries
- **Cryptanalysis** — The study of methods to break or bypass
cryptographic security systems without knowing the key
- **CIDR** — Classless Inter-Domain Routing, a notation for specifying
IP address ranges (ex: 192.168.0.0/24 covers 256 addresses)
- **Concurrency** — In Metasploit, the number of targets being scanned
simultaneously during a scan module
- **CSS** — Cascading Style Sheets, describes the visual appearance
of a web application including colors, fonts and layouts
- **CSP** — Content Security Policy, an HTTP security header that
helps prevent XSS attacks by controlling where resources can be
loaded from
- **Control Flow** — The order in which code is executed in a
program, controlled by conditions (if-else, switch) and loops
(for, while, do...while)
- **Comparer** — A Burp Suite tool that compares two pieces of data
at word or byte level to identify differences
- **CNAME Record** — Canonical Name DNS record, maps one domain name
to another domain name
## D
- **Daemon** — A background service running on Linux
- **Delegation** — Process of granting privileges to a user over an OU
or other Active Directory object
- **Directory** — A container (folder) that organizes and stores files
  - Examples: /home/tryhackme/ | /var/log/
- **Domain Controller** — Server in charge of running Active Directory services
- **Decryption** — The reverse process of encryption, converting
ciphertext back into plaintext using a cipher and a key
- **DES** — Data Encryption Standard, adopted in 1977, uses a 56-bit
key. Broken in under 24 hours in 1999, now deprecated
- **Diffie-Hellman** — Asymmetric key exchange protocol that allows
two parties to establish a shared secret over an insecure channel
- **Dictionary Attack** — Attack method where the attacker tries
common dictionary words or combinations to guess a password or key
- **Diffie-Hellman** — Key exchange protocol that establishes a shared
secret between two parties over an insecure channel
- **Digital Signature** — A cryptographic method to verify the
authenticity and integrity of a message or document
- **DSA** — Digital Signature Algorithm, a public-key cryptography
algorithm specifically designed for digital signatures
- **Digest** — Another name for a hash value, the fixed-size output
produced by a hash function
- **Database** — A structured system for storing, modifying and
retrieving information used by web applications
- **Decoder** — A Burp Suite tool used to decode captured data or
encode payloads before sending them to a target
- **DNS Subdomain** — A prefix added to a domain name to create a
separate section of a website (ex: admin.example.com,
mail.example.com). Enumerating subdomains can reveal hidden services
## E
- **Encryption** — Process of encoding data so only authorized parties can read it
- **Enumeration** — Systematically gathering information about a target system
- **Exploit** — Code or technique that takes advantage of a vulnerability
- **ECC** — Elliptic Curve Cryptography, a form of asymmetric
encryption that provides strong security with smaller key sizes
- **Encryption** — The process of converting plaintext into ciphertext
using a cipher and a key. The cipher is public but the key is secret
- **ECDSA** — Elliptic Curve Digital Signature Algorithm, a variant
of DSA that uses elliptic curve cryptography for smaller key sizes
with equivalent security
- **ECDSA-SK** — ECDSA with Security Key, extends ECDSA by using
hardware-based security keys for enhanced private key protection
- **Ed25519** — A public-key signature system using EdDSA with
Curve25519, modern, fast and highly secure
- **Ed25519-SK** — Ed25519 with Security Key, uses hardware-based
security keys for improved private key protection
- **EdDSA** — Edwards-curve Digital Signature Algorithm, the algorithm
used by Ed25519
- **Encoding** — The process of converting data from one form to
another to make it compatible with a specific system. Reversible
without a key (ex: Base64, URL encoding)
- **Exploit** — A piece of code that takes advantage of a vulnerability
present on a target system to gain access or cause unintended behavior
- **Enumeration** — The act of systematically listing all available
resources on a target, whether accessible or not. A key phase in
penetration testing and CTF challenges
## F
- **File** — A unit of stored data (text, code, image, config, etc).
Everything in Linux is technically a file
  - Examples: /etc/passwd | flag.txt | /var/log/auth.log
- **Firewall** — Security system that monitors and controls network traffic
- **Fish** — User friendly Linux shell with autocompletion features
- **FTP** — File Transfer Protocol, used to transfer files over a network (Port 21)
- **Fragment** — The part of a URL starting with # that points to
a specific section of a webpage
- **Function** — A reusable block of code designed to perform a
specific task. Called by name whenever that task needs to be done
- **Fuzzing** — A testing technique that sends large amounts of
random or unexpected data to an application to discover
vulnerabilities or unexpected behavior
## G
- **GPO** — Group Policy Objects, collection of settings applied to
Organizational Units in Active Directory
- **GUI** — Graphical User Interface, visual interface for interacting
with a computer
- **Get-Command** — PowerShell cmdlet to list all available commands,
functions and aliases in the current session
- **Get-Content** — PowerShell cmdlet to read and display file contents,
similar to cat in Linux
- **GPG** — GNU Privacy Guard, an open-source implementation of the
OpenPGP standard used for encrypting and signing data
- **GnuPG** — Another name for GPG (GNU Privacy Guard)
- **GPU** — Graphics Processing Unit, specialized hardware originally
for image processing, also widely used for password cracking due to
its ability to perform massive parallel computations
- **GUID** — Globally Unique Identifier, a unique reference number
used to identify a Meterpreter session or object
- **getsystem** — Meterpreter command that attempts to automatically
escalate privileges to SYSTEM level on a Windows target
- **Gobuster** — An open-source offensive enumeration tool written
in Golang, used to brute force web directories, DNS subdomains,
virtual hosts and cloud storage buckets using wordlists
## H
- **Hash** — A fixed-length string generated from data, used to verify integrity
- **Have I Been Pwned** — Tool that tells you if an email address has appeared
in a leaked data breach
- **Heartbleed** — Critical OpenSSL vulnerability (CVE-2014-0160) that leaked
server memory
- **Honeypot** — A decoy system designed to attract and detect attackers
- **Hex (Hexadecimal)** — Base-16 number system used to display raw
packet data in network analysis tools
- **Hash Collision** — When two different inputs produce the same
hash output. Considered a weakness in a hash function
- **Hash Function** — A function that takes input data of any size
and produces a fixed-size output called a hash value or digest
- **Hash Value** — A fixed-size string of characters computed by a
hash function from an input of any size
- **Hashcat** — A popular password cracking tool that uses wordlists
and hash types to recover plaintext passwords
- **HMAC** — Keyed-Hash Message Authentication Code, uses a
cryptographic hash function combined with a secret key to verify
the authenticity and integrity of data
- **hashdump** — Meterpreter command that extracts password hashes
from the Windows SAM database for offline cracking
- **HTML** — Hypertext Markup Language, the foundational language
that instructs web browsers what to display and how to display it
- **HSTS** — HTTP Strict Transport Security, a header that forces
browsers to always connect over HTTPS
- **Hydra** — A fast online brute force password cracking tool used
to attack login forms, SSH, FTP and other authentication services
## I
- **Injection** — Attack inserting malicious code into an input field
- **IP Address** — Internet Protocol Address, a unique numerical label assigned
to every device on a network
- **ipconfig** — Windows command for Internet Protocol Configuration, shows
network information. Full path: C:\Windows\System32\ipconfig.exe
- **IPv4** — Internet Protocol version 4, format: 192.168.0.18
- **IPv6** — Internet Protocol version 6, format: 2a02:a31a:a4b8:7800:...
- **ISP** — Internet Service Provider, the company providing your internet connection
- **Invoke-Command** — PowerShell cmdlet for executing commands on remote
systems, used by admins and penetration testers alike
- **Intruder** — A Burp Suite tool used to automate customized
attacks against web applications, commonly used for brute forcing
and fuzzing endpoints
## J
- **John the Ripper** — Free open source password cracking tool that
automatically detects hash types and supports wordlist, single and
brute force attack modes. Pre-installed on Kali Linux
- **Jumbo John** — The most popular extended version of John the
Ripper with additional hash support and features
- **JavaScript (JS)** — A programming language that enables complex
interactive behavior in web browsers, part of the web front end
- **JavaScript (JS)** — A popular scripting language that adds
interactive features to websites alongside HTML and CSS. Runs in
the browser (front end) and can also run on servers (Node.js)
## K
- **KDC** — Key Distribution Center, service installed on the Domain
Controller that creates Kerberos tickets on the network
- **Key** — A string of bits used by a cipher to encrypt or decrypt
data. Must remain secret (except for public keys in asymmetric
encryption)
- **Keylogger** — A tool or technique that records keystrokes on a
target system. In Meterpreter: keyscan_start, keyscan_dump,
keyscan_stop
## L
- **Linux Distributions** — Different versions of Linux built for different purposes:
  - **General Purpose:** Ubuntu | Debian | Fedora | Linux Mint
  - **Cybersecurity:** Kali Linux | Parrot OS | BlackArch | REMnux
  - **Server/Enterprise:** CentOS | RHEL | Alpine Linux
- **Localhost** — The IP address 127.0.0.1, always refers to your own machine
- **Loop** — Programming/scripting construct used to repeat a set of
commands iteratively
- **LHOST** — Local Host, the IP address of the attacking machine used
in Metasploit reverse shell connections
- **LPORT** — Local Port, the port on the attacking machine that
listens for incoming reverse shell connections
- **Loop** — A programming construct that repeats a block of code
multiple times while a condition is true:
  - for — runs a set number of times
  - while — runs while condition is true
  - do...while — runs at least once then checks condition
## M
- **Machine Account** — Windows computer account, always ends with $ symbol
- **Malware** — Malicious software designed to damage or gain unauthorized access
- **Meterpreter** — Advanced shell built into Metasploit, runs in memory
- **Metasploit** — Popular penetration testing framework for exploiting vulnerabilities
- **MITM** — Man In The Middle attack, intercepting communication between
two parties
- **Modulo** — Mathematical operation that returns the remainder of a
division. Written as % or mod
  - Example: 10 % 3 = 1
  - **MD5** — Message-Digest Algorithm 5, a widely used hash function
that produces a 128-bit hash value. Considered cryptographically
broken and unsuitable for security use
- **md5crypt** — MD5-based password hashing originally developed for
FreeBSD. Prefix: $1$
- **Metasploit** — The most widely used open source exploitation
framework, supports all phases of penetration testing from
reconnaissance to post-exploitation
- **Metasploit Framework** — The free open source command-line version
of Metasploit, pre-installed on Kali Linux
- **Metasploit Pro** — The commercial version of Metasploit with a
graphical interface and automation features
- **Meterpreter** — An advanced Metasploit payload that runs entirely
in memory, provides a powerful interactive shell on the target system
- **Module** — A self-contained piece of code in Metasploit that
performs a specific task (exploit, scanner, payload, etc)
- **msfvenom** — Metasploit command-line tool used to generate
standalone payloads in various formats (exe, php, python, etc)
for use outside of msfconsole
- **Migrate** — Meterpreter command that moves the payload from one
process to another on the target, used to gain stability or avoid
detection
- **Meterpreter** — An advanced Metasploit payload that runs entirely
in memory on the target system without writing to disk, making it
harder to detect. Provides a powerful interactive shell with
commands for file management, networking, surveillance and
privilege escalation
- **MIME Type** — Multipurpose Internet Mail Extensions type, a
label that identifies the format of a file or content (ex:
text/html, image/png)
## N
- **NAT** — Network Address Translation, maps private IPs to a public IP
- **Nmap** — Network scanning tool used to discover open ports and services
- **NTFS** — New Technology File System, the standard file system used by Windows
- **Network Interface** — The connection point between a computer and
a network (ex: eth0, wlo1, lo, ens33)
- **NTP** — Network Time Protocol, used to synchronize clocks across
networked devices (UDP Port 123)
- **Nmap** — Open-source network scanner used to discover hosts,
open ports, services and operating systems on a network
- **NTP** — Network Time Protocol, used to synchronize clocks across
networked devices (UDP Port 123)
- **NTLM** — NT LAN Manager, a Microsoft authentication protocol
that uses hashing to store and verify Windows passwords
- **NP** — Non-deterministic Polynomial Time, a class of computational
problems where a given solution can be checked quickly but finding
the solution itself may be very hard
- **NThash** — The hash format used by modern Windows operating systems
to store user and service passwords (also called NTLM hash)
- **Null** — A data type representing an intentionally empty or
non-existent value in programming
## O
- **Open Port** — A port actively accepting connections on a device
- **OpenSSL** — Cryptographic library that powers HTTPS encryption
- **OSI Model** — 7-layer framework describing how data travels over a network
- **OUs** — Organizational Units, container objects in Active Directory
used to classify users and machines
- **Object** — A complex data type in JavaScript that stores
multiple values as key-value pairs (ex: {name: "Pierre", age: 25})

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
- **Packet Sniffer** — A tool that captures and analyzes network traffic
passing through a network interface
- **pcap** — Packet Capture file format used to save captured network
traffic (file extension .pcap)
- **pcap-filter** — Filter syntax used in tcpdump to filter packets
by protocol, port, host, size and more
- **PCIDSS** — Payment Card Industry Data Security Standard, a set of
security standards designed to protect card payment data
- **Plaintext** — The original readable message or data before
encryption. Can be a document, image, or any binary data
- **PGP** — Pretty Good Privacy, software that implements encryption
for files, digital signing and secure communication
- **Private Key** — Secret key kept by the owner, used to decrypt
data or sign messages in asymmetric encryption
- **Public Key** — Key shared openly with everyone, used to encrypt
data or verify signatures in asymmetric encryption
- **Public Key Cryptography** — Encryption system using two
mathematically linked keys: a public key and a private key
- **Password Salting** — Adding a random value (salt) to a password
before hashing it, making rainbow table attacks ineffective
- **P (Polynomial Time)** — A class of computational problems whose
solution can be found efficiently in polynomial time (not exponential)
- **Password Cracking** — The process of recovering plaintext passwords
from stored hash values using tools like John the Ripper or Hashcat
- **Payload** — Code that runs on the target system after an exploit
succeeds. Determines what happens after gaining access:
  - **Singles** — Self-contained, no download needed
  - **Stagers** — Small payload that sets up connection, downloads stage
  - **Stages** — Downloaded by stager, enables larger payloads
  - **Adapters** — Converts payloads into different formats
  - **portfwd** — Meterpreter command that forwards a local port to a
remote service, used for pivoting into internal networks
- **Privilege Escalation** — The process of gaining higher access
than originally permitted. In Meterpreter: getsystem
- **Path** — The part of a URL that points to a specific file or
page on the web server (ex: /about/team)
- **Proxy** — In Burp Suite, an intercepting proxy that sits between
the browser and web server, capturing and allowing modification of
all HTTP/HTTPS traffic
## Q
- **Query String** — The part of a URL starting with ? that sends
parameters to the server (ex: ?search=hacking). Can be exploited
for injection attacks if not validated
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
- **RSA** — A widely used asymmetric encryption algorithm based on the
mathematical difficulty of factoring large prime numbers
- **RSA** — A widely used asymmetric encryption algorithm that enables
secure data transmission over insecure channels, based on the
mathematical difficulty of factoring large prime numbers
- **Rainbow Table** — A precomputed lookup table of hash values to
plaintext passwords, used to quickly crack password hashes
- **Rockyou.txt** — The most widely used password wordlist in
cybersecurity, containing over 14 million real passwords leaked from
the RockYou data breach. Pre-installed on Kali Linux at
/usr/share/wordlists/rockyou.txt
- **RHOSTS** — Remote Hosts, the target IP address or range set in
Metasploit modules
- **RPORT** — Remote Port, the port on the target system running the
vulnerable service
- **Reverse Shell** — A connection initiated from the target back to
the attacker's machine, used to gain remote control
- **Referrer-Policy** — An HTTP header that controls how much
referrer information is sent when a user clicks a link
- **Request-Response Cycle** — The process where a browser (client)
sends an HTTP request to a web server and the server responds with
the requested content
- **Repeater** — A Burp Suite tool that allows capturing, modifying
and resending HTTP requests multiple times, useful for manual
testing of vulnerabilities like SQLi and XSS
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
- **Scripting** — The process of writing and executing a series of commands
contained in a text file to automate tasks
- **Shebang** — The line #!/bin/bash at the top of a script that tells
the system which shell to use to execute it
- **SNMP** — Simple Network Management Protocol, used to monitor and
manage network devices like routers, switches and servers
- **SYN Scan** — A stealthy Nmap scan (-sS) that sends SYN packets
without completing the TCP handshake, harder to detect in logs
- **Subnet** — A subdivision of an IP network, represented with slash
notation (ex: 192.168.0.1/24 covers 256 addresses)
- **Symmetric Encryption** — Encryption that uses the same key for
both encrypting and decrypting data. Examples: AES, DES, 3DES
- **ssh-keygen** — Command-line tool used to generate SSH key pairs
(public and private keys)
- **SHA1** — Secure Hash Algorithm 1, produces a 160-bit hash value.
No longer considered secure for cryptographic use
- **SHA256** — Secure Hash Algorithm 256, produces a 256-bit hash
value. Part of the SHA-2 family, widely used and considered secure
- **scrypt** — A password-based key derivation function designed to
be memory-intensive to resist brute-force attacks. Prefix: $7$
- **Session** — An active connection established between Metasploit
and a target system, identified by a Session ID
- **Staged Payload** — A two-part payload where a small stager is
sent first to set up the connection, then downloads the larger stage
- **Stager** — The first part of a staged payload, sets up a
communication channel between attacker and target
- **SAM Database** — Security Account Manager, a Windows database
that stores user account password hashes. Can be dumped using
hashdump in Meterpreter
- **screenshare** — Meterpreter command that allows real-time viewing
of the target user's desktop
- **String** — A data type representing text values in programming
(ex: "Hello", "password123")
- **src attribute** — HTML attribute that specifies the path to an
external JavaScript file to be loaded into a web page
- **Sequencer** — A Burp Suite tool that assesses the randomness of
tokens such as session cookies and generated values to identify
weak randomness vulnerabilities
- **Session Cookie** — A unique identifier stored in the browser
that authenticates a user's session with a web application
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
- **Taskkill** — Windows command to terminate a running process by PID
- **Tasklist** — Windows command to list all currently running processes
- **TCP Connection** — Transmission Control Protocol connection, a
reliable connection-based communication between two endpoints
- **tcpdump** — Command-line packet analyzer tool used to capture, log
and filter network traffic on Linux/Mac
- **TCP Flags** — Control bits in a TCP packet header that manage the
state of a connection:
  - SYN — Synchronize, initiates a connection
  - ACK — Acknowledge, confirms receipt of data
  - FIN — Finish, terminates a connection
  - RST — Reset, abruptly terminates a connection
  - PSH — Push, sends data immediately without buffering
  - **TCP Connect Scan** — An Nmap scan (-sT) that completes the full
TCP three-way handshake to detect open ports
- **Timing Template** — Nmap setting (-T0 to -T5) that controls scan
speed from paranoid (slowest, stealthiest) to insane (fastest)
- **3DES** — Triple DES, applies DES encryption three times for a
168-bit key (112-bit effective security). Deprecated in 2019,
replaced by AES
- **Threads** — In Metasploit scanning, the number of simultaneous
processes running during a scan. More threads = faster but noisier
- **Timestomp** — A Meterpreter technique used to modify file
timestamps to hide evidence of activity on a target system
- **Typosquatting** — Registering domain names similar to legitimate
ones with small differences to trick users (ex: g00gle.com instead
of google.com), commonly used in phishing attacks
- **Token** — A randomly generated value used for authentication
or session management. Weak randomness in tokens can lead to
session hijacking attacks
## U
- **UAC** — User Account Control, Windows security feature that controls
administrative privileges
- **UDP Scan** — An Nmap scan (-sU) used to discover open UDP services
on a target
- **UDP** — User Datagram Protocol, connectionless transport protocol,
faster but less reliable than TCP
- **URL** — Uniform Resource Locator, a web address that guides your
browser to a specific resource on the internet. Made up of: scheme,
host, port, path, query string and fragment
## V
- **VirusTotal** — Virus-scanning service that scans files and URLs against
multiple antivirus engines and website scanners in a single operation
- **VPN** — Virtual Private Network, encrypts internet traffic and hides your
real public IP address
- **VSS** — Volume Shadow Copy Service, Windows service for backup and
restore of files
- **Vulnerability** — A weakness in a system that can be exploited
- **Variable** — A named storage location in a script that holds a value
to be reused (ex: name="Pierre")
- **VM** — Virtual Machine, a software-based emulation of a physical
computer that runs its own operating system
- **Vulnerability** — A design, coding or logic flaw in a system that
can be exploited to disclose information or execute unauthorized code
- **Variable** — A named container that stores a data value in
programming, can be updated and reused throughout the code
- **Virtual Host (vhost)** — A method of hosting multiple websites
on a single server using the same IP address. Different hostnames
are used to serve different websites
## W
- **Web Shell** — Malicious script uploaded to a web server giving
browser-based shell access
- **Wireshark** — Graphical network packet analyzer used to capture,
filter and investigate network traffic in real time
- **Word Mangling** — The process of applying rules to modify words
in a wordlist to generate password variations (ex: password →
Password1!)
- **Wordlist** — A text file containing a list of words or passwords
used in dictionary attacks for password cracking
- **Workspace** — A Metasploit feature that organizes scan results and
data into separate project spaces, useful when working on multiple
targets or engagements
- **WAF** — Web Application Firewall, filters incoming traffic to
block malicious requests before they reach the web server
- **Web Application** — A software application that runs in a web
browser, consisting of front end (HTML, CSS, JS) and back end
(server, database)
- **Web Browser** — A tool used to access and interact with web
applications (ex: Chrome, Firefox, Safari)
- **Web Server** — A component responsible for hosting and delivering
content for web applications
## X
- **XSS** — Cross-Site Scripting, injecting malicious scripts into web pages
- **XZ Utils** — Linux compression tool targeted by a supply chain attack
(CVE-2024-3094)
- **XOR** — Exclusive OR, a logical binary operation that returns 1
if bits are different and 0 if bits are the same. Widely used in
cryptography and computing
  - Symbol: ⊕ or ^
  - 1 XOR 0 = 1
  - 1 XOR 1 = 0
  - 0 XOR 0 = 0
  - **X-Content-Type-Options** — An HTTP security header that prevents
browsers from guessing MIME types, uses the nosniff directive
- **XSS** — Cross-Site Scripting, an attack that injects malicious
scripts into web pages viewed by other users
  ## Y
- **yescrypt** — A modern scalable password hashing scheme, default
and recommended choice on new Linux systems. Prefix: $y$
## Z
- **Zero-Day** — A vulnerability unknown to the software vendor with no
available patch
- **Zsh** (Z Shell) — Default shell on modern Macs, similar to Bash

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
## A
- **ARP** — Address Resolution Protocol, resolves IP addresses to MAC
addresses on a local network

## B
- **BGP** — Border Gateway Protocol, the primary routing protocol used
on the Internet, allows different networks to exchange routing information

## C
- **CA** — Certificate Authority, a trusted organization that issues
digital certificates to verify identities
- **CNAME Record** — Canonical Name DNS record, maps a domain name to
another domain name (ex: www.example.com → example.com)
- **CRS** — Certificate Signing Request, a request sent to a CA to
obtain a digital certificate

## D
- **Datagram** — UDP data unit that encapsulates application data
- **DHCP** — Dynamic Host Configuration Protocol, automatically assigns
IP addresses to devices on a network. Uses UDP and follows 4 steps:
  1. Discover — Client broadcasts looking for a DHCP server
  2. Offer — Server offers an available IP address
  3. Request — Client accepts the offered IP
  4. Acknowledge — Server confirms the IP is assigned to the client
- **DNS** — Domain Name System, translates domain names into IP addresses
- **DNS Record Types:**
  - **A Record** — Maps a hostname to an IPv4 address
  - **AAAA Record** — Maps a hostname to an IPv6 address
  - **CNAME Record** — Maps a domain to another domain name
  - **MX Record** — Specifies the mail server for a domain

## E
- **EIGRP** — Enhanced Interior Gateway Routing Protocol, a Cisco
proprietary routing protocol that chooses efficient paths based on
bandwidth and delay

## F
- **Frame** — An IP packet encapsulated on a WiFi or Ethernet network

## H
- **HTTP** — Hypertext Transfer Protocol, designed to retrieve web pages
(Port 80)
- **HTTPS** — Hypertext Transfer Protocol Secure, encrypted version of
HTTP (Port 443)

## I
- **ICMP** — Internet Control Message Protocol, used for network
diagnostics like ping and traceroute
- **IMAP** — Internet Message Access Protocol, allows email
synchronization across devices including read, moved and deleted messages

## M
- **MAC Address** — Media Access Control address, a unique 48-bit
hardware identifier for network devices, represented in hexadecimal
(ex: 7C:DF:A1:D3:8C:5C)
- **MIME** — Multipurpose Internet Mail Extensions, standard for
formatting non-text email content (attachments, images, etc)
- **MX Record** — Mail Exchange DNS record, specifies the mail server
responsible for handling emails for a domain

## N
- **NFS** — Network File System, allows files to be shared over a network
- **NSLOOKUP** — Command to look up the IP address of a domain name

## O
- **OSPF** — Open Shortest Path First, a routing protocol that allows
routers to share network topology and calculate the most efficient paths
- **OSI Model** — Open Systems Interconnection model, a 7-layer framework
describing how data travels over a network:
  1. Physical — Physical connection between devices (cables, signals)
  2. Data Link — Communication on same network segment, uses MAC addresses
  (ex: Ethernet, WiFi)
  3. Network — Logical addressing and routing between networks (ex: IP,
  ICMP, VPN)
  4. Transport — End-to-end communication between applications (ex: TCP,
  UDP)
  5. Session — Establishes, maintains and synchronizes communication
  between applications
  6. Presentation — Data encoding, compression and encryption
  7. Application — Network services for end-user applications (ex: HTTP,
  FTP, DNS, SMTP)
  - Mnemonic bottom to top: Please Do Not Throw Spinach Pizza Away

## P
- **POP3** — Post Office Protocol version 3, used to retrieve emails
from a mail server
- **Port 80** — HTTP web traffic
- **Port 443** — HTTPS secure web traffic
- **Port 8080** — Alternative HTTP port
- **Port 8443** — Alternative HTTPS port

## R
- **RIP** — Routing Information Protocol, a simple routing protocol for
small networks that chooses routes based on fewest hops
- **Routing Protocols** — Protocols that allow routers to share network
information and determine best paths for data:
  - OSPF — Open Shortest Path First
  - EIGRP — Enhanced Interior Gateway Routing Protocol
  - BGP — Border Gateway Protocol
  - RIP — Routing Information Protocol

## S
- **Segment** — TCP data unit that encapsulates application data sent
over TCP
- **SFTP** — SSH File Transfer Protocol, allows secure encrypted file
transfer (runs over SSH)
- **SMTP** — Simple Mail Transfer Protocol, defines how mail clients
talk to mail servers and how mail servers talk to each other
- **SSL** — Secure Sockets Layer, predecessor to TLS, used to encrypt
network communications (now largely replaced by TLS)

## T
- **TCP** — Transmission Control Protocol, a connection-oriented
transport protocol that ensures reliable data delivery (Layer 4)
- **Telnet** — Teletype Network protocol, used for remote terminal
connection, sends data in plain text (insecure, replaced by SSH, Port 23)
- **TLS** — Transport Layer Security, added to existing protocols to
protect communication confidentiality, integrity and authenticity
- **TTL** — Time-to-Live, an IP header field that limits how long a
packet can travel through the network, used by traceroute

## U
- **UDP** — User Datagram Protocol, a connectionless transport protocol
that allows fast data delivery to a specific process on a target host,
no guarantee of delivery (Layer 4)

## W
- **WHOIS** — Command and service to look up registration records of
any registered domain name

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
## Common Ports Reference

### All Protocols — Transport Protocol & Port
| Protocol | Transport | Default Port | Description |
|----------|-----------|--------------|-------------|
| TELNET | TCP | 23 | Insecure remote access |
| DNS | UDP or TCP | 53 | Domain Name System |
| HTTP | TCP | 80 | Web traffic |
| HTTPS | TCP | 443 | Secure web traffic |
| FTP | TCP | 21 | File Transfer Protocol |
| SMTP | TCP | 25 | Sending emails |
| POP3 | TCP | 110 | Receiving emails |
| IMAP | TCP | 143 | Email synchronization |
| SSH | TCP | 22 | Secure Shell |
| RPCSS | TCP | 135 | Windows Remote Procedure Call |
| SMB | TCP | 445 | Windows file sharing |
| RDP | TCP | 3389 | Remote Desktop Protocol |

### Cleartext vs Secure Protocol Ports
| Protocol | Cleartext Port | Secure Version | Secure Port |
|----------|---------------|----------------|-------------|
| HTTP | 80 | HTTPS | 443 |
| FTP | 21 | FTPS | 990 |
| TELNET | 23 | SSH | 22 |
| SMTP | 25 | SMTPS | 465 and 587 |
| POP3 | 110 | POP3S | 995 |
| IMAP | 143 | IMAPS | 993 |
