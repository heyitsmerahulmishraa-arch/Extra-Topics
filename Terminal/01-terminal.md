# Terminal Fundamentals

## What is a Terminal?

A terminal is a text-based interface that allows users to interact with the operating system by typing commands. It is commonly used for tasks such as navigating the file system, managing files and directories, running scripts, and executing various system commands.

## Why Terminal is Important

A terminal is important because it provides a powerful and efficient way to interact with the operating system. It allows users to perform tasks quickly, automate repetitive processes through scripting, and access advanced features that may not be available through graphical user interfaces. Additionally, many development and system administration tasks require the use of a terminal.

## What is the difference between Terminal and shell

A terminal is the interface that allows users to interact with the operating system by typing commands, while a shell is the program that interprets and executes those commands. In other words, the terminal provides the environment for user input and output, and the shell processes the commands entered by the user. Common shells include Bash, Zsh, and Fish.

## is terminal and shell same thing?

A terminal and a shell are not the same thing. A terminal is the interface that allows users to input commands and view output, while a shell is the program that interprets and executes those commands. The terminal provides the environment for interaction, and the shell handles the command processing.

## What is Bash?

Bash (Bourne Again SHell) is a popular Unix shell and command language. It is widely used as the default shell on many Linux distributions and macOS. Bash provides a command-line interface for users to interact with the operating system, execute commands, and write shell scripts for automating tasks. It is an enhanced version of the original Bourne shell (sh) with additional features and improvements.

### Example of Bash

```bash
# Print the current working directory
pwd

# List files and directories
ls -l

# Create a new directory
mkdir my_directory

# Change to the new directory
cd my_directory

# Create a new file
touch my_file.txt

# Display the contents of the file
cat my_file.txt
```

## How to run Bash commands

To run Bash commands, you need to open a terminal and type the commands at the prompt. Press `Enter` to execute each command. You can also create a shell script file with a `.sh` extension, write your Bash commands in the file, and then run the script using the following command:

```bash
bash my_script.sh
```

## How to run a Bash script

1. Open a terminal.
2. Navigate to the directory containing your Bash script using the `cd` command.
3. Make the script executable (optional but recommended) using the command:

```bash
chmod +x my_script.sh
```

4. Run the script using one of the following commands:

```bash
./my_script.sh
```
or
```bash
bash my_script.sh
```

## What is Zsh?

Zsh (Z Shell) is an extended version of the Bourne shell (sh) with many improvements and additional features. It is known for its powerful scripting capabilities, advanced tab completion, and customization options. Zsh is often used as an alternative to Bash and is popular among developers for its flexibility and user-friendly features. Many users also use Oh My Zsh, a framework for managing Zsh configuration, to enhance their Zsh experience.

### Example of Zsh

```zsh
# Print the current working directory
pwd

# List files and directories
ls -l

# Create a new directory
mkdir my_directory

# Change to the new directory
cd my_directory

# Create a new file
touch my_file.txt

# Display the contents of the file
cat my_file.txt
```

## How to run Zsh commands

To run Zsh commands, you need to open a terminal and type the commands at the prompt. Press `Enter` to execute each command. You can also create a shell script file with a `.zsh` extension, write your Zsh commands in the file, and then run the script using the following command:

```zsh
zsh my_script.zsh
```

## Terminal Emulator

A terminal emulator is a software application that provides a text-based interface for interacting with the operating system. It allows users to run shell commands, execute scripts, and manage files and processes. Popular terminal emulators include GNOME Terminal, Konsole, iTerm2, and Windows Terminal. Terminal emulators are essential tools for developers, system administrators, and power users who prefer command-line interfaces over graphical user interfaces.

## CLI vs GUI

CLI (Command-Line Interface) allows users to interact with the operating system by typing text commands in a terminal emulator. It is powerful, flexible, and often preferred by advanced users and developers for automation and scripting.

GUI (Graphical User Interface) provides a visual interface with windows, icons, and menus for interacting with the operating system. It is user-friendly and suitable for general users who prefer point-and-click interactions over typing commands.

## Command Structure

A typical command in the terminal follows this structure:

```
command [options] [arguments]
```

- `command`: The program or utility you want to run.
- `options`: Modifiers that change the behavior of the command (usually prefixed with `-` or `--`).
- `arguments`: The targets or inputs for the command, such as files or directories.

### Example

```bash
ls -l /home/user/Documents
```

In this example:
- `ls` is the command to list directory contents.
- `-l` is an option to display the contents in long format.
- `/home/user/Documents` is the argument specifying the directory to list.

## Command arguments

Command arguments are the inputs provided to a command to specify what the command should act upon. They can be files, directories, or other data required by the command.

### Example

```bash
cp source.txt destination.txt
```

In this example:
- `cp` is the command to copy files.
- `source.txt` is the first argument specifying the file to copy.
- `destination.txt` is the second argument specifying the destination file.

## Options/flags

Options or flags are modifiers that change the behavior of a command. They are usually prefixed with a single dash `-` for short options or a double dash `--` for long options.

### Example

```bash
ls -a --color=auto
```

In this example:
- `ls` is the command to list directory contents.
- `-a` is a short option to include hidden files in the listing.
- `--color=auto` is a long option to enable colored output based on file types.

## Short flags and Long flags

Short flags are single-character options prefixed with a single dash `-`. They are usually combined together to save typing.

Long flags are multi-character options prefixed with a double dash `--`. They are more descriptive and easier to understand.

### Example

```bash
tar -xvf archive.tar.gz
tar --extract --verbose --file=archive.tar.gz
```

In this example:
- `-xvf` are short flags combined together: `-x` for extract, `-v` for verbose, and `-f` to specify the file.
- `--extract --verbose --file=archive.tar.gz` are the equivalent long flags providing the same functionality.

## Command Output

Command output is the information displayed by the terminal after executing a command. It can include success messages, error messages, or the requested data.

### Example

```bash
ls /home/user/Documents
```

In this example:
- The terminal will display the contents of the `/home/user/Documents` directory as the command output.

## Exit status

The exit status is a numeric value returned by a command to indicate its success or failure. By convention, an exit status of `0` indicates success, while any non-zero value indicates an error.

### Example

```bash
ls /home/user/Documents
echo $?
```

In this example:
- The `ls` command lists the contents of the `/home/user/Documents` directory.
- The `echo $?` command displays the exit status of the previous command. A `0` indicates that the `ls` command was successful.

## CTRL+C,D,Z,L,A,E,R,U,K,W

These are common keyboard shortcuts used in the terminal to control processes and manage the terminal environment:

- `CTRL+C`: Interrupts the current running process.
- `CTRL+D`: Signals the end of input (EOF) or logs out of the terminal.
- `CTRL+Z`: Suspends the current running process.
- `CTRL+L`: Clears the terminal screen.
- `CTRL+A`: Moves the cursor to the beginning of the line.
- `CTRL+E`: Moves the cursor to the end of the line.
- `CTRL+R`: Initiates a reverse search through command history.
- `CTRL+U`: Deletes from the cursor to the beginning of the line.
- `CTRL+K`: Deletes from the cursor to the end of the line.
- `CTRL+W`: Deletes the word before the cursor.
- `CTRL+Y`: Pastes the last deleted text (yank).
- `CTRL+P`: Recalls the previous command from the history.
- `CTRL+N`: Recalls the next command from the history.
- `CTRL+G`: Aborts the current search in the command history.
- `CTRL+T`: Transposes the character before the cursor with the character under the cursor.
- `CTRL+X`: Used in combination with other keys for various shortcuts, such as `CTRL+X CTRL+E` to open the current command in the default text editor.
- `CTRL+H`: Deletes the character before the cursor (backspace).
- `CTRL+Q`: Resumes the terminal output if it was paused with `CTRL+S`.
- `CTRL+S`: Pauses the terminal output.
- `CTRL+V`: Inserts the next character literally, allowing you to input control characters.
- `CTRL+O`: Executes the current command and then returns to the previous state in the command line editor.
- `CTRL+J`: Executes the current command (similar to pressing Enter).

# Linux Basics

## What is Linux?

Linux is an open-source operating system based on Unix. It is widely used for servers, desktops, and embedded systems. Linux provides a robust and secure environment for running applications and managing hardware resources. It is known for its stability, flexibility, and strong community support.

## What is Linux Kernel?

The Linux kernel is the core component of the Linux operating system. It manages system resources, including the CPU, memory, and peripheral devices, and provides essential services to applications. The kernel acts as a bridge between the hardware and software, ensuring efficient and secure operation of the system. It is responsible for process management, memory management, device drivers, and system calls.

## Linux Distributions

Linux distributions (distros) are different versions of the Linux operating system that bundle the Linux kernel with various software packages and tools. Popular Linux distributions include Ubuntu, Fedora, Debian, CentOS, and Arch Linux. Each distribution has its own package management system, release cycle, and target audience, but all share the common Linux kernel at their core.

![linux kernal and distributions](./images/linux%20kernal%20and%20linux%20distributions.png)

## What is Root user

The root user, also known as the superuser, is a special user account in Linux with full administrative privileges. The root user has the ability to perform any action on the system, including installing and removing software, modifying system configurations, managing user accounts, and accessing all files and directories. Due to its extensive permissions, it is recommended to use the root account sparingly and perform regular tasks with a standard user account to minimize the risk of accidental system changes or security breaches.

## Why Use the Root User?

The root user is necessary for performing administrative tasks that require elevated privileges. This includes installing and updating software, configuring system settings, managing user accounts, and accessing restricted files and directories. Using the root account allows system administrators to maintain and control the system effectively. However, due to the potential risks associated with having full system access, it is recommended to use the root account only when necessary and to perform routine tasks with a standard user account.

## Can we create multiple users

Yes, Linux allows the creation of multiple user accounts. Each user can have their own set of permissions, home directory, and personal settings. This enables multiple people to use the same system securely without interfering with each other's files and configurations. User management is typically performed using commands like `adduser` or `useradd` for creating new users, and `passwd` for setting or changing passwords.

## Are all different users have root privileges?

No, not all users have root privileges. In Linux, only the root user has full administrative access by default. Other users have limited permissions and can only perform actions within their own scope unless granted additional privileges through mechanisms like `sudo`. This separation of privileges helps maintain system security and prevents accidental or unauthorized changes to critical system files and settings.

## if we create another user using `adduser` they don't have root privileges?

No, when you create a new user using the `adduser` command, the new user does not have root privileges by default. The new user will have limited permissions and will only be able to perform actions within their own scope. If you want the new user to have administrative privileges, you need to add them to the `sudo` group using a command like `usermod -aG sudo username`. This allows the user to execute commands with elevated privileges by prefixing them with `sudo`.

## how to assign permissions to a user

To assign permissions to a user in Linux, you can use the `chmod` and `chown` commands. The `chmod` command changes the file permissions, while the `chown` command changes the file ownership. For example:

- To change the permissions of a file for a specific user:
  ```bash
  chmod u+rwx filename
  ```
  This grants the user read, write, and execute permissions on the file.

- To change the ownership of a file to a specific user:
  ```bash
  chown username filename
  ```
  This makes the specified user the owner of the file.

Additionally, you can manage group permissions and add users to groups to control access more efficiently. Use the `usermod -aG groupname username` command to add a user to a group.

## How to assign root permissions to a new user

To assign root permissions to a new user, you need to add the user to the `sudo` group. This allows the user to execute commands with elevated privileges by prefixing them with `sudo`. Here is how you can do it:

```bash
usermod -aG sudo username 
```

Replace `username` with the actual username of the new user. After this, the user will have root privileges when using `sudo`.

### Explaining code

```bash
usermod -aG sudo username
```

The `usermod -aG sudo username` command adds the specified user to the `sudo` group. The `-aG` option means "append the user to the specified group(s)". By adding the user to the `sudo` group, the user gains the ability to execute commands with root privileges by using `sudo` before the command.

## What is the difference between a root user and a normal user

A root user, also known as the superuser, has full administrative privileges and can perform any action on the system, including modifying system files, installing software, and managing other users. A normal user has limited permissions and can only perform actions within their own scope unless granted additional privileges through mechanisms like `sudo`. This distinction helps maintain system security and prevents accidental or unauthorized changes to critical system files and settings.

## Home directory

The home directory is a personal directory assigned to each user on the system. It typically contains the user's personal files, configuration settings, and subdirectories. The home directory provides a workspace for the user and helps keep user-specific data separate from system files.

For example, the home directory for a user named `username` is usually located at `/home/username`.

You can navigate to your home directory using the `cd` command without any arguments:

```bash
cd
```

Or explicitly:

```bash
cd /home/username
```

## Common subdirectories in the home directory

The home directory usually contains several common subdirectories that help organize user data and configuration files. Some of the typical subdirectories include:

- `Documents`: Stores personal documents and files.
- `Downloads`: Contains files downloaded from the internet.
- `Pictures`: Stores image files.
- `Music`: Contains audio files.
- `Videos`: Stores video files.
- `.config`: A hidden directory that contains configuration files for various applications.

You can list all files and directories, including hidden ones, in your home directory using:

```bash
ls -a ~
```

## Filesystem

The filesystem is the hierarchical structure used by the operating system to organize and store files and directories on storage devices. It starts from the root directory `/` and branches out into various subdirectories.

Some important directories in the root filesystem include:

- `/bin`: Contains essential binary executables.
- `/etc`: Contains system configuration files.
- `/home`: Contains the home directories of users.
- `/lib`: Contains essential shared libraries.
- `/var`: Contains variable data files like logs and databases.
- `/tmp`: Contains temporary files.
- `/usr`: Contains user-installed software and utilities.

You can navigate the filesystem using the `cd` command and list files using the `ls` command. For example:

```bash
cd /
ls
```

## Processes

A process is an instance of a running program. Each process has a unique process ID (PID) and can be managed using various commands in the terminal.

You can view the list of currently running processes using the `ps` command:

```bash
ps aux
```

To monitor processes in real-time, you can use the `top` command:

```bash
top
```

## Services

Services, also known as daemons, are background processes that perform various tasks on the system. They are typically started during system boot and continue running without direct user interaction.

You can view the status of services using the `systemctl` command:

```bash
systemctl status
```

To start, stop, or restart a service, you can use:

```bash
sudo systemctl start <service_name>
sudo systemctl stop <service_name>
sudo systemctl restart <service_name>
```

## Packages

Packages are collections of software that can be installed, updated, and removed on a system. Most Linux distributions use package managers to handle software packages.

For example, on Debian-based systems (like Ubuntu), you can use `apt` to manage packages:

- Update the package list:

```bash
sudo apt update
```

- Install a package:

```bash
sudo apt install <package_name>
```

- Remove a package:

```bash
sudo apt remove <package_name>
```

On Red Hat-based systems (like Fedora), you can use `dnf`:

- Install a package:

```bash
sudo dnf install <package_name>
```

- Remove a package:

```bash
sudo dnf remove <package_name>
```

## Daemons

Daemons are background processes that run continuously and perform specific tasks without direct user interaction. They are often started during system boot and managed by the init system or service manager.

You can view running daemons using the `ps` command with appropriate options, for example:

```bash
ps aux | grep daemon_name
```

To manage daemons, you typically use the same commands as for services, such as `systemctl` on systems using systemd.

For example, to start, stop, or restart a daemon, you can use:

```bash
sudo systemctl start <daemon_name>
sudo systemctl stop <daemon_name>
sudo systemctl restart <daemon_name>
```





