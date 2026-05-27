# Linux Commands Cheatsheet

## Archiving & Compression
- `tar` — Tape Archive, used to archive and compress files
- `tar xzvf filename.tgz` — Unzip/extract a tgz file

## Cron Jobs
- `crontab` — Schedule tasks to run automatically at specified times
- Crontab format requires 6 values:
  - MIN — Minute to execute at
  - HOUR — Hour to execute at
  - DOM — Day of month to execute at
  - MON — Month of year to execute at
  - DOW — Day of week to execute at
  - CMD — The actual command to execute

## File & Directory Management
- `mkdir` — Make Directory, create a new folder
- `rmdir` — Remove Directory, delete an empty folder
- `rm filename` — Delete a file
- `rm -r` — Delete a directory and all its contents
- `rm -fr` — Force delete a directory and its contents
- `touch filename` — Create an empty file or modify the timestamp of a file/folder
- `mv` — Move or rename a file
- `cp` — Copy a file
- `ln` — Create a link between files
- `ln -s` — Create a symbolic link (requires complete paths)

## File Operations & Redirection
- `echo "text"` — Repeat/display text or variables (ex: echo $0)
- `echo "text" > filename` — Overwrite a file with text
- `echo "text" >> filename` — Append text to an existing file
- `>` — Send the result of a command to a file
- `>>` — Add output to an existing file
- `|` — Pipe, allows two commands to communicate
- `*` — Wildcard for filenames
- `{}` — Used in the exec part of find command to insert the found filename
- `'xxx'` — Apostrophe, protection block for characters
- `xargs` — Retrieve arguments passed to another command
- `-h` — Flag to display output in a human-readable format (ex: ls -lh, df -h)

## File System Directories
| Directory | Description |
|-----------|-------------|
| `/etc` | Stores system configuration files used by the operating system |
| `/var` | Variable data directory, stores files that frequently change |
| `/root` | Home directory for the root user |
| `/tmp` | Temporary directory, contents are cleared on restart |
| `/var/log` | Standard directory where Linux stores all log files |

## File Transfer
- `wget URL` — Download a file from the web via HTTP
- `scp file user@ip:/path` — Securely transfer files between two computers
using SSH (provides authentication and encryption)

## Kill Signals
- `SIGTERM` — Kill a process but allow it to do cleanup tasks first
- `SIGKILL` — Kill a process immediately with no cleanup
- `SIGSTOP` — Stop/suspend a process

## Memory & Disk
- `du` — Disk Usage, show size of directories and files
- `df` — Disk Free, show available disk space on the filesystem
- `df -h` — Show partition sizes in human-readable format
- `swapon` — Activate/deactivate swap or display swap information
- `vmstat` — Virtual Memory Statistics, returns info about memory, processes, CPU
- `smem` — Show a report on memory being used
- `sar` — Collect statistical data on the system
- `sar -u` — Display current CPU data
- `sar -d` — Generate real-time disk I/O statistics
- `sar -r` — Show memory used
- `sar -w` — Show number of context switches per second

## Navigation
- `pwd` — Print Working Directory, shows the directory you are currently in
- `cd foldername` — Change Directory, move into a folder
- `cd ..` — Go back to the parent directory
- `cd /bin/` — Navigate to the bin directory
- `ls` — List files and folders in the current directory
- `ls -l filename` — Show detailed file info including owner and permissions
- `ls /dev` — Find the name of storage peripherals on the machine
- `lsblk` — Display storage devices
- `~` — Symbol representing the home directory (tilde)
- `..` — Symbol representing the parent directory

## Networking
- `ss -tuln` — Show all listening ports
- `ss -tulnp` — Show listening ports with process names
- `ifconfig | grep "inet "` — Show your private IP address
- `curl ifconfig.me` — Show your public IP address
- `nmtui` — Manage network from a graphical command line interface
- `nmcli` — Manage network from the command line
- `lsof` — Check which processes are using the network

## Package Management
- `apt install packagename` — Install software
- `apt remove packagename` — Remove software

## Permissions & Ownership
- `chmod` — Change/modify permissions of a file
- `chown` — Change the owner of a file
- `getfacl` — Consult file access control lists
- `passwd` — Change password

## Process Management
- `ps` — Process Status, display information about running processes
- `ps -f` — Display processes with more details
- `ps -e` — Display all processes on the machine
- `ps aux` — Display all processes in long format including background processes
- `top` — Real-time view of running processes and system resource usage
- `time` — Display a summary of the execution time of a process
- `uptime` — Show how long the system has been running
- `nproc` — Show the number of processors
- `nice` — Change the priority of a process
- `at` — Schedule a program to run at a given time
- `kill PID` — Terminate a process by its Process ID
- `fg` — Bring a previously backgrounded process back to the foreground

## Reading & Displaying Files
- `cat filename` — Display the contents of a file
- `cat -n filename` — Display file contents with line numbers
- `cat > filename` — Create or overwrite a file
- `cat >> filename` — Append to an existing file
- `head filename` — Show the beginning of a file (first 10 lines)
- `tail filename` — Show the end of a file (last 10 lines)
- `tail -n50 filename` — Show the last 50 lines of a file
- `stat filename` — Display statistics extracted from the file system
- `strings filename` — Extract readable strings from a binary file
- `wc filename` — Word Count, shows number of lines, words and bytes
- `wc -l filename` — Count the number of lines in a file

## Searching & Filtering
- `find / -name "filename" 2>/dev/null` — Search entire system for a file
- `find folder1 folder2 -type f` — Find files in specific folders
- `find -iname "filename"` — Search for files using a case-insensitive
regular expression
- `grep "keyword" filename` — Search for specific strings inside a file
- `sort` — Sort the output of a command
- `cut` — Cut sections of a file and print the result

## Services & Daemons
- `systemctl` — Manage daemons and services
- `systemctl start servicename` — Start a service
- `systemctl stop servicename` — Stop a service
- `systemctl enable servicename` — Enable a service to start at boot
- `systemctl disable servicename` — Disable a service at boot
- `systemctl status servicename` — Check the status of a service
- `systemctl is-system-running` — Check if the system is in normal working state
- `systemd-analyze` — Overview of machine startup time

## Shell & Miscellaneous
- `man command` — Show the manual page for a command (ex: man ls)
- `man -k keyword` — Search manual pages for a keyword (ex: man -k calendar)
- `q` — Exit a manual page
- `clear` — Clear the terminal screen
- `echo $0` — Show the current shell being used
- `csh` — Launch a new C shell
- `cal` — Show a calendar
- `fdisk` — Create or add a partition on a hard drive
- `mkfs` — Make File System, create a file system
- `mount` — Associate a partition/file system to a directory

## Text Editors
- `nano filename` — Create or edit a file using the nano text editor
- `Control + X` — Exit nano without saving
- `Control + X then Y then Enter` — Save and exit nano
- `vim filename` — Open a file in VIM, a more advanced text editor

## Users & Identity
- `whoami` — Find out which user you are currently logged in as
- `id` — Shows the identity of the current user
- `su` — Switch User, change to another user (root by default)
- `sudo` — Execute a command without leaving your account
- `sudo su` — Become root without knowing the root password
- `$` — Symbol representing a regular user
- `#` — Symbol representing a superuser (root)
- `exit` — Exit the current shell or user session
## Linux Shell
- `echo $0` — Check which shell you are currently using
- `cat /etc/shells` — List all available/installed shells on the system
- `history` — Display all previously typed commands
- `#!/bin/bash` — Shebang line used at the top of a Bash script to
indicate it should run with Bash
- `chmod +x filename` — Give executable permissions to a script

## Scripting & Variables
- Scripting — Writing and executing a series of commands in a text file
- Variables — Store a value to be reused in a script (ex: name="Pierre")
- Loops — Used in scripts to repeat iterative tasks automatically

## Windows Command Line (Additional Commands)
- `dir` — View child directories and files in current directory
- `dir /a` — Display hidden and system files
- `dir /s` — Display files in current directory and all subdirectories
- `cd target_directory` — Change to a specific directory
- `del filename` — Delete a file
- `erase filename` — Delete a file (alternative to del)
- `tasklist` — List all currently running processes
- `tasklist /FI "imagename eq notepad.exe"` — Find running process
related to a specific program
- `taskkill /PID 1516` — Kill a process by its PID
- `chkdsk` — Check the file system and disk volumes for errors and
bad sectors
- `driverquery` — Display a list of installed device drivers
- `sfc /scannow` — Scan system files for corruption and repair them
- `shutdown /s` — Shutdown the system
- `shutdown /r` — Restart the system
- `shutdown /a` — Abort a scheduled system shutdown

## PowerShell Commands
- `Get-Content filename` — Read and display the contents of a file
(similar to cat in Linux)
- `Set-Location path` — Change the current working directory
(similar to cd in Linux)
- `Get-Command` — List all available cmdlets, functions, aliases
and scripts in the current PowerShell session
- `Get-ChildItem` — List files and folders in current directory
(similar to ls in Linux)
- `Get-ChildItem | Sort-Object Length` — List files sorted by size
- `Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"` —
List only .txt files
- `Get-ComputerInfo` — Retrieve comprehensive system information
- `Get-LocalUser` — List all local user accounts on the system
- `Get-NetIPConfiguration` — Show detailed network interface info
including IP addresses, DNS servers and gateway
- `Get-NetIPAddress` — Show details for all IP addresses configured
on the system including inactive ones
- `Get-Process` — View all running processes including CPU and
memory usage
- `Get-Service` — Retrieve information about services on the machine
(running, stopped or paused)
- `Get-NetTCPConnection` — Display current TCP connections including
local and remote endpoints
- `Get-FileHash filename` — Generate a hash of a file
- `Invoke-Command` — Execute commands on remote systems, used for
remote management and automation

## PowerShell Comparison Operators
- `-eq` — Equal to
- `-ne` — Not equal to
- `-gt` — Greater than (strict, excludes equal values)
- `-ge` — Greater than or equal to
- `-lt` — Less than (strict, excludes equal values)
- `-le` — Less than or equal to
## Networking Commands
- `ping target` — Test connectivity to a target and measure round-trip
time (RTT) using ICMP
- `ping -c 4 target` — Send exactly 4 ping packets then stop
- `traceroute target` — Discover the network route from your host to
the target (Linux/Mac)
- `tracert target` — Same as traceroute but for Windows
- `nslookup domain` — Look up the IP address of a domain
- `whois domain` — Look up registration records of a domain name

## FTP Commands (inside an FTP session)
- `USER username` — Input the username
- `PASS password` — Enter the password
- `RETR filename` — Download a file from the FTP server to the client
- `STOR filename` — Upload a file from the client to the FTP server

## HTTP Methods
- `GET` — Retrieve data from a server (HTML file, image, etc)
- `POST` — Submit new data to the server (form, file upload)
- `PUT` — Create or overwrite a resource on the server
- `DELETE` — Delete a specified file or resource on the server

## SMTP Commands (inside an SMTP session)
- `HELO` or `EHLO` — Initiate an SMTP session
- `MAIL FROM` — Specify the sender's email address
- `RCPT TO` — Specify the recipient's email address
- `DATA` — Begin sending the email content
- `.` — Sent on its own line to indicate end of email message

## POP3 Commands (inside a POP3 session)
- `USER username` — Identify the user
- `PASS password` — Provide the user's password
- `STAT` — Request the number of messages and total size
- `LIST` — List all messages and their sizes
- `RETR message_number` — Retrieve a specific message
- `DELE message_number` — Mark a message for deletion
- `QUIT` — End the POP3 session and apply changes

## IMAP Commands (inside an IMAP session)
- `LOGIN username password` — Authenticate the user
- `SELECT mailbox` — Select a mailbox folder to work with
- `FETCH mail_number body[]` — Fetch a message (header and body)
- `MOVE sequence mailbox` — Move messages to another mailbox
- `COPY sequence mailbox` — Copy messages to another mailbox
- `LOGOUT` — Log out of the IMAP session
## Wireshark
- **Wireshark** — Graphical network packet analyzer used to capture
and investigate network traffic

### Wireshark Interface Sections
- **Toolbar** — Main toolbar for packet sniffing, filtering, sorting,
summarising, exporting and merging
- **Display Filter Bar** — Main query and filtering section
- **Recent Files** — List of recently investigated files
- **Capture Filter and Interfaces** — Capture filters and available
network interfaces (connection points between a computer and a network)
- **Status Bar** — Tool status, profile and numeric packet information

### Wireshark Alert Severity Colours
| Severity | Colour | Description |
|----------|--------|-------------|
| Chat | Blue | Information on usual workflow |
| Note | Cyan | Notable events like application error codes |
| Warn | Yellow | Warnings like unusual error codes or problems |
| Error | Red | Problems like malformed packets |

## Tcpdump
- **tcpdump** — Powerful command-line packet analyzer used to capture,
log and filter network traffic flowing through a computer

### Tcpdump Basic Options
- `tcpdump -i INTERFACE` — Listen on a specific network interface
- `tcpdump -i any` — Listen on all available interfaces
- `tcpdump -i eth0` — Listen on the eth0 interface
- `tcpdump -i wlo1` — Listen on the WiFi network interface
- `tcpdump -r FILE` — Read captured packets from a file
- `tcpdump -w FILE` — Save captured packets to a file
- `tcpdump -c COUNT` — Capture a specific number of packets then stop
- `tcpdump -n` — Do not resolve IP addresses
- `tcpdump -nn` — Do not resolve IP addresses or protocol numbers
- `tcpdump -v` — Verbose output, more details about packets
- `tcpdump -vv` — More verbose output
- `tcpdump -vvv` — Maximum verbosity output
- `tcpdump -q` — Quick output, print brief packet information
- `tcpdump -e` — Print the link-level header
- `tcpdump -A` — Show packet data in ASCII
- `tcpdump -xx` — Show packet data in hexadecimal (hex) format
- `tcpdump -X` — Show packet headers and data in both hex and ASCII
- `ip address show` — List all available network interfaces
- `ip a s` — Shorthand for ip address show

### Tcpdump Logical Operators
- `and` — Capture packets where both conditions are true
  - Example: `tcpdump host 1.1.1.1 and tcp`
- `or` — Capture packets where either condition is true
  - Example: `tcpdump udp or icmp`
- `not` — Capture packets where the condition is not true
  - Example: `tcpdump not tcp`

### Tcpdump Size Filters
- `greater LENGTH` — Filter packets with length greater than or equal
to specified length
- `less LENGTH` — Filter packets with length less than or equal to
specified length

### Tcpdump Binary Operators
- `&` — AND: returns 0 unless both inputs are 1
- `|` — OR: returns 1 unless both inputs are 0
- `!` — NOT: inverts the bit (1 becomes 0, 0 becomes 1)

### Tcpdump TCP Flags
- `tcp-syn` — TCP SYN (Synchronize) flag
- `tcp-ack` — TCP ACK (Acknowledge) flag
- `tcp-fin` — TCP FIN (Finish) flag
- `tcp-rst` — TCP RST (Reset) flag
- `tcp-push` — TCP Push flag
- `tcp[tcpflags]` — Used to refer to the TCP flags field in a filter

### Tcpdump Packet Header Syntax
- `proto[expr:size]` — Refer to contents of any byte in a packet header
  - `proto` — Protocol (arp, ether, icmp, ip, ip6, tcp, udp)
  - `expr` — Byte offset, 0 refers to the first byte
  - `size` — Number of bytes (1, 2 or 4), default is 1

### Tcpdump Practical Examples
- `tcpdump -i any tcp port 22` — Capture SSH traffic on all interfaces
- `tcpdump -i wlo1 udp port 123` — Capture NTP traffic on WiFi
- `tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap` —
Capture HTTPS traffic from example.com and save to file
### Tcpdump Filtering Commands
| Command | Explanation |
|---------|-------------|
| `tcpdump host IP` | Filters packets by IP address |
| `tcpdump host HOSTNAME` | Filters packets by hostname |
| `tcpdump src host IP` | Filters packets by specific source host |
| `tcpdump dst host IP` | Filters packets by specific destination host |
| `tcpdump port PORT_NUMBER` | Filters packets by port number |
| `tcpdump src port PORT_NUMBER` | Filters packets by source port number |
| `tcpdump dst port PORT_NUMBER` | Filters packets by destination port number |
| `tcpdump PROTOCOL` | Filters packets by protocol (ex: ip, ip6, icmp) |

### Tcpdump Display Options
| Command | Explanation |
|---------|-------------|
| `tcpdump -q` | Quick and quiet — brief packet information |
| `tcpdump -e` | Include MAC addresses in output |
| `tcpdump -A` | Print packets in ASCII encoding |
| `tcpdump -xx` | Display packets in hexadecimal format |
| `tcpdump -X` | Show packets in both hexadecimal and ASCII formats |
## Nmap
- **Nmap** — Open-source network scanner used to discover hosts,
services, and vulnerabilities on a network

### Nmap Target Specification
| Format | Example | Description |
|--------|---------|-------------|
| Single IP | `192.168.0.1` | Scan a single IP address |
| IP Range | `192.168.0.1-10` | Scan IPs from .1 to .10 |
| Subnet | `192.168.0.1/24` | Scan entire subnet (0-255) |
| Hostname | `example.thm` | Scan by hostname |

### Nmap Host Discovery
| Command | Explanation |
|---------|-------------|
| `nmap -sn TARGET` | Discover live hosts without port scanning |
| `nmap -sL TARGET` | List targets to scan without actually scanning |
| `nmap -Pn TARGET` | Scan hosts that appear to be offline/down |

### Nmap Scan Types
| Command | Explanation |
|---------|-------------|
| `nmap -sT TARGET` | TCP Connect scan |
| `nmap -sS TARGET` | SYN scan (stealth scan) |
| `nmap -sU TARGET` | UDP scan |

### Nmap Service & OS Detection
| Command | Explanation |
|---------|-------------|
| `nmap -O TARGET` | Enable OS detection |
| `nmap -sV TARGET` | Enable service and version detection |
| `nmap -A TARGET` | OS detection, version detection and extras |

### Nmap Port Selection
| Command | Explanation |
|---------|-------------|
| `nmap -F TARGET` | Fast mode, scan 100 most common ports |
| `nmap -p10-1024 TARGET` | Scan ports 10 to 1024 |
| `nmap -p-25 TARGET` | Scan ports 1 to 25 |
| `nmap -p- TARGET` | Scan all ports (1-65535) |
| `nmap -p1-1023 TARGET` | Scan well-known ports only |

### Nmap Timing Templates
| Template | Flag | Approx Speed |
|----------|------|-------------|
| Paranoid | `-T0` | 9.8 hours |
| Sneaky | `-T1` | 27.53 minutes |
| Polite | `-T2` | 40.56 seconds |
| Normal | `-T3` | 0.15 seconds (default) |
| Aggressive | `-T4` | 0.13 seconds |
| Insane | `-T5` | Fastest, may miss results |

### Nmap Performance Options
| Command | Explanation |
|---------|-------------|
| `--min-parallelism NUM` | Minimum number of parallel probes |
| `--max-parallelism NUM` | Maximum number of parallel probes |
| `--min-rate NUM` | Minimum packets per second |
| `--max-rate NUM` | Maximum packets per second |
| `--host-timeout TIME` | Maximum time to wait for a target host |

### Nmap Verbosity & Debugging
| Command | Explanation |
|---------|-------------|
| `nmap -v TARGET` | Verbose output, more details |
| `nmap -vv TARGET` | More verbose output |
| `nmap -vvvv TARGET` | Maximum verbose output |
| `nmap -v2 TARGET` | Specify verbosity level directly |
| `nmap -d TARGET` | Debugging output |
| `nmap -d9 TARGET` | Maximum debugging level |

### Nmap Output Formats
| Command | Explanation |
|---------|-------------|
| `nmap -oN filename` | Normal output saved to file |
| `nmap -oX filename` | XML output saved to file |
| `nmap -oG filename` | Grep-able output (useful for grep and awk) |
| `nmap -oA basename` | Output in all major formats at once |
## Cryptography Operations

### XOR Operation
- **XOR** (Exclusive OR) — Logical operation that compares two bits:
  - Returns 1 if the bits are DIFFERENT
  - Returns 0 if the bits are the SAME
  - Symbol: ⊕ or ^
  - Example: 1 XOR 0 = 1 | 1 XOR 1 = 0 | 0 XOR 0 = 0

### Modulo Operation
- **Modulo** — Returns the remainder when dividing two numbers
  - Written as % or mod
  - Example: 10 % 3 = 1 (because 10 divided by 3 = 3 remainder 1)
  - Example: 15 % 5 = 0 (because 15 divided by 5 = 3 remainder 0)

### Encryption Standards Comparison
| Standard | Key Size | Status |
|----------|----------|--------|
| DES | 56 bits | Broken in 1999, deprecated |
| 3DES | 168 bits (112 effective) | Deprecated 2019 |
| AES | 128, 192 or 256 bits | Current standard (since 2001) |

### Symmetric vs Asymmetric Encryption
| | Symmetric | Asymmetric |
|---|---|---|
| Keys used | Same key for encrypt and decrypt | Public key + Private key |
| Speed | Fast | Slower |
| Examples | AES, DES, 3DES | RSA, Diffie-Hellman, ECC |
| Key sharing | Key must stay secret | Public key shared freely |
## Public Key Cryptography Commands

### SSH Key Generation & Usage
- `ssh-keygen` — Generate an SSH key pair (public and private key)
- `ssh -i privateKeyFileName user@host` — Connect to a host using
a specific private key file

### GPG Commands
- `gpg --import backup.key` — Import a GPG key from a backup file
- `gpg --decrypt confidential_message.gpg` — Decrypt a GPG
encrypted message

### Key Types Comparison
| Key Type | Algorithm | Description |
|----------|-----------|-------------|
| RSA | RSA | Most widely used, based on prime factorization |
| DSA | DSA | Designed specifically for digital signatures |
| ECDSA | Elliptic Curve DSA | Smaller key sizes, same security as DSA |
| ECDSA-SK | ECDSA + Security Key | Hardware-based private key protection |
| Ed25519 | EdDSA + Curve25519 | Modern, fast and highly secure |
| Ed25519-SK | Ed25519 + Security Key | Hardware-based private key protection |

### Symmetric vs Asymmetric vs Digital Signatures
| | Symmetric | Asymmetric | Digital Signature |
|---|---|---|---|
| Purpose | Encrypt data | Encrypt data | Verify identity |
| Keys | One shared key | Public + Private key | Private to sign, Public to verify |
| Examples | AES, DES | RSA, Diffie-Hellman | DSA, ECDSA, Ed25519 |
| Speed | Fast | Slow | Medium |
## Hashcat
- **Hashcat** — Password cracking tool that uses hash files and
wordlists to recover plaintext passwords

### Hashcat Basic Syntax
## John the Ripper
- **John the Ripper** — Free open source password cracking tool,
beginner friendly with automatic hash type detection
- **Jumbo John** — The most popular extended version of John the
Ripper with more features and hash support

### John the Ripper Basic Syntax
## Metasploit

### Launching Metasploit
- `msfconsole` — Launch the Metasploit Framework console

### Metasploit Basic Commands
| Command | Explanation |
|---------|-------------|
| `search <keyword>` | Search for a module by name or keyword |
| `use <module>` | Select a module to use |
| `info` | Show information about the current module |
| `show options` | Display required and optional parameters |
| `show payloads` | List compatible payloads for current module |
| `set <option> <value>` | Set a parameter value |
| `setg <option> <value>` | Set a global parameter value for all modules |
| `unsetg <option>` | Clear a global parameter value |
| `run` or `exploit` | Execute the current module |
| `back` | Go back to the main console |
| `sessions` | List all active sessions |
| `sessions -i <ID>` | Interact with a specific session |

### Metasploit Common Parameters
| Parameter | Full Name | Description |
|-----------|-----------|-------------|
| `RHOSTS` | Remote Hosts | IP address of the target system |
| `RPORT` | Remote Port | Port on the target system |
| `PAYLOAD` | Payload | The payload to use with the exploit |
| `LHOST` | Local Host | IP address of your attacking machine |
| `LPORT` | Local Port | Port on your machine for reverse shell |
| `SESSION` | Session | ID of an existing connection to reuse |

### Metasploit Payload Types
| Type | Description |
|------|-------------|
| **Singles** | Self-contained payloads that run without downloading anything extra (ex: add user, launch notepad) |
| **Stagers** | Small payload that sets up a connection channel then downloads the rest of the payload |
| **Stages** | Downloaded by the stager, allows larger sized payloads |
| **Adapters** | Wraps payloads to convert them into different formats (ex: PowerShell) |

### Identifying Payload Types by Name
| Example | Type | Explanation |
|---------|------|-------------|
| `generic/shell_reverse_tcp` | Single/Inline | Uses / separator, self-contained |
| `windows/x64/shell/reverse_tcp` | Staged | Uses / separator with extra stage directory |

### Metasploit Two Versions
| Version | Type | Interface |
|---------|------|-----------|
| **Metasploit Pro** | Commercial | Graphical User Interface (GUI) |
| **Metasploit Framework** | Open Source | Command Line (msfconsole) |
## Metasploit: Exploitation & Advanced Commands

### Launching & Payload Generation
| Command | Explanation |
|---------|-------------|
| `msfconsole` | Launch the Metasploit Framework console |
| `msfvenom` | Generate standalone payloads outside of Metasploit |

### Metasploit Database Commands
| Command | Explanation |
|---------|-------------|
| `db_status` | Check the database connection status |
| `workspace` | List all available workspaces |
| `workspace <name>` | Switch to a specific workspace |
| `workspace -a <name>` | Create a new workspace |
| `workspace -d <name>` | Delete a workspace |
| `workspace -h` | List all available workspace options |
| `help` | Show Database Backends Commands menu |

### Metasploit Session Management
| Command | Explanation |
|---------|-------------|
| `sessions` | List all active sessions |
| `sessions -i <ID>` | Interact with a specific session |
| `Control + Z` | Background a session (keeps it alive) |
| `Control + C` | Abort/terminate a session |

### Metasploit Scanner Module Parameters
| Parameter | Explanation |
|-----------|-------------|
| `CONCURRENCY` | Number of targets to be scanned simultaneously |
| `PORTS` | Port range to scan (1-1000 scans ports 1 to 1000, unlike Nmap) |
| `RHOSTS` | Target IP or network range to scan |
| `THREADS` | Number of simultaneous threads (more = faster scan) |

### Useful Metasploit Modules
| Module | Explanation |
|--------|-------------|
| `scanner/discovery/udp_sweep` | Quickly identify services running over UDP |
| `info` | Show detailed information about any module |

### Important Notes
- Metasploit port scanning (1-1000) scans ports 1 to 1000 exactly
- Nmap default scans the 1000 most commonly used ports (not 1-1000)
- More THREADS = faster scan but more noisy on the network
- Always use `db_status` to confirm database is connected before scanning
## Meterpreter Commands

### About Meterpreter
- Runs entirely in memory on the target system
- Does not write itself to disk (harder to detect)
- Not installed on the target system permanently
- Loaded as a Metasploit payload after successful exploitation

### Meterpreter Core Commands
| Command | Explanation |
|---------|-------------|
| `background` | Background the current session (keeps it alive) |
| `exit` | Terminate the Meterpreter session |
| `guid` | Get the session GUID (Globally Unique Identifier) |
| `help` | Display the help menu |
| `info` | Display information about a Post module |
| `irb` | Open an interactive Ruby shell on the current session |
| `load` | Load one or more Meterpreter extensions |
| `migrate` | Migrate Meterpreter to another process |
| `run` | Execute a Meterpreter script or Post module |
| `sessions` | Quickly switch to another session |

### Meterpreter File System Commands
| Command | Explanation |
|---------|-------------|
| `cd <directory>` | Change directory |
| `ls` or `dir` | List files in the current directory |
| `pwd` | Print the current working directory |
| `cat <file>` | Display the contents of a file |
| `edit <file>` | Edit a file |
| `rm <file>` | Delete a file |
| `search <keyword>` | Search for files on the target system |
| `upload <file>` | Upload a file or directory to the target |
| `download <file>` | Download a file or directory from the target |

### Meterpreter Networking Commands
| Command | Explanation |
|---------|-------------|
| `arp` | Display the host ARP cache |
| `ifconfig` | Display network interfaces on the target system |
| `netstat` | Display active network connections |
| `portfwd` | Forward a local port to a remote service |
| `route` | View and modify the routing table |

### Meterpreter System Commands
| Command | Explanation |
|---------|-------------|
| `clearev` | Clear the event logs on the target |
| `execute <command>` | Execute a command on the target |
| `getpid` | Show the current process identifier |
| `getuid` | Show the user Meterpreter is running as |
| `kill <PID>` | Terminate a process by PID |
| `pkill <name>` | Terminate processes by name |
| `ps` | List all running processes |
| `reboot` | Reboot the remote computer |
| `shell` | Drop into a system command shell |
| `shutdown` | Shut down the remote computer |
| `sysinfo` | Get system information including OS details |

### Meterpreter Surveillance Commands
| Command | Explanation |
|---------|-------------|
| `idletime` | Show how long the remote user has been idle |
| `keyscan_start` | Start capturing keystrokes on the target |
| `keyscan_dump` | Dump the captured keystroke buffer |
| `keyscan_stop` | Stop capturing keystrokes |
| `screenshare` | Watch the remote user's desktop in real time |
| `screenshot` | Take a screenshot of the target desktop |
| `record_mic` | Record audio from the target microphone |
| `webcam_list` | List available webcams on the target |
| `webcam_snap` | Take a snapshot from a webcam |
| `webcam_stream` | Stream live video from a webcam |
| `webcam_chat` | Start a video chat with the target |

### Meterpreter Privilege & Password Commands
| Command | Explanation |
|---------|-------------|
| `getsystem` | Attempt to elevate privileges to local system |
| `hashdump` | Dump the contents of the SAM database |

### Meterpreter Command Categories
- Core commands
- File system commands
- Networking commands
- System commands
- User interface commands
- Webcam commands
- Audio output commands
- Elevate commands
- Password database commands
- Timestomp commands
## Web Application Basics

### URL Structure Breakdown
| Component | Symbol | Description | Security Note |
|-----------|--------|-------------|---------------|
| **Scheme** | `http://` or `https://` | Protocol used to access the website | Always prefer HTTPS |
| **User** | `user@` | Optional login credentials in URL | Avoid — exposes sensitive info |
| **Host/Domain** | `example.com` | The website you are accessing | Watch for typosquatting |
| **Port** | `:80` or `:443` | Directs browser to correct service | 80=HTTP, 443=HTTPS |
| **Path** | `/page/file` | Specific file or page on the server | Secure paths from unauthorized access |
| **Query String** | `?search=term` | Parameters sent to the server | Validate to prevent injection attacks |
| **Fragment** | `#section` | Points to specific section of a page | Validate to prevent injection attacks |

### HTTP Message Structure
| Part | Description |
|------|-------------|
| **Start Line** | Introduces the message, states request or response type |
| **Headers** | Key-value pairs providing extra info about the message |
| **Empty Line** | Separates headers from the body |
| **Body** | Contains the actual data (form data, webpage content, etc) |

### HTTP Methods
| Method | Purpose | Security Note |
|--------|---------|---------------|
| `GET` | Fetch data from server without changes | Never put sensitive info in GET requests |
| `POST` | Send data to create or update something | Always validate input, prevent SQLi and XSS |
| `PUT` | Replace or update a resource on server | Verify user is authorized before accepting |
| `DELETE` | Remove a resource from server | Only authorized users should delete |
| `PATCH` | Update part of a resource | Validate data to avoid inconsistencies |
| `HEAD` | Like GET but retrieves headers only | Useful for checking metadata |
| `OPTIONS` | Show available methods for a resource | Helps clients understand server capabilities |
| `TRACE` | Shows allowed methods, used for debugging | Often disabled for security reasons |
| `CONNECT` | Create a secure encrypted connection | Used for HTTPS tunneling |

### HTTP Versions Timeline
| Version | Year | Key Features |
|---------|------|-------------|
| HTTP/0.9 | 1991 | First version, GET requests only |
| HTTP/1.0 | 1996 | Added headers and content type support |
| HTTP/1.1 | 1997 | Persistent connections, chunked encoding, caching |
| HTTP/2 | 2015 | Multiplexing, header compression, prioritization |
| HTTP/3 | 2022 | Built on QUIC protocol, faster and more secure |

### HTTP Security Headers
| Header | Purpose |
|--------|---------|
| `Content-Security-Policy (CSP)` | Prevents XSS by controlling where resources load from |
| `Strict-Transport-Security (HSTS)` | Forces browsers to always use HTTPS |
| `X-Content-Type-Options` | Prevents browsers from guessing MIME types |
| `Referrer-Policy` | Controls how much referrer info is sent to other sites |

### CSP Directives
| Directive | Description |
|-----------|-------------|
| `default-src` | Default policy, usually set to self (current website only) |
| `script-src` | Where scripts can be loaded from |
| `style-src` | Where CSS stylesheets can be loaded from |

### HSTS Directives
| Directive | Description |
|-----------|-------------|
| `max-age` | Expiry time in seconds for the HSTS setting |
| `includeSubDomains` | Apply HSTS to all subdomains |
| `preload` | Include site in browser preload lists |

### Referrer-Policy Options
| Policy | Description |
|--------|-------------|
| `no-referrer` | Never send referrer information |
| `same-origin` | Only send referrer for same website links |
| `strict-origin` | Send referrer only when protocol stays the same |
| `strict-origin-when-cross-origin` | Full URL for same origin, origin only for cross origin |

### X-Content-Type-Options
| Directive | Description |
|-----------|-------------|
| `nosniff` | Instructs browser not to guess the MIME type |
## JavaScript Essentials

### JavaScript Integration Methods
| Method | Description |
|--------|-------------|
| **Internal** | JS code placed directly inside the HTML document |
| **External** | JS loaded from a separate file using the src attribute |

```html
<!-- Internal JavaScript -->
<script>
  alert("Hello!");
</script>

<!-- External JavaScript -->
<script src="script.js"></script>
```

### JavaScript Data Types
| Data Type | Description | Example |
|-----------|-------------|---------|
| `string` | Text values | "Hello", "password123" |
| `number` | Numeric values | 42, 3.14 |
| `boolean` | True or false values | true, false |
| `null` | Intentionally empty value | null |
| `undefined` | Variable declared but not assigned | undefined |
| `object` | Complex data like arrays or objects | {name: "Pierre"} |

### JavaScript Control Flow
| Structure | Description |
|-----------|-------------|
| `if-else` | Execute different code blocks based on a condition |
| `switch` | Select one of many code blocks to execute |
| `for` | Loop that runs a set number of times |
| `while` | Loop that runs while a condition is true |
| `do...while` | Loop that runs at least once then checks condition |

### JavaScript Dialogue Functions
| Function | Description | Returns |
|----------|-------------|---------|
| `alert("message")` | Displays a message with an OK button | Nothing |
| `prompt("question")` | Asks user for input | String input or null |
| `confirm("question")` | Asks user to confirm with OK/Cancel | true or false |

### JavaScript Examples
```javascript
// Variable
let name = "Pierre";

// Function
function greet(name) {
  return "Hello " + name;
}

// If-Else
if (name === "Pierre") {
  alert("Welcome back!");
} else {
  alert("Who are you?");
}

// For Loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// While Loop
while (condition === true) {
  // code runs repeatedly
}

// Prompt
let username = prompt("What is your name?");

// Confirm
let answer = confirm("Are you sure?");
// Returns true if OK, false if Cancel
```

### Request-Response Cycle
1. User types a URL or clicks a link in their browser (client)
2. Browser sends an HTTP request to the web server
3. Server processes the request
4. Server sends back an HTTP response
5. Browser renders the response (HTML, CSS, JS)
