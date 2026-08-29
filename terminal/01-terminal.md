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

