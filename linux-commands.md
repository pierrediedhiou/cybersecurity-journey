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
