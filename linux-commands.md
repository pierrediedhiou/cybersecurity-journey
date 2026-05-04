# Linux Commands Cheatsheet

## Navigation
- `pwd` — Print Working Directory, shows the directory you are currently in
- `cd foldername` — Change Directory, move into a folder
- `cd ..` — Go back to the parent directory
- `cd /bin/` — Navigate to the bin directory
- `ls` — List files and folders in the current directory
- `ls /dev` — Find the name of storage peripherals on the machine
- `lsblk` — Display storage devices

## File & Directory Management
- `mkdir` — Make Directory, create a new folder
- `rmdir` — Remove Directory, delete an empty folder
- `rm -R` — Delete a directory and all its contents
- `rm -fr` — Force delete a directory and its contents
- `rm filename` — Delete a file
- `touch filename` — Create an empty file or modify the timestamp of a file/folder
- `mv` — Move or rename a file
- `cp` — Copy a file
- `ln` — Create a link between files
- `ln -s` — Create a symbolic link (requires complete paths)
- `~` — Symbol representing the home directory (tilde)
- `..` — Symbol representing the parent directory

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
- `find -iname "filename"` — Search for files using a case-insensitive regular expression
- `grep "keyword" filename` — Search for specific strings inside a file
- `sort` — Sort the output of a command
- `cut` — Cut sections of a file and print the result

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

## Permissions & Ownership
- `chmod` — Change/modify permissions of a file
- `chown` — Change the owner of a file
- `getfacl` — Consult file access control lists
- `passwd` — Change password

## Users & Identity
- `whoami` — Find out which user you are currently logged in as
- `id` — Shows the identity of the current user
- `su` — Switch User, change to another user (root by default)
- `sudo` — Execute a command without leaving your account
- `sudo su` — Become root without knowing the root password
- `$` — Symbol representing a regular user
- `#` — Symbol representing a superuser (root)
- `exit` — Exit the current shell or user session

## Processes & System
- `ps` — Process Status, display information about running processes
- `ps -f` — Display processes with more details
- `ps -e` — Display all processes on the machine
- `ps aux` — Display all processes in long format
- `top` — Real-time view of running processes and system resource usage
- `time` — Display a summary of the execution time of a process
- `uptime` — Show how long the system has been running
- `nproc` — Show the number of processors
- `nice` — Change the priority of a process
- `at` — Schedule a program to run at a given time

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

## Networking
- `ss -tuln` — Show all listening ports
- `ss -tulnp` — Show listening ports with process names
- `ifconfig | grep "inet "` — Show your private IP address
- `curl ifconfig.me` — Show your public IP address
- `Nmtui` — Manage network from a graphical command line interface
- `nmcli` — Manage network from the command line
- `lsof` — Check which processes are using the network

## Services & Daemons
- `systemctl` — Manage daemons and services
- `systemctl status servicename` — Check the state of a service
- `systemctl disable servicename` — Disable a service at boot
- `systemctl is-system-running` — Check if the system is in normal working state
- `systemd-analyze` — Overview of machine startup time

## Archiving & Compression
- `tar` — Tape Archive, used to archive and compress files
- `tar xzvf filename.tgz` — Unzip/extract a tgz file

## Shell & Miscellaneous
- `man command` — Show the manual page for a command (ex: man ls)
- `man -k keyword` — Search manual pages for a keyword (ex: man -k calendar)
- `q` — Exit a manual page
- `clear` — Clear the terminal screen
- `echo $0` — Show the current shell being used
- `csh` — Launch a new C shell
- `cal` — Show a calendar
- `fdisk` — Create or add a partition on a hard drive
- `Mkfs` — Make File System, create a file system
- `mount` — Associate a partition/file system to a directory
