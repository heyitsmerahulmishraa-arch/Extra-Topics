# Complete Linux Terminal & Ubuntu Mastery Checklist

## 1. Terminal Fundamentals

* [ ] What is a terminal?
* [ ] Terminal vs shell
* [ ] What is a shell?
* [ ] Bash
* [ ] Zsh
* [ ] Terminal emulator
* [ ] CLI vs GUI
* [ ] Command structure
* [ ] Command arguments
* [ ] Options/flags
* [ ] Short flags
* [ ] Long flags
* [ ] Command output
* [ ] Exit status
* [ ] `0` success
* [ ] Non-zero failure
* [ ] `$?`
* [ ] Command history
* [ ] Tab completion
* [ ] Ctrl+C
* [ ] Ctrl+D
* [ ] Ctrl+Z
* [ ] Ctrl+L
* [ ] Ctrl+A
* [ ] Ctrl+E
* [ ] Ctrl+R
* [ ] Ctrl+U
* [ ] Ctrl+K
* [ ] Ctrl+W

---

# 2. Linux Basics

* [ ] What is Linux?
* [ ] Linux kernel
* [ ] GNU/Linux
* [ ] Ubuntu
* [ ] Ubuntu Server
* [ ] Linux distributions
* [ ] Kernel vs distribution
* [ ] Root user
* [ ] Normal user
* [ ] Home directory
* [ ] Filesystem
* [ ] Processes
* [ ] Services
* [ ] Packages
* [ ] Daemons
* [ ] Shell

---

# 3. Filesystem Hierarchy

Understand what these directories are for:

* [ ] `/`
* [ ] `/home`
* [ ] `/root`
* [ ] `/etc`
* [ ] `/var`
* [ ] `/var/log`
* [ ] `/usr`
* [ ] `/usr/bin`
* [ ] `/usr/sbin`
* [ ] `/bin`
* [ ] `/sbin`
* [ ] `/opt`
* [ ] `/tmp`
* [ ] `/dev`
* [ ] `/proc`
* [ ] `/sys`
* [ ] `/run`
* [ ] `/mnt`
* [ ] `/media`
* [ ] `/boot`
* [ ] `/lib`
* [ ] `/snap`

---

# 4. Navigation

* [ ] `pwd`
* [ ] `ls`
* [ ] `ls -l`
* [ ] `ls -a`
* [ ] `ls -lah`
* [ ] `cd`
* [ ] `cd ..`
* [ ] `cd ~`
* [ ] `cd -`
* [ ] Absolute paths
* [ ] Relative paths
* [ ] `.` current directory
* [ ] `..` parent directory
* [ ] `~` home directory

### Practice

* [ ] Navigate entire filesystem
* [ ] Move between nested directories
* [ ] Use absolute paths
* [ ] Use relative paths

---

# 5. Creating Files & Directories

* [ ] `touch`
* [ ] `mkdir`
* [ ] `mkdir -p`
* [ ] Create nested directories
* [ ] Create multiple files
* [ ] Create multiple directories
* [ ] Hidden files
* [ ] File extensions
* [ ] Files without extensions

---

# 6. Copy, Move & Delete

* [ ] `cp`
* [ ] `cp -r`
* [ ] `cp -a`
* [ ] `mv`
* [ ] `rm`
* [ ] `rm -r`
* [ ] `rm -f`
* [ ] `rmdir`
* [ ] Understand dangerous `rm -rf`
* [ ] Rename files
* [ ] Rename directories
* [ ] Move files
* [ ] Copy directories
* [ ] Delete directories

---

# 7. Reading Files

* [ ] `cat`
* [ ] `less`
* [ ] `more`
* [ ] `head`
* [ ] `tail`
* [ ] `tail -f`
* [ ] `nl`
* [ ] `wc`
* [ ] `file`
* [ ] `stat`

### Practice

* [ ] Read configuration files
* [ ] Read log files
* [ ] Monitor logs in real time
* [ ] Inspect file metadata

---

# 8. Editing Files From Terminal

* [ ] Nano
* [ ] Vim
* [ ] Neovim
* [ ] Open file
* [ ] Edit file
* [ ] Save file
* [ ] Exit editor
* [ ] Search inside files
* [ ] Replace text
* [ ] Copy/paste
* [ ] Vim modes
* [ ] Vim navigation
* [ ] Vim commands
* [ ] Vim configuration

### Minimum

* [ ] Become comfortable with Nano
* [ ] Learn basic Vim
* [ ] Open and edit server configuration files

---

# 9. File Permissions

One of the most important Linux topics.

* [ ] Read permission
* [ ] Write permission
* [ ] Execute permission
* [ ] User
* [ ] Group
* [ ] Others
* [ ] `ls -l`
* [ ] Permission notation
* [ ] `r`
* [ ] `w`
* [ ] `x`
* [ ] Numeric permissions
* [ ] `chmod`
* [ ] `chmod 755`
* [ ] `chmod 644`
* [ ] `chmod 700`
* [ ] `chmod +x`
* [ ] `chmod -x`
* [ ] `chown`
* [ ] `chgrp`
* [ ] `umask`

### Understand

* [ ] Why files have permissions
* [ ] Why directories behave differently
* [ ] Executable files
* [ ] Ownership
* [ ] Permission inheritance concepts

---

# 10. Users & Groups

* [ ] Current user
* [ ] `whoami`
* [ ] `id`
* [ ] `who`
* [ ] `w`
* [ ] `/etc/passwd`
* [ ] `/etc/group`
* [ ] `/etc/shadow`
* [ ] Create user
* [ ] `useradd`
* [ ] `adduser`
* [ ] Delete user
* [ ] Modify user
* [ ] Change password
* [ ] `passwd`
* [ ] Create group
* [ ] Add user to group
* [ ] Remove user from group
* [ ] `usermod`
* [ ] `groups`

---

# 11. Root & sudo

* [ ] Root user
* [ ] Why root is powerful
* [ ] `sudo`
* [ ] `sudo -i`
* [ ] `sudo su`
* [ ] `su`
* [ ] Root shell
* [ ] `/etc/sudoers`
* [ ] `visudo`
* [ ] Sudo permissions
* [ ] Least privilege
* [ ] Why not to run everything as root

---

# 12. Searching

* [ ] `find`
* [ ] `locate`
* [ ] `which`
* [ ] `whereis`
* [ ] `type`
* [ ] `command -v`
* [ ] Search by filename
* [ ] Search by extension
* [ ] Search by size
* [ ] Search by permissions
* [ ] Search by owner
* [ ] Search by modification time

### Practice

* [ ] Find large files
* [ ] Find recently modified files
* [ ] Find executable files
* [ ] Find configuration files

---

# 13. Text Processing

This is extremely important for Linux/server work.

* [ ] `grep`
* [ ] `grep -i`
* [ ] `grep -r`
* [ ] `grep -n`
* [ ] `grep -v`
* [ ] `grep -E`
* [ ] `sed`
* [ ] `awk`
* [ ] `cut`
* [ ] `sort`
* [ ] `uniq`
* [ ] `tr`
* [ ] `xargs`
* [ ] `tee`
* [ ] `diff`
* [ ] `comm`
* [ ] `join`

### Practice

* [ ] Search logs
* [ ] Extract columns
* [ ] Replace text
* [ ] Count occurrences
* [ ] Filter command output
* [ ] Transform text

---

# 14. Pipes & Redirection

Master these:

* [ ] `|`
* [ ] `>`
* [ ] `>>`
* [ ] `<`
* [ ] `2>`
* [ ] `2>>`
* [ ] `&>`
* [ ] `2>&1`
* [ ] `/dev/null`
* [ ] `tee`

### Practice

* [ ] Pipe one command into another
* [ ] Save output to file
* [ ] Append output
* [ ] Redirect errors
* [ ] Separate stdout/stderr
* [ ] Build command pipelines

---

# 15. Shell Variables

* [ ] Variables
* [ ] Environment variables
* [ ] `export`
* [ ] `unset`
* [ ] `$PATH`
* [ ] `$HOME`
* [ ] `$USER`
* [ ] `$PWD`
* [ ] `$SHELL`
* [ ] `$OLDPWD`
* [ ] `$?`
* [ ] `$0`
* [ ] `$1`
* [ ] `$@`
* [ ] `$#`
* [ ] `$*`

---

# 16. PATH

Understand this deeply:

* [ ] What is `$PATH`?
* [ ] How commands are found
* [ ] `which`
* [ ] `command -v`
* [ ] Add directory to PATH
* [ ] `.bashrc`
* [ ] `.profile`
* [ ] `.bash_profile`
* [ ] Permanent PATH changes
* [ ] Temporary PATH changes
* [ ] PATH security

---

# 17. Bash Scripting

This is where terminal knowledge becomes automation.

### Basics

* [ ] Create `.sh` file
* [ ] Shebang
* [ ] `#!/bin/bash`
* [ ] Execute script
* [ ] `chmod +x`
* [ ] Variables
* [ ] Strings
* [ ] Numbers
* [ ] Arrays
* [ ] Comments

### Conditions

* [ ] `if`
* [ ] `elif`
* [ ] `else`
* [ ] `case`
* [ ] String comparison
* [ ] Numeric comparison
* [ ] File tests

### Loops

* [ ] `for`
* [ ] `while`
* [ ] `until`
* [ ] `break`
* [ ] `continue`

### Functions

* [ ] Define functions
* [ ] Function arguments
* [ ] Return values
* [ ] Local variables

### Advanced

* [ ] `$?`
* [ ] `$@`
* [ ] `$#`
* [ ] `$1`
* [ ] Command substitution
* [ ] `$(command)`
* [ ] `&&`
* [ ] `||`
* [ ] `;`
* [ ] `set -e`
* [ ] `set -u`
* [ ] `set -x`
* [ ] `trap`

---

# 18. Process Management

* [ ] What is a process?
* [ ] PID
* [ ] PPID
* [ ] `ps`
* [ ] `ps aux`
* [ ] `top`
* [ ] `htop`
* [ ] `pgrep`
* [ ] `pkill`
* [ ] `kill`
* [ ] `killall`
* [ ] `nice`
* [ ] `renice`
* [ ] Foreground processes
* [ ] Background processes
* [ ] `&`
* [ ] `jobs`
* [ ] `fg`
* [ ] `bg`
* [ ] `nohup`
* [ ] `disown`

---

# 19. Signals

* [ ] What is a signal?
* [ ] SIGTERM
* [ ] SIGKILL
* [ ] SIGINT
* [ ] SIGHUP
* [ ] SIGSTOP
* [ ] SIGCONT
* [ ] `kill`
* [ ] Graceful termination
* [ ] Forced termination
* [ ] Signal handling in Bash

---

# 20. System Monitoring

* [ ] `top`
* [ ] `htop`
* [ ] `free`
* [ ] `uptime`
* [ ] `vmstat`
* [ ] `iostat`
* [ ] `lsof`
* [ ] `dmesg`
* [ ] `watch`
* [ ] `uname`
* [ ] `hostname`
* [ ] `date`
* [ ] `timedatectl`

### Monitor

* [ ] CPU
* [ ] RAM
* [ ] Disk
* [ ] Network
* [ ] Processes
* [ ] Load average
* [ ] System uptime

---

# 21. Disk Management

* [ ] `df`
* [ ] `df -h`
* [ ] `du`
* [ ] `du -sh`
* [ ] Disk usage
* [ ] Partitions
* [ ] Mount points
* [ ] `lsblk`
* [ ] `blkid`
* [ ] `mount`
* [ ] `umount`
* [ ] `/etc/fstab`
* [ ] Disk space troubleshooting
* [ ] Inodes
* [ ] `df -i`

---

# 22. Archives & Compression

* [ ] `tar`
* [ ] Create tar archive
* [ ] Extract tar archive
* [ ] `tar.gz`
* [ ] `tar.bz2`
* [ ] `tar.xz`
* [ ] `gzip`
* [ ] `gunzip`
* [ ] `zip`
* [ ] `unzip`
* [ ] Compression levels

### Practice

* [ ] Backup directory
* [ ] Compress logs
* [ ] Extract application files

---

# 23. Package Management — Ubuntu

* [ ] What is a package?
* [ ] APT
* [ ] `apt update`
* [ ] `apt upgrade`
* [ ] `apt install`
* [ ] `apt remove`
* [ ] `apt purge`
* [ ] `apt search`
* [ ] `apt show`
* [ ] `apt autoremove`
* [ ] `apt list`
* [ ] `apt-mark`
* [ ] Package repositories
* [ ] PPAs
* [ ] `.deb` packages
* [ ] `dpkg`
* [ ] Package dependencies

---

# 24. Snap

* [ ] What is Snap?
* [ ] `snap`
* [ ] Install Snap package
* [ ] Remove Snap package
* [ ] List Snap packages
* [ ] Update Snap packages
* [ ] Snap channels
* [ ] Snap permissions

---

# 25. Services & systemd

Extremely important for Ubuntu servers.

* [ ] What is a service?
* [ ] What is systemd?
* [ ] `systemctl`
* [ ] `systemctl status`
* [ ] `systemctl start`
* [ ] `systemctl stop`
* [ ] `systemctl restart`
* [ ] `systemctl reload`
* [ ] `systemctl enable`
* [ ] `systemctl disable`
* [ ] `systemctl is-active`
* [ ] `systemctl is-enabled`
* [ ] Service files
* [ ] Unit files
* [ ] Service dependencies
* [ ] Automatic startup
* [ ] Restart policies

### Build

* [ ] Run Node application as systemd service
* [ ] Automatically restart crashed application
* [ ] Start application on boot

---

# 26. Logs

* [ ] `/var/log`
* [ ] System logs
* [ ] Application logs
* [ ] `journalctl`
* [ ] `journalctl -f`
* [ ] `journalctl -u`
* [ ] Search logs
* [ ] Filter by time
* [ ] Filter by service
* [ ] Log rotation
* [ ] `logrotate`

### Practice

* [ ] Find application errors
* [ ] Monitor service logs
* [ ] Debug failed service

---

# 27. Networking Fundamentals

* [ ] IP address
* [ ] IPv4
* [ ] IPv6
* [ ] MAC address
* [ ] Subnet
* [ ] Gateway
* [ ] DNS
* [ ] DHCP
* [ ] TCP
* [ ] UDP
* [ ] Ports
* [ ] localhost
* [ ] `127.0.0.1`
* [ ] `0.0.0.0`
* [ ] Public vs private IP

---

# 28. Network Commands

* [ ] `ip`
* [ ] `ip addr`
* [ ] `ip route`
* [ ] `ip link`
* [ ] `ping`
* [ ] `ss`
* [ ] `netstat`
* [ ] `curl`
* [ ] `wget`
* [ ] `dig`
* [ ] `nslookup`
* [ ] `host`
* [ ] `traceroute`
* [ ] `tracepath`
* [ ] `nc`
* [ ] `telnet`

### Practice

* [ ] Find machine IP
* [ ] Find open ports
* [ ] Test connectivity
* [ ] Test DNS
* [ ] Test HTTP APIs
* [ ] Inspect network connections

---

# 29. SSH

One of the most important skills for backend/server development.

* [ ] What is SSH?
* [ ] SSH client
* [ ] SSH server
* [ ] `ssh`
* [ ] SSH username
* [ ] SSH hostname/IP
* [ ] SSH port
* [ ] SSH keys
* [ ] `ssh-keygen`
* [ ] Public key
* [ ] Private key
* [ ] `authorized_keys`
* [ ] `~/.ssh`
* [ ] `known_hosts`
* [ ] SSH config
* [ ] `~/.ssh/config`
* [ ] `scp`
* [ ] `sftp`
* [ ] SSH agent
* [ ] `ssh-agent`
* [ ] `ssh-add`
* [ ] Port forwarding
* [ ] Local forwarding
* [ ] Remote forwarding
* [ ] SSH tunneling

### Practice

* [ ] Connect to Ubuntu server
* [ ] Upload files
* [ ] Download files
* [ ] Run remote commands
* [ ] Configure SSH key authentication
* [ ] Secure SSH access

---

# 30. Firewall

* [ ] What is a firewall?
* [ ] UFW
* [ ] `ufw status`
* [ ] `ufw enable`
* [ ] `ufw disable`
* [ ] Allow port
* [ ] Deny port
* [ ] Delete firewall rule
* [ ] SSH firewall rules
* [ ] HTTP/HTTPS rules
* [ ] Default policies
* [ ] Firewall troubleshooting

### Advanced

* [ ] iptables concepts
* [ ] nftables concepts
* [ ] Firewall chains
* [ ] Firewall rules

---

# 31. Environment Configuration

* [ ] `.bashrc`
* [ ] `.profile`
* [ ] `.bash_aliases`
* [ ] Shell startup
* [ ] Aliases
* [ ] Functions
* [ ] Environment variables
* [ ] PATH
* [ ] Shell prompt
* [ ] Shell history configuration

### Build

* [ ] Custom aliases
* [ ] Developer shell configuration
* [ ] Project-specific commands

---

# 32. Git From Terminal

* [ ] `git init`
* [ ] `git clone`
* [ ] `git status`
* [ ] `git add`
* [ ] `git commit`
* [ ] `git log`
* [ ] `git diff`
* [ ] `git branch`
* [ ] `git switch`
* [ ] `git merge`
* [ ] `git rebase`
* [ ] `git stash`
* [ ] `git remote`
* [ ] `git fetch`
* [ ] `git pull`
* [ ] `git push`
* [ ] SSH authentication
* [ ] Resolve merge conflicts
* [ ] `.gitignore`

---

# 33. Process + Network Debugging

Learn to answer:

> "My Node server isn't working. What's wrong?"

* [ ] Is the process running?
* [ ] Find PID
* [ ] Check CPU
* [ ] Check RAM
* [ ] Check logs
* [ ] Check port
* [ ] Check firewall
* [ ] Check network interface
* [ ] Check DNS
* [ ] Check HTTP response
* [ ] Check permissions
* [ ] Check environment variables
* [ ] Check service status
* [ ] Check disk space

### Commands

* [ ] `ps`
* [ ] `top`
* [ ] `htop`
* [ ] `ss`
* [ ] `lsof`
* [ ] `journalctl`
* [ ] `systemctl`
* [ ] `curl`
* [ ] `ping`
* [ ] `df`
* [ ] `du`

---

# 34. Server Administration

* [ ] Create users
* [ ] Configure SSH
* [ ] Configure firewall
* [ ] Install packages
* [ ] Configure services
* [ ] Manage processes
* [ ] Monitor resources
* [ ] Manage logs
* [ ] Manage disks
* [ ] Configure networking
* [ ] Configure DNS
* [ ] Configure environment variables
* [ ] Schedule tasks
* [ ] Create backups
* [ ] Restore backups
* [ ] Security updates

---

# 35. Cron & Scheduled Tasks

* [ ] What is cron?
* [ ] `crontab`
* [ ] `crontab -e`
* [ ] `crontab -l`
* [ ] Cron syntax
* [ ] Minutes
* [ ] Hours
* [ ] Days
* [ ] Months
* [ ] Weekdays
* [ ] Cron environment
* [ ] Cron logs
* [ ] `at`
* [ ] System timers

### Build

* [ ] Automatic backup
* [ ] Log cleanup
* [ ] Database backup
* [ ] Scheduled script
* [ ] Health-check script

---

# 36. Backup & Restore

* [ ] Backup concepts
* [ ] File backup
* [ ] Directory backup
* [ ] `tar`
* [ ] `rsync`
* [ ] Incremental backup
* [ ] Remote backup
* [ ] SSH + rsync
* [ ] Database backup concepts
* [ ] Backup scheduling
* [ ] Backup verification
* [ ] Restore process

---

# 37. Rsync

* [ ] What is rsync?
* [ ] Local synchronization
* [ ] Remote synchronization
* [ ] `rsync -av`
* [ ] `rsync --delete`
* [ ] SSH + rsync
* [ ] Exclude patterns
* [ ] Incremental transfer
* [ ] Backup using rsync

---

# 38. Security Administration

* [ ] Strong passwords
* [ ] SSH keys
* [ ] Disable unnecessary services
* [ ] Firewall
* [ ] Security updates
* [ ] File permissions
* [ ] User permissions
* [ ] Sudo configuration
* [ ] SSH hardening
* [ ] Failed login monitoring
* [ ] Log monitoring
* [ ] File ownership
* [ ] Principle of least privilege
* [ ] Secrets management

---

# 39. System Information

* [ ] `uname`
* [ ] `hostname`
* [ ] `hostnamectl`
* [ ] `lsb_release`
* [ ] `/etc/os-release`
* [ ] `lscpu`
* [ ] `lsmem`
* [ ] `lsblk`
* [ ] `lspci`
* [ ] `lsusb`
* [ ] `free`
* [ ] `df`
* [ ] `uptime`

---

# 40. Advanced Shell

* [ ] Command substitution
* [ ] Process substitution
* [ ] Subshells
* [ ] Command chaining
* [ ] `&&`
* [ ] `||`
* [ ] `;`
* [ ] `|`
* [ ] Background jobs
* [ ] Job control
* [ ] Shell functions
* [ ] Aliases
* [ ] Here documents
* [ ] Here strings
* [ ] Quoting
* [ ] Single quotes
* [ ] Double quotes
* [ ] Escaping
* [ ] Globbing
* [ ] Wildcards
* [ ] Brace expansion
* [ ] Parameter expansion

---

# 41. Regex in Terminal

* [ ] Regular expressions
* [ ] Basic regex
* [ ] Extended regex
* [ ] `grep`
* [ ] `grep -E`
* [ ] `sed`
* [ ] `awk`
* [ ] Character classes
* [ ] Quantifiers
* [ ] Groups
* [ ] Anchors
* [ ] Search patterns
* [ ] Replace patterns

---

# 42. Advanced Linux Concepts

* [ ] Processes
* [ ] Threads
* [ ] File descriptors
* [ ] stdin
* [ ] stdout
* [ ] stderr
* [ ] Signals
* [ ] Sockets
* [ ] Pipes
* [ ] Named pipes
* [ ] Unix sockets
* [ ] `/proc`
* [ ] `/sys`
* [ ] `/dev`
* [ ] Kernel modules
* [ ] System calls
* [ ] Permissions
* [ ] Capabilities
* [ ] Namespaces
* [ ] cgroups

---

# 43. Containers Preparation

Before Docker, understand:

* [ ] Processes
* [ ] Namespaces
* [ ] cgroups
* [ ] Filesystems
* [ ] Networking
* [ ] Ports
* [ ] Environment variables
* [ ] Process isolation
* [ ] Resource limits
* [ ] Linux permissions

Then:

* [ ] Install Docker
* [ ] Understand Docker CLI
* [ ] Images
* [ ] Containers
* [ ] Volumes
* [ ] Networks
* [ ] Dockerfiles
* [ ] Container logs
* [ ] Container processes

---

# 44. Server Deployment

Learn to deploy a Node application manually.

* [ ] Create Ubuntu server
* [ ] Connect using SSH
* [ ] Create deployment user
* [ ] Configure SSH keys
* [ ] Update system
* [ ] Install Node.js
* [ ] Clone Git repository
* [ ] Install dependencies
* [ ] Configure environment variables
* [ ] Start application
* [ ] Create systemd service
* [ ] Configure firewall
* [ ] Configure logs
* [ ] Configure restart policy
* [ ] Configure domain
* [ ] Configure DNS
* [ ] Configure HTTPS
* [ ] Monitor application
* [ ] Perform updates
* [ ] Rollback deployment

---

# 45. Troubleshooting Skills

Learn to diagnose problems rather than blindly running commands.

### "Command not found"

* [ ] Check PATH
* [ ] `which`
* [ ] `command -v`
* [ ] Check installation

### "Permission denied"

* [ ] Check owner
* [ ] Check group
* [ ] Check permissions
* [ ] Check `sudo`
* [ ] Check filesystem mount

### "Port already in use"

* [ ] `ss`
* [ ] `lsof`
* [ ] Find PID
* [ ] Stop process

### "Server unreachable"

* [ ] Check IP
* [ ] Check network
* [ ] Check firewall
* [ ] Check SSH
* [ ] Check service
* [ ] Check DNS

### "Disk full"

* [ ] `df -h`
* [ ] `du`
* [ ] Find large files
* [ ] Check logs
* [ ] Check deleted-but-open files

### "Application crashed"

* [ ] Check process
* [ ] Check logs
* [ ] Check systemd
* [ ] Check memory
* [ ] Check environment
* [ ] Restart service
* [ ] Find root cause

---

# 46. Terminal Productivity

* [ ] Aliases
* [ ] Shell functions
* [ ] Command history
* [ ] History search
* [ ] Tab completion
* [ ] Custom prompt
* [ ] `tmux`
* [ ] Multiple terminal sessions
* [ ] Split panes
* [ ] Detachable sessions
* [ ] `watch`
* [ ] `time`
* [ ] `xargs`
* [ ] `tee`
* [ ] Command pipelines

---

# 47. tmux

* [ ] What is tmux?
* [ ] Create session
* [ ] Detach
* [ ] Attach
* [ ] List sessions
* [ ] Kill sessions
* [ ] Windows
* [ ] Panes
* [ ] Split panes
* [ ] Resize panes
* [ ] Navigate panes
* [ ] Rename sessions
* [ ] Persistent server sessions

---

# 48. Automation

* [ ] Bash scripts
* [ ] File automation
* [ ] Server setup scripts
* [ ] Backup scripts
* [ ] Deployment scripts
* [ ] Monitoring scripts
* [ ] Health checks
* [ ] Log cleanup
* [ ] Cron automation
* [ ] Error handling
* [ ] Exit codes
* [ ] Logging scripts

---

# 49. Practical Projects

### Beginner

* [ ] Terminal file manager
* [ ] CLI calculator
* [ ] CLI todo application
* [ ] File organizer
* [ ] Log analyzer
* [ ] System information script

### Intermediate

* [ ] Backup automation tool
* [ ] Server monitoring script
* [ ] Website uptime checker
* [ ] Log monitoring system
* [ ] CLI deployment tool
* [ ] File synchronization tool
* [ ] Process monitoring tool

### Advanced

* [ ] Mini process manager
* [ ] Custom shell
* [ ] Custom CLI framework
* [ ] Server health monitoring system
* [ ] Automated deployment system
* [ ] Backup + restore system
* [ ] Log aggregation system
* [ ] TCP diagnostic tool
* [ ] Network monitoring tool

---

# 50. Final Linux Terminal Mastery

* [ ] I can navigate Linux entirely from terminal
* [ ] I understand Linux filesystem
* [ ] I can create, copy, move and delete files
* [ ] I understand permissions
* [ ] I can manage users and groups
* [ ] I understand sudo
* [ ] I can search files
* [ ] I can process text with grep/sed/awk
* [ ] I understand pipes and redirection
* [ ] I can write Bash scripts
* [ ] I can manage processes
* [ ] I understand signals
* [ ] I can monitor CPU/RAM/disk
* [ ] I can manage disks
* [ ] I can install/remove packages
* [ ] I can manage systemd services
* [ ] I can read system logs
* [ ] I understand Linux networking
* [ ] I can diagnose ports and connections
* [ ] I can connect to servers using SSH
* [ ] I can configure a firewall
* [ ] I can schedule tasks with cron
* [ ] I can create backups
* [ ] I can automate repetitive tasks
* [ ] I can troubleshoot a Linux server
* [ ] I can deploy a Node.js application manually
* [ ] I understand the Linux concepts behind Docker
* [ ] I can manage an Ubuntu server without a GUI
