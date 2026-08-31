# Terminal Fundamentals

## What is a terminal?

A terminal is a text-based interface that allows users to interact with the operating system by typing commands. It provides a way to execute programs, manage files, and perform various tasks without using a graphical user interface (GUI).

Terminals are commonly used by developers, system administrators, and power users to perform tasks more efficiently and automate repetitive actions through scripts. They are available on most operating systems, including Linux, macOS, and Windows (via Command Prompt, PowerShell, or Windows Terminal).

## Terminal vs shell

A terminal is often confused with a shell, but they are not the same thing. A terminal is the interface that allows you to interact with the system, while a shell is the program that interprets and executes the commands you type in the terminal. Common shells include Bash, Zsh, and PowerShell.

## What is a shell?

A shell is a program that provides an interface for users to interact with the operating system by interpreting and executing commands. It can be used to run programs, manage files, and automate tasks through scripts. Common shells include Bash, Zsh, and PowerShell.

## Common shell commands

Here are some commonly used shell commands:

- `ls` : Lists the files and directories in the current directory (use `dir` on Windows).
- `cd <directory>` : Changes the current directory to the specified directory.
- `pwd` : Prints the current working directory.
- `mkdir <directory>` : Creates a new directory with the specified name.
- `rm <file>` : Deletes the specified file (use `del <file>` on Windows).
- `rmdir <directory>` : Deletes the specified directory (use `rd <directory>` on Windows).
- `cp <source> <destination>` : Copies a file from the source to the destination (use `copy` on Windows).
- `mv <source> <destination>` : Moves or renames a file (use `move` on Windows).
- `echo <text>` : Prints the specified text to the terminal.
- `cat <file>` : Displays the contents of a file (use `type <file>` on Windows).

## Bash

Bash (Bourne Again SHell) is a popular Unix shell and command language. It is widely used on Linux and macOS systems and is available on Windows through Windows Subsystem for Linux (WSL) or Git Bash. Bash provides powerful features for command-line interaction, scripting, and automation.

Some common Bash features include:

- Command history and tab completion.
- Variables and environment management.
- Control structures like loops and conditionals.
- Functions for reusable code blocks.
- Redirection and piping for input/output management.

## Zsh

Zsh (Z Shell) is an extended version of the Bourne shell (sh) with many improvements and additional features. It is known for its powerful scripting capabilities, customizable prompts, and advanced tab completion. Zsh is popular among developers who want a more feature-rich shell experience compared to Bash.

Some common Zsh features include:

- Advanced tab completion and command correction.
- Customizable prompts and themes (often used with Oh My Zsh).
- Enhanced scripting capabilities and built-in functions.
- Plugin support for extending functionality.
- Compatibility with Bash scripts.

## PowerShell

PowerShell is a task automation and configuration management framework from Microsoft, consisting of a command-line shell and associated scripting language. It is designed for system administrators and power users to automate tasks and manage system configurations. PowerShell is available on Windows, macOS, and Linux.

Some common PowerShell features include:

- Cmdlets for performing various system tasks.
- Pipeline support for chaining commands.
- Advanced scripting capabilities with functions and modules.
- Access to .NET framework for extended functionality.
- Remote management and automation capabilities.

## Terminal emulator
A terminal emulator is a software application that provides a text-based interface for interacting with the operating system's shell. It allows users to run shell commands, execute scripts, and manage system tasks from a graphical or text-based environment.

Some popular terminal emulators include:

- GNOME Terminal (Linux)
- Konsole (Linux)
- iTerm2 (macOS)
- Terminal.app (macOS)
- Windows Terminal (Windows)
- Alacritty (cross-platform)
- Tilix (Linux)
- Hyper (cross-platform)
- Kitty (cross-platform)

## CLI vs GUI

The Command-Line Interface (CLI) and Graphical User Interface (GUI) are two different ways for users to interact with a computer system.

- **CLI (Command-Line Interface):**
  - Users interact with the system by typing text commands.
  - Provides powerful scripting and automation capabilities.
  - Often preferred by advanced users and system administrators.
  - Examples: Bash, Zsh, PowerShell.

- **GUI (Graphical User Interface):**
  - Users interact with the system through graphical elements like windows, icons, and buttons.
  - Easier for beginners and general users to navigate.
  - Typically less efficient for repetitive tasks compared to CLI.
  - Examples: Windows Desktop, macOS Finder, GNOME Desktop.


## Command structure

A typical command in a CLI follows a specific structure:

```
command [options] [arguments]
```

- **command**: The program or utility to be executed.
- **options**: Modifiers that change the behavior of the command (usually prefixed with `-` or `--`).
- **arguments**: The targets or inputs for the command (such as files or directories).

Example:

```
ls -l /home/user
```

- `ls` is the command to list directory contents.
- `-l` is an option to display detailed information.
- `/home/user` is the argument specifying the directory to list.

## Command arguments

Command arguments are the inputs provided to a command to specify what the command should act upon. They can be files, directories, or other data depending on the command.

For example, in the command:

```
cp file1.txt /home/user/Documents/
```

- `cp` is the command to copy files.
- `file1.txt` is the argument specifying the source file.
- `/home/user/Documents/` is the argument specifying the destination directory.

## Options/flags

Options or flags are used to modify the behavior of a command. They are usually prefixed with a single dash (`-`) for short options or a double dash (`--`) for long options.

For example, in the command:

```
ls -l --color=auto /home/user
```

- `-l` is a short option to display detailed information.
- `--color=auto` is a long option to enable colored output.
- `/home/user` is the argument specifying the directory to list.

## Short flags

Short flags are single-character options prefixed with a single dash (`-`). Multiple short flags can often be combined after a single dash.

For example, in the command:

```
ls -la /home/user
```

- `-l` is a short flag to display detailed information.
- `-a` is a short flag to include hidden files.
- `/home/user` is the argument specifying the directory to list.

## Long flags

Long flags are multi-character options prefixed with a double dash (`--`). They are usually more descriptive than short flags.

For example, in the command:

```
ls --all --color=auto /home/user
```

- `--all` is a long flag to include hidden files.
- `--color=auto` is a long flag to enable colored output.
- `/home/user` is the argument specifying the directory to list.

## Command output

Command output is the information displayed by the command after it is executed. It can include text, error messages, or other data depending on the command.

For example, in the command:

```
ls -l /home/user
```

The output might look like:

```
total 4
-rw-r--r-- 1 user user  0 Jan  1 12:00 file1.txt
-rw-r--r-- 1 user user  0 Jan  1 12:00 file2.txt
```

- The first line shows the total number of blocks used by the files.
- Each subsequent line shows detailed information about a file, including permissions, number of links, owner, group, size, modification date, and filename.

Understanding command output is crucial for interpreting the results of commands and for troubleshooting issues in the terminal.

## Exit status

The exit status is a numeric value returned by a command to indicate its success or failure. By convention, an exit status of `0` indicates success, while any non-zero value indicates an error.

For example, after running a command:

```
echo $?
```

The output will be the exit status of the previously executed command.

- An exit status of `0` indicates that the command was successful.
- A non-zero exit status indicates that an error occurred. The specific non-zero value can provide information about the type of error, depending on the command.

## `0` success

An exit status of `0` indicates that the command was successful. This means that the command completed its task without any errors.

For example:

```
ls /home/user
echo $?
```

If the `ls` command executes successfully, the output of `echo $?` will be:

```
0
```

## Non-zero failure

An exit status other than `0` indicates that the command failed. The specific non-zero value can provide information about the type of error, depending on the command.

For example:

```
ls /nonexistent_directory
echo $?
```

If the `ls` command fails because the directory does not exist, the output of `echo $?` will be a non-zero value, typically:

```
2
```

Understanding exit statuses is important for scripting and automation, as it allows you to check whether commands succeeded or failed and take appropriate actions based on the result.

## `$?`

The special variable `$?` holds the exit status of the last executed command. It allows you to check whether the previous command succeeded or failed.

For example:

```
ls /home/user
echo $?
```

If the `ls` command executes successfully, `echo $?` will output `0`. If it fails, it will output a non-zero value.

## Command history

The terminal keeps a history of commands that have been executed. This allows you to recall and reuse previous commands without retyping them.

For example, you can use the `history` command to view the list of previously executed commands:

```
history
```

You can also use the up and down arrow keys to navigate through your command history and edit or re-execute previous commands.

You can also search through your command history using `Ctrl + R` and typing a part of the command you want to find. This will allow you to quickly locate and reuse previous commands without scrolling through the entire history.

For example:

```
Ctrl + R
(reverse-i-search)`ls': ls /home/user
```

This will show the most recent command that matches the search term, and you can press `Enter` to execute it again.

You can continue pressing `Ctrl + R` to cycle through earlier matches for the search term. This makes it easy to find and reuse commands from your history without manually scrolling through the list.

To exit the reverse search without executing a command, you can press `Ctrl + G`. This will cancel the search and return you to the normal command prompt.


## Tab completion

Tab completion is a feature in the terminal that allows you to quickly complete file names, directory names, and commands by pressing the `Tab` key. This can save time and reduce typing errors.

For example, if you have a directory `/home/user/Documents` and you type:

```
cd /home/user/Doc
```

Pressing the `Tab` key will automatically complete the directory name:

```
cd /home/user/Documents
```

If there are multiple possible completions, pressing `Tab` twice will show a list of all possible matches:

```
cd /home/user/Doc<Tab><Tab>
Documents/  Downloads/
```

You can then continue typing to narrow down the options and press `Tab` again to complete the name.

## Ctrl+C

`Ctrl+C` is a keyboard shortcut used to interrupt or terminate a running command in the terminal. This is useful when a command is taking too long to execute or if you want to stop it for any reason.

For example, if you start a long-running command:

```
ping google.com
```

You can press `Ctrl+C` to stop the command:

```
^C
```

The `^C` indicates that the command was interrupted by the user.

## Ctrl+D

`Ctrl+D` is a keyboard shortcut used to signal the end of input or to log out of the terminal session. When used in the terminal, it sends an EOF (End Of File) signal to the current process.

For example, if you are using the `cat` command to read input from the terminal:

```
cat
```

You can type some text and then press `Ctrl+D` to indicate the end of input:

```
Hello, world!
^D
```

The `^D` indicates that the end of input has been reached. If you are at the command prompt, pressing `Ctrl+D` will log you out of the terminal session.

## Ctrl+Z

`Ctrl+Z` is a keyboard shortcut used to suspend a running command in the terminal. This allows you to temporarily stop a command and resume it later using the `fg` command.

For example, if you start a long-running command:

```
ping google.com
```

You can press `Ctrl+Z` to suspend the command:

```
^Z
[1]+  Stopped                 ping google.com
```

The `^Z` indicates that the command was suspended. You can resume the command in the foreground by using:

```
fg
```

The `fg` command brings the suspended command back to the foreground, allowing it to continue execution.

## Ctrl+L

`Ctrl+L` is a keyboard shortcut used to clear the terminal screen. This can help you remove clutter and focus on the current task.

For example, if your terminal is filled with previous commands and output:

```
ls
Documents  Downloads  Pictures
ping google.com
^C
```

Pressing `Ctrl+L` will clear the screen:

```
```

The terminal is now cleared, and you can continue working with a clean screen.

## Ctrl+A

`Ctrl+A` is a keyboard shortcut used to move the cursor to the beginning of the line in the terminal. This can be useful when you want to quickly navigate to the start of a long command.

For example, if you have typed a long command:

```
echo "This is a long command"
```

Pressing `Ctrl+A` will move the cursor to the beginning of the line:

```
^echo "This is a long command"
```

You can then continue editing the command from the start.

## Ctrl+E

`Ctrl+E` is a keyboard shortcut used to move the cursor to the end of the line in the terminal. This can be useful when you want to quickly navigate to the end of a long command.

For example, if you have typed a long command:

```
echo "This is a long command"
```

Pressing `Ctrl+E` will move the cursor to the end of the line:

```
echo "This is a long command"^
```

You can then continue editing the command from the end.

## Ctrl+R

`Ctrl+R` is a keyboard shortcut used to search through the command history in the terminal. This allows you to quickly find and reuse previously executed commands.

For example, if you want to search for a command that contains the word "ping":

```
Ctrl+R
(reverse-i-search)`': ping
```

As you type, the terminal will display the most recent matching command. You can press `Ctrl+R` again to cycle through earlier matches. Once you find the desired command, you can press `Enter` to execute it or use the arrow keys to edit it before execution.

## Ctrl+U

`Ctrl+U` is a keyboard shortcut used to delete the text from the cursor position to the beginning of the line in the terminal. This can be useful when you want to quickly remove a portion of a command.

For example, if you have typed a long command:

```
echo "This is a long command"
```

Pressing `Ctrl+U` will delete the text from the cursor to the beginning of the line:

```
^
```

You can then continue typing a new command from the start of the line.

## Ctrl+K

`Ctrl+K` is a keyboard shortcut used to delete the text from the cursor position to the end of the line in the terminal. This can be useful when you want to quickly remove a portion of a command.

For example, if you have typed a long command:

```
echo "This is a long command"
```

Pressing `Ctrl+K` will delete the text from the cursor to the end of the line:

```
echo "^
```

You can then continue typing a new command from the current cursor position.

## Ctrl+W

`Ctrl+W` is a keyboard shortcut used to delete the word before the cursor in the terminal. This can be useful when you want to quickly remove a portion of a command.

For example, if you have typed a long command:

```
echo "This is a long command"
```

Pressing `Ctrl+W` will delete the word before the cursor:

```
echo "This is a long "
```

You can then continue typing a new command from the current cursor position.

## Ctrl+Y

`Ctrl+Y` is a keyboard shortcut used to paste the text that was most recently deleted using `Ctrl+U`, `Ctrl+K`, or `Ctrl+W` in the terminal. This can be useful when you want to quickly restore a portion of a command.

For example, if you have deleted a portion of a command using `Ctrl+U`:

```
^
```

Pressing `Ctrl+Y` will paste the previously deleted text:

```
echo "This is a long command"
```

You can then continue editing the command from the current cursor position.

# Linux Basics

## What is Linux?

Linux is an open-source operating system that is widely used for servers, desktops, and embedded systems. It is known for its stability, security, and flexibility. Linux provides a command-line interface (CLI) as well as graphical user interfaces (GUIs) for interacting with the system.

## Linux Kernel

The Linux kernel is the core component of the Linux operating system. It manages the system's hardware, including the CPU, memory, and peripheral devices, and provides essential services to the software running on the system. The kernel is responsible for process management, memory management, device drivers, and system calls, making it a critical part of the operating system.

## GNU/Linux

GNU/Linux, often referred to simply as Linux, is a combination of the GNU software and the Linux kernel. The GNU project provides essential system utilities and libraries, while the Linux kernel handles hardware interactions and core system functions. Together, they form a complete operating system that is widely used in various computing environments.

## Ubuntu

Ubuntu is a popular Linux distribution based on Debian. It is known for its user-friendliness, regular release cycle, and strong community support. Ubuntu provides both desktop and server editions, making it suitable for a wide range of users, from beginners to experienced professionals. It includes a wide array of pre-installed software and has access to extensive repositories for additional applications.

## Ubuntu Server

Ubuntu Server is the server edition of the Ubuntu operating system. It is optimized for use on servers and provides a robust platform for deploying web servers, databases, and other server applications. Ubuntu Server is known for its stability, security, and ease of maintenance, making it a popular choice for both small and large-scale server deployments.

## Linux Distributions

Linux distributions, often referred to as distros, are different versions of the Linux operating system that include the Linux kernel, GNU utilities, and additional software tailored for specific use cases. Popular Linux distributions include Ubuntu, Debian, Fedora, CentOS, and Arch Linux. Each distribution has its own package management system, release cycle, and community support, catering to various user needs and preferences.

## Kernel vs distribution

The Linux kernel is the core component of the operating system that interacts directly with the hardware and manages system resources. A Linux distribution, on the other hand, is a complete operating system that includes the Linux kernel along with GNU utilities, libraries, and additional software. While the kernel provides the essential functionality, the distribution packages it with user-space tools and applications to create a usable system for end users.

## Root user

The root user, also known as the superuser, is a special user account in Linux with full administrative privileges. The root user has the ability to perform any action on the system, including installing and removing software, modifying system configurations, and managing other user accounts. Due to its extensive permissions, it is recommended to use the root account sparingly and perform regular tasks using a standard user account with limited privileges.

## Sudo

Sudo (short for "superuser do") is a command in Linux that allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. It provides a way to perform administrative tasks without logging in as the root user, thereby reducing the risk of accidental system-wide changes. Users must be granted sudo privileges to use the command, and it typically requires entering the user's password for authentication.

## Normal User

A normal user, also known as a standard user, is an account in Linux with limited privileges. Normal users can perform everyday tasks such as running applications, managing personal files, and changing their own settings, but they cannot make system-wide changes or access other users' files without permission. This separation of privileges helps maintain system security and stability by preventing accidental or unauthorized modifications to critical system components.

## Home directory

The home directory is a personal directory assigned to each user in a Linux system. It serves as the primary location for storing a user's files, configurations, and personal data. The home directory is typically located at `/home/username`, where `username` is the name of the user. Standard users have full access to their own home directories but have limited or no access to other users' home directories, ensuring privacy and security.

## Root's Home Directory

The root user's home directory is typically located at `/root`. Unlike normal users, the root user has unrestricted access to all files and directories on the system. The root home directory contains configuration files and personal data specific to the root user. It is important to exercise caution when working in the root home directory, as changes made here can affect the entire system.

## Filesystem

The filesystem in Linux is a hierarchical structure that organizes and stores files and directories on the system. At the top of the hierarchy is the root directory, denoted by `/`, which contains all other files and directories. The filesystem includes various standard directories such as `/bin` for essential binaries, `/etc` for configuration files, `/var` for variable data, and `/home` for user home directories. Understanding the filesystem structure is crucial for navigating, managing, and maintaining a Linux system effectively.

## Processes

In Linux, a process is an instance of a running program. Each process is assigned a unique process ID (PID) and has its own memory space and system resources. Processes can be managed using various commands such as `ps` to list running processes, `top` to monitor system performance, `kill` to terminate processes, and `nice` to adjust process priority. Understanding and managing processes is essential for maintaining system performance and stability.

## Services

In Linux, a service (also known as a daemon) is a background process that runs continuously to perform specific tasks or provide system functionality. Services can include web servers, database servers, and system monitoring tools. They are typically managed using commands such as `systemctl` to start, stop, enable, or disable services. Proper management of services is important for ensuring system reliability, security, and performance.

## Packages

In Linux, a package is a collection of files and metadata that together provide a specific piece of software or functionality. Packages are managed by package managers, which handle the installation, upgrade, and removal of software on the system. Common package managers include `apt` for Debian-based distributions, `yum` or `dnf` for Red Hat-based distributions, and `pacman` for Arch Linux. Proper package management ensures that software is installed correctly, dependencies are resolved, and the system remains secure and up-to-date.

## Daemons

In Linux, a daemon is a background process that runs independently of user interaction, typically to perform system-level tasks or provide services. Daemons are often started at boot time and continue running until the system is shut down. Examples of daemons include `sshd` for handling SSH connections, `httpd` for serving web pages, and `cron` for scheduling tasks. Managing daemons properly is important for system stability, security, and performance.

## Shell

In Linux, the shell is a command-line interface that allows users to interact with the operating system by executing commands. The shell interprets user input and translates it into actions performed by the kernel. Common shells include `bash` (Bourne Again Shell), `zsh` (Z Shell), and `fish` (Friendly Interactive Shell). The shell provides powerful features such as scripting, command history, and job control, making it an essential tool for system administration and automation.

# Filesystem Hierarchy
The Linux filesystem hierarchy is organized into a structured directory tree, with each directory serving a specific purpose. Understanding the filesystem hierarchy is important for system administration, navigation, and file management. Key directories include:

## /

The root directory `/` is the top-level directory in the Linux filesystem hierarchy. It contains all other directories and files on the system. Key subdirectories under `/` include:
- `/home` - Contains the home directories of individual users. Each user typically has a subdirectory under `/home` where personal files, configuration settings, and user-specific data are stored.
- `/root` - The home directory of the root user (the system administrator). It contains configuration files and personal data specific to the root user.
- `/etc` - Contains system-wide configuration files and directories. These files control the behavior of various system services and applications.
- `/var` - Contains variable data files, such as logs, databases, and spool files. The contents of this directory are expected to change frequently during system operation.
- `/var/log` - Contains log files generated by the system and various applications. These logs are useful for monitoring system activity, troubleshooting issues, and auditing security events.
- `/usr` - Contains user-related programs and data. This directory is typically used for installing software and storing shared resources for all users. Subdirectories include `/usr/bin` for executable binaries, `/usr/lib` for libraries, and `/usr/share` for shared data.
- `/usr/bin` - Contains executable binaries for user programs. This directory is part of the system's `PATH` environment variable, allowing users to run programs without specifying their full path.
- `/usr/sbin` - Contains system administration binaries that are typically intended to be run by the root user. This directory is also part of the system's `PATH` environment variable for the root user.
- `/bin` - Contains essential command binaries that are required for the system to boot and run in single-user mode. This directory is part of the system's `PATH` environment variable, allowing users to run these commands without specifying their full path.
- `/sbin` - Contains essential system binaries that are typically intended to be run by the root user for system administration tasks. This directory is part of the system's `PATH` environment variable for the root user.
- `/opt` - Contains optional software packages and third-party applications. This directory is typically used for installing software that is not part of the default system installation.
- `/tmp` - Contains temporary files created by system processes and users. Files in this directory are typically deleted upon system reboot or after a certain period of time.
- `/dev` - Contains device files that represent hardware devices and virtual devices. These files provide an interface for the kernel and user-space programs to interact with the hardware. Examples include `/dev/sda` for a hard disk and `/dev/tty` for terminal devices.
- `/proc` - Contains virtual files that provide information about the system and running processes. This directory is part of the proc filesystem and is used for accessing kernel and process information in a hierarchical manner. Examples include `/proc/cpuinfo` for CPU information and `/proc/meminfo` for memory usage.
- `/sys` - Contains virtual files that provide information about the system's hardware and kernel subsystems. This directory is part of the sysfs filesystem and is used for accessing and configuring hardware devices and kernel parameters. Examples include `/sys/class` for device classes and `/sys/block` for block devices.
- `/run` - Contains runtime data for system processes and services. This directory is typically used for storing PID files, sockets, and other transient files that are needed during system operation. The contents of this directory are usually cleared upon system reboot.
- `/mnt` - Contains mount points for temporarily mounting filesystems, such as external drives, network shares, or other storage devices. This directory is commonly used for manual mounting of filesystems.
- `/media` - Contains mount points for removable media, such as USB drives, CDs, and DVDs. This directory is commonly used for automatically mounting removable storage devices.
- `/boot` - Contains the files required for the system to boot, including the Linux kernel, initial RAM disk (initrd or initramfs), and bootloader configuration files. This directory is typically mounted separately to ensure that the boot files are accessible during the boot process.
- `/lib` - Contains essential shared libraries and kernel modules required for the system to boot and run. This directory is typically used by the binaries in `/bin` and `/sbin`. Subdirectories include `/lib/modules` for kernel modules and `/lib/systemd` for systemd-related libraries.
- `/snap` - Contains the files related to Snap packages, which are self-contained software packages that include all the dependencies required to run an application. This directory is used by the Snap package management system to store installed snaps and their associated data.

# Navigation

## pwd

The `pwd` command stands for "print working directory" and is used to display the current directory you are in within the terminal.

```bash
pwd
```


## ls

The `ls` command is used to list the contents of a directory. By default, it displays the names of files and directories in the current directory.

```bash
ls
```

## ls -l

The `ls -l` command is used to list the contents of a directory in long format. It provides detailed information about each file and directory, including permissions, number of links, owner, group, size, and modification date.

```bash
ls -l
```

## ls -a

The `ls -a` command is used to list all the contents of a directory, including hidden files and directories (those starting with a dot `.`).

```bash
ls -a
```

## ls -la

The `ls -la` command is used to list all the contents of a directory in long format, including hidden files and directories. It combines the functionality of `ls -l` and `ls -a`.

```bash
ls -la
```

## ls -lah

The `ls -lah` command is used to list all the contents of a directory in long format, including hidden files and directories, with human-readable file sizes (e.g., KB, MB, GB). It combines the functionality of `ls -l`, `ls -a`, and adds the `-h` option for human-readable sizes.

```bash
ls -lah
```

## cd

The `cd` command stands for "change directory" and is used to navigate between directories in the terminal.

```bash
cd /path/to/directory
```

## cd ..

The `cd ..` command is used to navigate to the parent directory of the current directory.

```bash
cd ..
```

## cd ~

The `cd ~` command is used to navigate to the home directory of the current user.

```bash
cd ~
```

## cd -

The `cd -` command is used to navigate to the previous directory you were in.

```bash
cd -
```

## Absolute paths

An absolute path is a complete path from the root directory (`/`) to the desired file or directory. It specifies the location of a file or directory regardless of the current working directory.

```bash
cd /home/user/Documents
```

## Relative paths

A relative path specifies the location of a file or directory in relation to the current working directory. It does not start with a `/` and is interpreted relative to the current directory.

```bash
cd Documents
```

## .

The `.` (dot) represents the current directory. It can be used in commands to refer to the current directory explicitly.

```bash
cd .
```

## ..

The `..` (double dot) represents the parent directory. It can be used in commands to refer to the parent directory explicitly.

```bash
cd ..
```

## ~

The `~` (tilde) represents the home directory of the current user. It can be used in commands to refer to the home directory explicitly.

```bash
cd ~
```

# Creating Files & Directories

## touch

The `touch` command is used to create an empty file or update the timestamp of an existing file.

```bash
touch filename.txt
```

## mkdir

The `mkdir` command is used to create a new directory.

```bash
mkdir new_directory
```

## mkdir -p

The `mkdir -p` command is used to create a new directory along with any necessary parent directories. If the parent directories do not exist, they will be created automatically.

```bash
mkdir -p parent_directory/child_directory
```

## Create nested directories

The `mkdir -p` command can be used to create nested directories in a single command. This is useful when you need to create a directory structure with multiple levels.

```bash
mkdir -p parent_directory/child_directory/grandchild_directory
```

## Create multiple files

The `touch` command can be used to create multiple files at once by specifying multiple filenames separated by spaces.

```bash
touch file1.txt file2.txt file3.txt
```

## Create multiple directories

The `mkdir` command can be used to create multiple directories at once by specifying multiple directory names separated by spaces.

```bash
mkdir dir1 dir2 dir3
```

## Hidden files

Hidden files are files whose names start with a dot (`.`). They are not displayed by default when listing files in a directory.

```bash
touch .hidden_file.txt
```

## File extensions

File extensions indicate the type of a file and are usually found at the end of the filename, following a dot (`.`). Common file extensions include `.txt` for text files, `.jpg` for images, and `.sh` for shell scripts.

```bash
touch file.txt
touch image.jpg
touch script.sh
```

## Files without extensions

Files without extensions do not have a dot (`.`) followed by a file type at the end of the filename. They are treated as generic files by the system.

```bash
touch file_without_extension
```

# Copy, Move & Delete

## cp

The `cp` command is used to copy files or directories from one location to another.

```bash
cp source_file.txt destination_file.txt
```

## cp -r

The `cp -r` command is used to copy directories recursively, including all their contents.

```bash
cp -r source_directory destination_directory
```

## cp -a

The `cp -a` command is used to copy files and directories while preserving their attributes, such as timestamps, symbolic links, and permissions.

```bash
cp -a source_directory destination_directory
```

## mv

The `mv` command is used to move or rename files and directories.

```bash
mv source_file.txt destination_file.txt
```

## rm

The `rm` command is used to delete files or directories.

```bash
rm file.txt
```

## rm -r

The `rm -r` command is used to delete directories and their contents recursively.

```bash
rm -r directory_name
```

## rm -f

The `rm -f` command is used to forcefully delete files without prompting for confirmation, even if the files are write-protected.

```bash
rm -f file.txt
```

## rmdir

The `rmdir` command is used to delete empty directories.

```bash
rmdir empty_directory
```

## Understand dangerous rm -rf

The `rm -rf` command is extremely powerful and dangerous. It forcefully deletes files and directories recursively without any confirmation. Using it carelessly can result in permanent data loss.

```bash
rm -rf directory_name
```

## Rename files
The `mv` command can also be used to rename files.

```bash
mv old_filename.txt new_filename.txt
```

## Rename directories

The `mv` command can also be used to rename directories.

```bash
mv old_directory_name new_directory_name
```

## Move files

The `mv` command is used to move files from one location to another.

```bash
mv source_file.txt destination_directory/
```

## Copy directories

The `cp -r` command is used to copy directories and their contents recursively.

```bash
cp -r source_directory destination_directory
```

## Delete directories

The `rm -r` command is used to delete directories and their contents recursively.

```bash
rm -r directory_name
```

# Reading Files

## Cat

The `cat` command is used to display the contents of a file.

```bash
cat file.txt
```

## less

The `less` command is used to view the contents of a file one screen at a time. It allows for easy navigation through large files.

```bash
less file.txt
```

## more

The `more` command is used to view the contents of a file one screen at a time, similar to `less`, but with fewer navigation features.

```bash
more file.txt
```

## head

The `head` command is used to display the first few lines of a file.

```bash
head file.txt
```

## tail

The `tail` command is used to display the last few lines of a file.

```bash
tail file.txt
```

## tail -f

The `tail -f` command is used to continuously monitor the end of a file in real-time. It is commonly used to watch log files as they are updated.

```bash
tail -f file.txt
```

## nl

The `nl` command is used to display the contents of a file with line numbers.

```bash
nl file.txt
```

## wc

The `wc` command is used to display the word count, line count, and byte count of a file.

```bash
wc file.txt
```

## file

The `file` command is used to determine the type of a file.

```bash
file file.txt
```

## stat

The `stat` command is used to display detailed information about a file, including its size, permissions, and modification times.

```bash
stat file.txt
```

## Read configuration files

Configuration files are typically read using commands like `cat`, `less`, or `more`.

```bash
cat /etc/config_file.conf
```

```bash
less /etc/config_file.conf
```

```bash
more /etc/config_file.conf
```

## Read log files

Log files are typically read using commands like `cat`, `less`, `more`, or `tail -f`.

```bash
cat /var/log/log_file.log
```

```bash
less /var/log/log_file.log
```

```bash
more /var/log/log_file.log
```

```bash
tail -f /var/log/log_file.log
```

## Monitor logs in real time

The `tail -f` command is commonly used to monitor log files in real time, allowing you to see new entries as they are added.

```bash
tail -f /var/log/log_file.log
```

## Inspect file metadata

The `stat` command is used to display detailed information about a file, including its size, permissions, and modification times.

```bash
stat file.txt
```

# Editing files

## Nano

The `nano` command is used to edit files in the terminal using the Nano text editor.

```bash
nano file.txt
```

## Vim

The `vim` command is used to edit files in the terminal using the Vim text editor.

```bash
vim file.txt
```

## open file

The `xdg-open` command is used to open a file with the default application associated with its file type.

```bash
xdg-open file.txt
```

## edit file

The `xdg-open` command can also be used to open a file for editing with the default application associated with its file type.

```bash
xdg-open file.txt
```

## Save file
The `cp` command can be used to save a file by copying it to a new location or with a new name.

```bash
cp file.txt /path/to/new_location/file.txt
```

## Exit editor

To exit a text editor like Nano or Vim, you can use the following commands:

### Nano

Press `Ctrl + X` to exit Nano. If you have unsaved changes, Nano will prompt you to save them.

### Vim

In Vim, press `Esc` to enter command mode, then type `:q` to quit. If you have unsaved changes, use `:q!` to quit without saving or `:wq` to save and quit.

## Search inside files

The `grep` command is used to search for specific patterns within files.

```bash
grep "search_pattern" file.txt
```

## Replace text

The `sed` command is commonly used to replace text within files.

```bash
sed -i 's/old_text/new_text/g' file.txt
```

## Copy/paste

The `cp` command is used to copy files, which can be considered as a way to "paste" the file to a new location.

```bash
cp file.txt /path/to/destination/file.txt
```

## Vim modes

Vim has different modes for different types of interactions:

- **Normal mode**: Used for navigation and command execution. Press `Esc` to enter normal mode.
- **Insert mode**: Used for inserting text. Press `i` to enter insert mode from normal mode.
- **Visual mode**: Used for selecting text. Press `v` to enter visual mode from normal mode.
- **Command-line mode**: Used for executing commands like saving and quitting. Press `:` to enter command-line mode from normal mode.

### Switching between modes

- To switch from **Normal mode** to **Insert mode**, press `i`.
- To switch from **Insert mode** to **Normal mode**, press `Esc`.
- To switch from **Normal mode** to **Visual mode**, press `v`.
- To switch from **Visual mode** to **Normal mode**, press `Esc`.
- To switch from **Normal mode** to **Command-line mode**, press `:`.
- To switch from **Command-line mode** to **Normal mode**, press `Esc`.

## Vim commands

Vim has several commands that are useful for editing and navigating text:

- `:w` - Save the current file.
- `:q` - Quit Vim.
- `:wq` - Save and quit Vim.
- `:q!` - Quit Vim without saving changes.
- `:e filename` - Open a new file for editing.
- `:set number` - Show line numbers.
- `:set nonumber` - Hide line numbers.

## Vim navigation commands

- `h` - Move the cursor left.
- `j` - Move the cursor down.
- `k` - Move the cursor up.
- `l` - Move the cursor right.
- `0` - Move to the beginning of the current line.
- `^` - Move to the first non-blank character of the current line.
- `$` - Move to the end of the current line.
- `gg` - Move to the beginning of the file.
- `G` - Move to the end of the file.
- `w` - Move to the beginning of the next word.
- `b` - Move to the beginning of the previous word.
- `e` - Move to the end of the current word.
- `ge` - Move to the end of the previous word.

## Vim Configuration

Vim can be customized through a configuration file called `.vimrc`. This file allows you to set various options and define custom key mappings.

Example `.vimrc`:

```vim
" Enable line numbers
set number

" Enable syntax highlighting
syntax on

" Set tabs to 4 spaces
set tabstop=4
set shiftwidth=4
set expandtab
```

# File Permissions

File permissions in Unix-like systems determine who can read, write, or execute a file. Each file has three types of permissions for three categories of users:

- **Owner**: The user who owns the file.
- **Group**: The group that owns the file.
- **Others**: All other users.

The permissions are represented as a combination of `r` (read), `w` (write), and `x` (execute).

## Viewing file permissions

Use the `ls -l` command to view file permissions:

```bash
ls -l file.txt
```

Example output:

```
-rw-r--r-- 1 user group 1234 Jun  1 12:34 file.txt
```

## Changing file permissions

Use the `chmod` command to change file permissions:

```bash
chmod 755 file.txt
```

This sets the permissions to `rwxr-xr-x` (owner can read, write, and execute; group and others can read and execute).

## Read permission
Read permission allows a user to view the contents of a file. It is represented by the `r` character in the file permissions.

## Write permission

Write permission allows a user to modify the contents of a file. It is represented by the `w` character in the file permissions.

## Execute permission

Execute permission allows a user to run a file as a program. It is represented by the `x` character in the file permissions.

## User

The user (owner) of a file has specific permissions that determine what actions they can perform on the file. The owner's permissions are represented by the first set of three characters in the file permissions string (e.g., `rw-` in `rw-r--r--`).

## Group

The group associated with a file has specific permissions that determine what actions members of the group can perform on the file. The group's permissions are represented by the second set of three characters in the file permissions string (e.g., `r--` in `rw-r--r--`).

## Others

The "others" category refers to all users who are not the owner of the file and do not belong to the group associated with the file. The permissions for others are represented by the third set of three characters in the file permissions string (e.g., `r--` in `rw-r--r--`).

## ls -l

The `ls -l` command lists files in the current directory along with their detailed information, including file permissions, number of links, owner, group, size, and modification date.

Example:

```bash
ls -l
```

Output:

```
-rw-r--r-- 1 user group 1234 Jun  1 12:34 file.txt
```

## Permission notation

File permissions are represented using a combination of characters for each category of users (owner, group, others). The notation consists of three sets of three characters:

- The first set represents the owner's permissions.
- The second set represents the group's permissions.
- The third set represents the permissions for others.

Each set of three characters can include:
- `r` for read permission
- `w` for write permission
- `x` for execute permission
- `-` if the permission is not granted

For example, `rw-r--r--` means:
- Owner has read and write permissions (`rw-`)
- Group has read-only permission (`r--`)
- Others have read-only permission (`r--`)

## Numeric permissions
Numeric permissions provide an alternative way to represent file permissions using octal numbers. Each permission is assigned a numeric value:

- Read permission (`r`) has a value of 4.
- Write permission (`w`) has a value of 2.
- Execute permission (`x`) has a value of 1.
- No permission (`-`) has a value of 0.

The numeric value for each set of permissions (owner, group, others) is calculated by summing the values of the individual permissions. For example:

- `rw-` (read and write) = 4 + 2 + 0 = 6
- `r--` (read-only) = 4 + 0 + 0 = 4
- `r--` (read-only) = 4 + 0 + 0 = 4

So, the numeric representation of `rw-r--r--` is `644`.

## chmod

The `chmod` command is used to change the permissions of a file or directory. It can be used with either symbolic notation (e.g., `u+r`, `g-w`) or numeric notation (e.g., `644`, `755`).

Example using numeric notation:

```bash
chmod 644 file.txt
```

Example using symbolic notation:

```bash
chmod u+r,g-w,o+x file.txt
```

## chmod 755

The `chmod 755` command sets the permissions of a file or directory so that the owner has read, write, and execute permissions, while the group and others have read and execute permissions.

Example:

```bash
chmod 755 file.txt
```

This is equivalent to the symbolic notation:

```bash
chmod u=rwx,g=rx,o=rx file.txt
```

## chmod 644

The `chmod 644` command sets the permissions of a file or directory so that the owner has read and write permissions, while the group and others have read-only permissions.

Example:

```bash
chmod 644 file.txt
```

This is equivalent to the symbolic notation:

```bash
chmod u=rw,g=r,o=r file.txt
```

## chmod 700

The `chmod 700` command sets the permissions of a file or directory so that the owner has read, write, and execute permissions, while the group and others have no permissions.

Example:

```bash
chmod 700 file.txt
```

This is equivalent to the symbolic notation:

```bash
chmod u=rwx,g=,o= file.txt
```

## chmod +x

The `chmod +x` command adds execute permission to a file or directory for the owner, group, and others.

Example:

```bash
chmod +x file.txt
```

This is equivalent to the symbolic notation:

```bash
chmod u+x,g+x,o+x file.txt
```

## chmod -x

The `chmod -x` command removes execute permission from a file or directory for the owner, group, and others.

Example:

```bash
chmod -x file.txt
```

This is equivalent to the symbolic notation:

```bash
chmod u-x,g-x,o-x file.txt
```

## chown

The `chown` command is used to change the owner and/or group of a file or directory.

Example:

```bash
chown newowner:newgroup file.txt
```

This changes the owner of `file.txt` to `newowner` and the group to `newgroup`.


## chgrp

The `chgrp` command is used to change the group of a file or directory.

Example:

```bash
chgrp newgroup file.txt
```

This changes the group of `file.txt` to `newgroup`.

## umask

The `umask` command is used to set the default file creation permissions for new files and directories.

Example:

```bash
umask 022
```

This sets the default permissions so that new files are created with `644` permissions and new directories with `755` permissions.

## Users & Groups

In Linux, users and groups are used to manage permissions and access control for files and directories.

- **User**: An individual account that can own files and run processes.
- **Group**: A collection of users that can share access to files and directories.

You can view the current user with:

```bash
whoami
```

You can view the groups a user belongs to with:

```bash
groups
```

## Current user

The current user is the user account that is currently logged in and executing commands in the terminal.

You can view the current user with:

```bash
whoami
```

## id

The `id` command is used to display the user ID (UID), group ID (GID), and the groups a user belongs to.

Example:

```bash
id
```

This will output information about the current user, including the UID, GID, and group memberships.

## who

The `who` command is used to display information about users currently logged into the system.

Example:

```bash
who
```

This will output a list of logged-in users, along with their terminal, login time, and other relevant information.


## w

The `w` command is used to display information about users currently logged into the system and their activities.

Example:

```bash
w
```

This will output a list of logged-in users, along with their terminal, login time, idle time, JCPU, PCPU, and the command they are currently executing.


## /etc/passwd

The `/etc/passwd` file contains information about user accounts on the system, including the username, user ID (UID), group ID (GID), home directory, and default shell.

Example:

```bash
cat /etc/passwd
```

This will display the contents of the `/etc/passwd` file, showing details for each user account.

## /etc/group

The `/etc/group` file contains information about groups on the system, including the group name, group ID (GID), and the list of users belonging to the group.

Example:

```bash
cat /etc/group
```

This will display the contents of the `/etc/group` file, showing details for each group.

## /etc/shadow

The `/etc/shadow` file contains secure user account information, including encrypted passwords and password expiration details.

Example:

```bash
sudo cat /etc/shadow
```

This will display the contents of the `/etc/shadow` file, showing details for each user account. Note that this file is typically only accessible by the root user for security reasons.

## Create User

The `useradd` command is used to create a new user account on the system.

Example:

```bash
sudo useradd -m username
```

This will create a new user with the specified `username` and a home directory.

## Create Group

The `groupadd` command is used to create a new group on the system.

Example:

```bash
sudo groupadd groupname
```

This will create a new group with the specified `groupname`.

## useradd

The `useradd` command is used to create a new user account on the system. It allows you to specify various options such as the home directory, shell, and group membership.

Example:

```bash
sudo useradd -m -s /bin/bash -G groupname username
```

This will create a new user with the specified `username`, a home directory, the default shell set to `/bin/bash`, and add the user to the specified `groupname`.

## adduser

The `adduser` command is a more user-friendly way to create a new user account on the system. It typically prompts for additional information such as the password and user details.

Example:

```bash
sudo adduser username
```

This will create a new user with the specified `username` and prompt for additional information such as the password and user details.

## Delete user

The `userdel` command is used to delete a user account from the system.

Example:

```bash
sudo userdel -r username
```

This will delete the user with the specified `username` and remove their home directory and mail spool.

## Modify user

The `usermod` command is used to modify an existing user account on the system. It allows you to change various options such as the home directory, shell, and group membership.

Example:

```bash
sudo usermod -m -d /new/home/directory -s /bin/zsh -G newgroup username
```

This will modify the user with the specified `username`, changing their home directory to `/new/home/directory`, the default shell to `/bin/zsh`, and updating their group membership to include `newgroup`.

## Change Password

The `passwd` command is used to change the password for a user account on the system.

Example:

```bash
sudo passwd username
```

This will prompt for a new password for the specified `username` and update it accordingly.

## Create Group

The `groupadd` command is used to create a new group on the system.

Example:

```bash
sudo groupadd groupname
```

This will create a new group with the specified `groupname`.

## Add user to group

The `usermod` command with the `-aG` option is used to add an existing user to a group on the system.

Example:

```bash
sudo usermod -aG groupname username
```

This will add the user with the specified `username` to the specified `groupname` without affecting their existing group memberships.

## Remove user from group

The `gpasswd` command with the `-d` option is used to remove an existing user from a group on the system.

Example:

```bash
sudo gpasswd -d username groupname
```

This will remove the user with the specified `username` from the specified `groupname`.

## usermod

The `usermod` command is used to modify an existing user account on the system. It allows you to change various options such as the home directory, shell, and group membership.

Example:

```bash
sudo usermod -m -d /new/home/directory -s /bin/zsh -G newgroup username
```

This will modify the user with the specified `username`, changing their home directory to `/new/home/directory`, the default shell to `/bin/zsh`, and updating their group membership to include `newgroup`.

## groups

The `groups` command is used to display the groups that a user belongs to on the system.

Example:

```bash
groups username
```

This will display the groups that the specified `username` is a member of.

# Root & sudo

## Root User

The root user is the superuser account on a Unix-like system with full administrative privileges. The root user can perform any action on the system, including modifying system files, managing users, and installing software.

Example:

```bash
sudo su -
```

This will switch the current user to the root user, prompting for the current user's password if necessary.

## Why root is powerful

The root user has unrestricted access to all commands and files on the system. This level of access allows the root user to perform critical administrative tasks such as installing and removing software, changing system configurations, managing user accounts, and accessing all files regardless of their permissions. However, this power also comes with the risk of accidentally making system-breaking changes, so it should be used with caution.

## sudo

The `sudo` command allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. It is commonly used to perform administrative tasks without logging in as the root user.

Example:

```bash
sudo command
```

This will execute the specified `command` with superuser privileges, prompting for the current user's password if necessary.

## sudo -i

The `sudo -i` command is used to start a login shell as the root user. It provides an environment similar to what the root user would have if they logged in directly, including the root user's home directory and environment variables.

Example:

```bash
sudo -i
```

This will switch the current user to a root login shell, prompting for the current user's password if necessary.

## sudo su

The `sudo su` command is used to switch the current user to the root user. It is similar to `sudo su -`, but it does not start a login shell, so the environment variables and current working directory of the original user are preserved.

Example:

```bash
sudo su
```

This will switch the current user to the root user, prompting for the current user's password if necessary.

## su

The `su` command is used to switch the current user to another user, typically the root user. When used without any arguments, it defaults to switching to the root user. The user will be prompted to enter the target user's password.

Example:

```bash
su
```

This will switch the current user to the root user, prompting for the root user's password if necessary.

## root shell

A root shell is a command-line session where the user has root privileges. This can be achieved by using commands like `sudo -i`, `sudo su -`, or `su` to switch to the root user. In a root shell, the user can execute any command with full administrative rights.

Example:

```bash
sudo -i
```

This will start a root login shell, giving the user full root privileges.

## /etc/sudoers

The `/etc/sudoers` file is the configuration file for the `sudo` command. It defines which users and groups have permission to execute commands as the superuser or other users, and under what conditions. This file should be edited with the `visudo` command to ensure syntax correctness and prevent accidental lockout.

Example:

```bash
sudo visudo
```

This will open the `/etc/sudoers` file in a safe editor, allowing you to modify the sudo permissions.

## visudo

The `visudo` command is used to safely edit the `/etc/sudoers` file. It performs syntax checking and prevents multiple simultaneous edits, reducing the risk of misconfigurations that could lock out administrative access.

Example:

```bash
sudo visudo
```

This will open the `/etc/sudoers` file in a safe editor, allowing you to modify the sudo permissions.

## Sudo permissions

Sudo permissions determine which users and groups are allowed to execute commands with elevated privileges using the `sudo` command. These permissions are configured in the `/etc/sudoers` file or in separate files within the `/etc/sudoers.d/` directory.

Example:

```bash
sudo visudo
```

Within the editor, you might see lines like:

```
root    ALL=(ALL:ALL) ALL
username ALL=(ALL:ALL) ALL
```

This configuration allows the `root` user and `username` to execute any command as any user on the system using `sudo`.

## Least privilege

The principle of least privilege dictates that users and processes should have the minimum level of access necessary to perform their tasks. This reduces the risk of accidental or malicious changes to the system and limits the potential impact of security breaches.

Example:

Instead of giving a user full root access, you can grant specific sudo permissions for only the commands they need:

```
username ALL=(ALL:ALL) /usr/bin/apt-get, /usr/bin/systemctl
```

This configuration allows the `username` to execute only `apt-get` and `systemctl` commands with `sudo`, adhering to the principle of least privilege.

## why not to run everything as root

Running all commands as the root user can be dangerous because it grants full administrative privileges to every action. This increases the risk of accidental system changes, security vulnerabilities, and potential damage from malicious software.

Example:

Instead of logging in as root for all tasks, use a regular user account and elevate privileges only when necessary with `sudo`:

```bash
sudo apt-get update
sudo systemctl restart apache2
```

This approach minimizes the risk of unintended system modifications and adheres to the principle of least privilege.

# Searching 

## find

The `find` command is used to search for files and directories within a specified directory hierarchy based on various criteria such as name, type, size, and modification time.

Example:

```bash
find /path/to/search -name "filename.txt"
```

This command searches for a file named `filename.txt` starting from the `/path/to/search` directory and its subdirectories.

## locate

The `locate` command is used to quickly find files and directories by searching a pre-built database, rather than traversing the filesystem in real-time like `find`.

Example:

```bash
locate filename.txt
```

This command searches for a file named `filename.txt` using the `locate` database, which is typically faster than `find` for large filesystems.

## which

The `which` command is used to locate the executable file associated with a given command by searching the directories listed in the `PATH` environment variable.

Example:

```bash
which python3
```

This command displays the full path to the `python3` executable, helping you determine which version of a command will be executed.

## whereis

The `whereis` command is used to locate the binary, source, and manual page files for a specified command.

Example:

```bash
whereis python3
```

This command displays the locations of the `python3` binary, source, and man page files.

## type

The `type` command is used to display information about a command, including whether it is a built-in shell command, an alias, or an external executable.

Example:

```bash
type python3
```

This command shows information about the `python3` command, helping you understand how it will be interpreted by the shell.

## command -v

The `command -v` command is used to display the path to the executable that would be executed for a given command, similar to `which`, but it is a shell built-in and more reliable in scripts.

Example:

```bash
command -v python3
```

This command shows the full path to the `python3` executable that will be used by the shell.

## Search by filename

To search for files by their name, you can use the `find` or `locate` commands as described above. Here are some additional examples:

### Using `find`

```bash
find /path/to/search -type f -name "*.txt"
```

This command searches for all files with a `.txt` extension starting from the `/path/to/search` directory and its subdirectories.

### Using `locate`

```bash
locate "*.txt"
```

This command searches for all files with a `.txt` extension using the `locate` database.

## Search by extension

To search for files by their extension, you can use the `find` or `locate` commands. Here are some examples:

### Using `find`

```bash
find /path/to/search -type f -name "*.jpg"
```

This command searches for all files with a `.jpg` extension starting from the `/path/to/search` directory and its subdirectories.

### Using `locate`

```bash
locate "*.jpg"
```

This command searches for all files with a `.jpg` extension using the `locate` database.

## Search by size

To search for files by their size, you can use the `find` command with the `-size` option. Here are some examples:

### Using `find`

```bash
find /path/to/search -type f -size +100M
```

This command searches for all files larger than 100 megabytes starting from the `/path/to/search` directory and its subdirectories.

## Search by permission

To search for files by their permission, you can use the `find` command with the `-perm` option. Here are some examples:

### Using `find`

```bash
find /path/to/search -type f -perm 644
```

This command searches for all files with the permission `644` starting from the `/path/to/search` directory and its subdirectories.

## Search by owner

To search for files by their owner, you can use the `find` command with the `-user` option. Here are some examples:

### Using `find`

```bash
find /path/to/search -type f -user username
```

This command searches for all files owned by the user `username` starting from the `/path/to/search` directory and its subdirectories.

## Search by modification time

To search for files by their modification time, you can use the `find` command with the `-mtime` option. Here are some examples:

### Using `find`

```bash
find /path/to/search -type f -mtime -7
```

This command searches for all files modified in the last 7 days starting from the `/path/to/search` directory and its subdirectories.

# Text Processing

## grep

The `grep` command is used to search for text patterns within files. Here are some examples:

### Basic usage

```bash
grep "pattern" /path/to/file
```

This command searches for the specified `pattern` in the given file.

### Recursive search

```bash
grep -r "pattern" /path/to/search
```

This command searches for the specified `pattern` in all files under the `/path/to/search` directory and its subdirectories.

### Case-insensitive search

```bash
grep -i "pattern" /path/to/file
```

This command searches for the specified `pattern` in the given file, ignoring case differences.

## grep -i

The `-i` option makes the search case-insensitive. Here is an example:

### Case-insensitive search in multiple files

```bash
grep -i "pattern" /path/to/search/*.txt
```

This command searches for the specified `pattern` in all `.txt` files under the `/path/to/search` directory, ignoring case differences.


## grep -r

The `-r` option makes the search recursive, meaning it will search through all files in the specified directory and its subdirectories. Here is an example:

### Recursive search in a directory

```bash
grep -r "pattern" /path/to/search
```

This command searches for the specified `pattern` in all files under the `/path/to/search` directory and its subdirectories.

## grep -n

The `-n` option makes `grep` display the line numbers of matching lines. Here is an example:

### Search with line numbers

```bash
grep -n "pattern" /path/to/file
```

This command searches for the specified `pattern` in the given file and displays the line numbers of the matching lines.

## grep -v

The `-v` option makes `grep` display lines that do not match the specified pattern. Here is an example:

### Search for lines not matching a pattern

```bash
grep -v "pattern" /path/to/file
```

This command searches for all lines in the given file that do not contain the specified `pattern`.

## grep -E

The `-E` option enables extended regular expressions, allowing more complex pattern matching. Here is an example:

### Search using extended regular expressions

```bash
grep -E "pattern1|pattern2" /path/to/file
```

This command searches for lines that match either `pattern1` or `pattern2` in the given file.

## sed

The `sed` command is used for stream editing, allowing you to perform basic text transformations on an input stream (a file or input from a pipeline). Here are some examples:

### Basic usage

```bash
sed 's/old-text/new-text/' /path/to/file
```

This command replaces the first occurrence of `old-text` with `new-text` in each line of the given file.

### Global replacement

```bash
sed 's/old-text/new-text/g' /path/to/file
```

This command replaces all occurrences of `old-text` with `new-text` in each line of the given file.

## awk

The `awk` command is used for pattern scanning and processing. It allows you to perform actions on lines that match a specified pattern. Here are some examples:

### Basic usage

```bash
awk '/pattern/ {print $0}' /path/to/file
```

This command searches for lines that match the specified `pattern` in the given file and prints them.

### Print specific columns

```bash
awk '{print $1, $3}' /path/to/file
```

This command prints the first and third columns of each line in the given file. Columns are typically separated by whitespace.

## cut

The `cut` command is used to extract sections from each line of input, typically from a file. Here are some examples:

### Basic usage

```bash
cut -d',' -f1 /path/to/file
```

This command extracts the first field from each line of the given file, assuming fields are separated by commas.

## sort

The `sort` command is used to sort lines of text files. Here are some examples:

### Basic usage

```bash
sort /path/to/file
```

This command sorts the lines of the given file in ascending order.

## uniq

The `uniq` command is used to filter out or report repeated lines in a file. It is often used in combination with `sort` to remove duplicate lines. Here are some examples:

### Basic usage

```bash
uniq /path/to/file
```

This command filters out consecutive duplicate lines in the given file.

### Count occurrences

```bash
uniq -c /path/to/file
```

This command prefixes each line with the number of times it occurs in the given file.

## tr

The `tr` command is used to translate or delete characters from the input. Here are some examples:

### Basic usage

```bash
tr 'a-z' 'A-Z' < /path/to/file
```

This command converts all lowercase letters to uppercase in the given file.

### Delete characters

```bash
tr -d 'aeiou' < /path/to/file
```

This command deletes all vowels from the given file.

## xargs

The `xargs` command is used to build and execute command lines from standard input. It is often used to process the output of other commands. Here are some examples:

### Basic usage

```bash
echo "file1 file2 file3" | xargs rm
```

This command removes the files `file1`, `file2`, and `file3`.

### Using with find

```bash
find /path/to/dir -name "*.txt" | xargs grep "pattern"
```

This command searches for the specified `pattern` in all `.txt` files within the given directory.

## tee

The `tee` command is used to read from standard input and write to standard output and files simultaneously. Here are some examples:

### Basic usage

```bash
echo "Hello, World!" | tee /path/to/file
```

This command writes the string "Hello, World!" to both the terminal and the specified file.

### Append to a file

```bash
echo "Hello again!" | tee -a /path/to/file
```

This command appends the string "Hello again!" to the specified file while also displaying it in the terminal.

## diff

The `diff` command is used to compare files line by line. It shows the differences between two files. Here are some examples:

### Basic usage

```bash
diff /path/to/file1 /path/to/file2
```

This command compares `file1` and `file2` and displays the differences between them.

### Unified format

```bash
diff -u /path/to/file1 /path/to/file2
```

This command compares `file1` and `file2` and displays the differences in a unified format, which is often used for creating patch files.

## comm

The `comm` command is used to compare two sorted files line by line. It produces three columns of output: lines only in the first file, lines only in the second file, and lines common to both files. Here are some examples:

### Basic usage

```bash
comm /path/to/file1 /path/to/file2
```

This command compares `file1` and `file2` and displays the differences and common lines in three columns.

### Suppress columns

```bash
comm -12 /path/to/file1 /path/to/file2
```

This command displays only the lines that are common to both `file1` and `file2`.

## join

The `join` command is used to join lines of two sorted files based on a common field. Here are some examples:

### Basic usage

```bash
join /path/to/file1 /path/to/file2
```

This command joins lines from `file1` and `file2` that have the same value in the first field.

### Specify a different field

```bash
join -1 2 -2 3 /path/to/file1 /path/to/file2
```

This command joins lines from `file1` and `file2` based on the second field of `file1` and the third field of `file2`.
