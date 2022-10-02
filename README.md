# Linux Cheat Sheet

This is a collection of notes about Linux. It is not a complete guide, perhaps this is a good place to remember some of the most important commands and concepts of Linux, and not an starting point for those who want to learn Linux from scratch.

- [How to Use This Cheat Sheet](#how-to-use-this-cheat-sheet)
- [Levels and Layers in Linux](#levels-and-layers-in-linux-🏴‍☠️)
- [Hardware: Main Memory](#hardware-main-memory-🏴‍☠️)
- [Kernel](#kernel-🏴‍☠️)
- [User Space](#user-space-🏴‍☠️)
- [Users](#users-🏴‍☠️)
- [The shell](#the-shell-🏴‍☠️)
- [The standard input, output and error](#the-standard-input-output-and-error🏴‍☠️)
- [Arguments](#arguments-🏴‍☠️)
- [Wildcards](#wildcards-🏴‍☠️)
- [Commands](#commands-🏴‍☠️)
- [Shell Variables](#shell-variables-🏴‍☠️)
- [Path Commands](#path-commands-🏴‍☠️)
- [Special Characters](#special-characters-🏴‍☠️)
- [Command Line Editing](#command-line-editing-🏴‍☠️)
- [Change Password (passwd)](#change-password-passwd-🏴‍☠️)
- [Text Editors](#text-editors-🏴‍☠️)

## How to Use This Cheat Sheet

This cheat sheet is organized in a way that you can use it as a reference. You can use the Table of Contents to jump to the section you want to read. Many of the sections have links to other sections, so you can jump to the next section or to the previous section.

---

## Levels and Layers in Linux 🏴‍☠️

### ✔ Hardware: Level 1

The hardware is at the base, include the memory to perform computation. (CPU, RAM, disk, network, etc.)

### ✔ Kernel: Level 2

It is responsible for managing the hardware and providing an interface for the user to interact with the hardware. (system calls, process management, memory management, device drivers, etc.)

### ✔ User Process: Level 3

The running programs managed by the kernel. (graphical user interface, servers, shell, etc.)

## Hardware: Main Memory 🏴‍☠️

The main memory is the place where the data and instructions are stored. An slot in the memory is called a byte. The memory is organized in a way that each byte has a unique address. The address is a number that identifies the byte.

## Kernel 🏴‍☠️

- Process: Determine the process allowed to access the memory.
- Memory: Determine the memory allowed to be accessed by the process.
- Driver: The kernel acts as interface between the hardware and the user process.

### ✔ Process Management

- Starting a process: The kernel creates a new process and allocates memory for it.
- Pausing a process: The kernel suspends the process and saves its state.
- Resuming a process: The kernel restores the process state and resumes it.
- Scheduling: The kernel decides which process to run next.
- Terminating a process: The kernel terminates the process and frees its memory.

Note: Many processes can be running simultaneously but only one process can be running at a time.

### ✔ Memory Management

- Allocating memory: The kernel allocates memory for a process.
- Freeing memory: The kernel frees memory allocated for a process.
- Swapping: The kernel moves a process from memory to disk and vice versa.

### ✔ Device Drivers

Allowing the user process to interact with a hardware device.

### ✔ System Calls

Interaction between the user process and the kernel.

- Fork: Create a new process.
- Exec: Start a new program.
- Wait: Wait for a child process to terminate.
- Exit: Terminate a process.
- Kill: Terminate a process.
- Init: Start the init process.

## User Space 🏴‍☠️

The space that kernel allocated for the user process.

## Users 🏴‍☠️

A users is an entity that can run programs. Each user has a unique user ID (UID) and a unique group ID (GID). The user ID is used to identify the user and the group ID is used to identify the group of users.

Note: The root user has UID 0 and GID 0, and it is the only user that can run programs with root privileges which means that has access as administrator on traditional Unix systems. Operating as root can be dangerous. It can be difficult to identify and correct mistakes because the system will let you do anything

---

## The shell 🏴‍☠️

The shell is program stored in the `/bin/sh` that run commands, these commands can be other programs or built-in features. The shell is also a programming language that can be used to automate tasks.

## The standard input, output and error🏴‍☠️

### ✔ Standard input (stdin)

The standard input is the input that a program receives from the keyboard. It is represented by the file descriptor 0.

### ✔ Standard output (stdout)

The standard output is the output that a program sends to the shell windows. It is represented by the file descriptor 1.

### ✔ Standard error (stderr)

The standard error is the output that a program sends to the shell windows when it encounters an error. It is represented by the file descriptor 2.

## Arguments 🏴‍☠️

Arguments are the parameters that a program receives from the shell. They are separated by spaces.

### ✔ --help

The `--help` argument is a special argument that is used to display the help of a program.

example:

```bash
$ ls --help
```

## Wildcards 🏴‍☠️

Expands are used to replace a string with another string.

| Expand | Description                                                      | Example    | Result                |
| ------ | ---------------------------------------------------------------- | ---------- | --------------------- |
| `~`    | The home directory                                               | `cd ~`     | `/home/user`          |
| `.`    | The current working directory                                    | `cd .`     | `/home/user`          |
| `..`   | The parent directory of the current working directory            | `cd ..`    | `/home`               |
| `*`    | Expand files that end with the string before the `*`             | `ls *.txt` | `file1.txt file2.txt` |
| `*`    | Expand files that start with the string after the `*`            | `ls file*` | `file1 file2`         |
| `*`    | Expand files that contain the string between the `*` and the `*` | `ls *1*`   | `file1 file2`         |
| `?`    | Match a exactly one character                                    | `ls b?at`  | `boat` and `brat`     |

## Commands 🏴‍☠️

### ✔ Moving around

| Command | Description                                                     | shell input     | shell output             |
| ------- | --------------------------------------------------------------- | --------------- | ------------------------ |
| `pwd`   | Print the current working directory                             | `pwd`           | `/home/user`             |
| `cd`    | Change the current working directory                            | `cd /home/user` | No output                |
| `ls`    | List the files and directories in the current working directory | `ls`            | `file1 file2 directory1` |

### ✔ Creating and removing files and directories

| Command | Description                                                                    | shell input                 | shell output  |
| ------- | ------------------------------------------------------------------------------ | --------------------------- | ------------- |
| `touch` | Create a file if it doesn't exist, otherwise update the last modification time | `touch file1`               | No output     |
| `mkdir` | Create a directory                                                             | `mkdir directory1`          | No output     |
| `rm`    | Remove a file or directory                                                     | `rm file1`                  | No output     |
| `rmdir` | Remove a directory                                                             | `rmdir directory1`          | No output     |
| `mv`    | Move a file or directory                                                       | `mv file1 directory1/file1` | No output     |
| `cp`    | Copy a file or directory                                                       | `cp file1 file2`            | No output     |
| `echo`  | Print the arguments                                                            | `echo hello world`          | `hello world` |

### ✔ Searching for files

#### ✔ find

The `find` command is used to search for files and directories.

```bash
$ find [path] [options] [expression]
```

| Argument  | Description                                   | Input                | Output                                                        |
| --------- | --------------------------------------------- | -------------------- | ------------------------------------------------------------- |
| path      | The path to search in                         | `find /home/user`    | `/home/user/file1` `/home/user/file2` `/home/user/directory1` |
| -name     | The name of the file                          | `find -name file`    | `/home/user/file1` `/home/user/file2`                         |
| -type     | The type of the file                          | `find -type f`       | `/home/user/file1` `/home/user/file2`                         |
| -print    | Print the result                              | `find -print`        | `/home/user/file1` `/home/user/file2`                         |
| -depth    | Search in subfolders                          | `find -depth`        | `/home/user/file1` `/home/user/file2`                         |
| --version | Print the version of the command              | `find --version`     | `find (GNU findutils) 4.6.0`                                  |
| -cnewer   | Search for files that are newer than the file | `find -cnewer file1` | `/home/user/file2`                                            |

#### ✔ Grep

The `grep` command is used to search for a string in a file.

```bash
$ grep [options] [pattern] [file]
```

| Argument | Description                                | Input                             | Output                        |
| -------- | ------------------------------------------ | --------------------------------- | ----------------------------- |
| pattern  | The string to search                       | `grep hello file`                 | `hello world`                 |
| -i       | Ignore case                                | `grep -i hello file`              | `hello world`                 |
| -n       | Print the line number                      | `grep -n hello file`              | `1:hello world`               |
| -v       | Invert the match                           | `grep -v hello file`              | `world`                       |
| -c       | Count the matches                          | `grep -c hello file`              | `1`                           |
| -l       | Print the file name                        | `grep -l hello file`              | `file`                        |
| -r       | Search in subfolders                       | `grep -r hello file`              | `file:hello world`            |
| -w       | Match the whole word                       | `grep -w hello file`              | `hello`                       |
| -E       | Use extended regular expressions           | `grep -E "hello                   | world" file`                  |
| -F       | Use fixed strings                          | `grep -F "hello world" file`      | `hello world`                 |
| -e       | Use a pattern                              | `grep -e "hello" -e "world" file` | `hello world`                 |
| -o       | Print only the matched part                | `grep -o "hello" file`            | `hello`                       |
| -A       | Print the lines after the match            | `grep -A 1 "hello" file`          | `hello world` `world`         |
| -B       | Print the lines before the match           | `grep -B 1 "hello" file`          | `hello` `hello world`         |
| -C       | Print the lines before and after the match | `grep -C 1 "hello" file`          | `hello` `hello world` `world` |
| -P       | Use Perl regular expressions               | `grep -P "hello                   | world" file`                  |
| -z       | Search for null terminated strings         | `grep -z "hello" file`            | `hello`                       |

### ✔ Less

The `less` command is used to view the contents of a file, see all the contents of a file without opening it.

```bash
$ less [file]
```

| Argument | Description           | Input          | Output          |
| -------- | --------------------- | -------------- | --------------- |
| file     | The file to view      | `less file`    | `hello world`   |
| -N       | Print the line number | `less -N file` | `1:hello world` |

Note: Use `--help` to see all the options.

### ✔ Pipe

The pipe `|` is used to send the output of one command to another command.

```bash
$ grep hello file | less # It will print the lines that contain the string "hello" in the file "file" and then it will open the file with less
```

### ✔ Redirect

The redirect `>` is used to redirect the output of a command to a file.

```bash
$ echo hello world > file # It will print "hello world" in the file "file"
```

### ✔ Some useful commands

| Argument | Description                            | Input                  | Output          |
| -------- | -------------------------------------- | ---------------------- | --------------- |
| cat      | Print the contents of a file           | `cat file`             | `hello world`   |
| head     | Print the first lines of a file        | `head file`            | `hello world`   |
| tail     | Print the last lines of a file         | `tail file`            | `hello world`   |
| wc       | Count the lines, words and characters  | `wc file`              | `1 2 11`        |
| sort     | Sort the lines of a file               | `sort file`            | `hello world`   |
| uniq     | Remove duplicate lines                 | `uniq file`            | `hello world`   |
| cut      | Cut out selected portions of each line | `cut -d " " -f 1 file` | `hello`         |
| tr       | Translate or delete characters         | `tr " " "\n" < file`   | `hello` `world` |
| file     | Determine the type of a file           | `file file`            | `ASCII text`    |
| du       | Estimate file space usage              | `du file`              | `4 file`        |

---

## Shell Variables 🏴‍☠️

Shell variables are a way to store information that can be accessed by the shell and programs that the shell runs. They are useful for passing information to scripts and storing configuration information.

### ✔ Setting Variables

Variables are set using the `=` operator. There is no space between the variable name, the equal sign, and the value. The value can be anything, but there are some rules:

- The first character of the variable name must be a letter or underscore.
- The rest of the variable name can contain letters, numbers, and underscores.
- There are no spaces allowed around the `=` operator.
- The value can contain anything.
- Variable names are case sensitive. This means that `MY_MESSAGE` and `my_message` are two different variables.

```bash
$ MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World
```

### ✔ Variable Types

There are two types of variables: local and environment variables. Local variables are only available to the current shell and any programs that it runs. Environment variables are available to any program that the user runs.

#### ✔ Local Variables

Local variables are set by assigning a value to them using the `=` operator. They are used to store information for the current shell and any programs that it runs.

```bash
$ MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World
```

#### ✔ Environment Variables

Environment variables are set by assigning a value to them using the `export` command. They are used to store information for any program that the user runs.

```bash
$ export MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World
```

### ✔ Unsetting Variables

Variables can be unset by using the `unset` command. This removes the variable from the current shell.

```bash
$ MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World

$ unset MY_MESSAGE
$ echo $MY_MESSAGE

$
```

### ✔ Variable Substitution

Variables can be substituted into other strings using the `$` character. This is useful for constructing messages.

```bash
$ MY_MESSAGE="Hello World"
$ echo "I said $MY_MESSAGE"
I said Hello World
```

### ✔ Command Substitution

Commands can be substituted into other strings using the `$()` syntax. This is useful for constructing messages.

```bash
$ echo "I said $(echo Hello World)"
I said Hello World
```

## Path Commands 🏴‍☠️

The `PATH` variable is a special environment variable that is used to store a list of directories. When a user runs a command, the shell looks for that command in each directory in the `PATH` variable. If the command is found, it is run. If the command is not found, an error is displayed. Restarting the shell will reload the `PATH` variable.

### ✔ Setting the Path

The `PATH` variable can be set using the `export` command.

```bash
$ export PATH="/usr/local/bin:/usr/bin:/bin"
```

### ✔ Adding to the Path

The `PATH` variable can be added to using the `:` operator.

```bash
$ export PATH="$PATH:/usr/local/bin"
```

### ✔ Prepending to the Path

The `PATH` variable can be prepended to using the `:` operator.

```bash
$ export PATH="/usr/local/bin:$PATH"
```

### ✔ Unsetting the Path

The `PATH` variable can be unset using the `unset` command.

```bash
$ unset PATH
```

## Special Characters 🏴‍☠️

There are a few special characters that have special meanings to the shell. These characters are used to perform operations like globbing, piping, and redirection.

| Character | Name         | Description                                 | input     | output      |
| --------- | ------------ | ------------------------------------------- | --------- | ----------- |
| `*`       | glob         | matches zero or more characters             | `echo *`  | `README.md` |
| `.`       | dot          | Current directory                           | `echo .`  | `.`         |
| `..`      | dot          | Parent directory                            | `echo ..` | `..`        |
| `!`       | bang         | negation, history                           | `echo !`  | `echo !`    |
|           |              | pipe                                        | pipe      | `echo       |
| `/`       | slash        | Directory separator, search command         | `echo /`  | `echo /`    |
| `\`       | backslash    | escape character, line continuation         | `echo \`  | `echo \`    |
| `$`       | dollar       | variable substitution, command substitution | `echo $`  | `echo $`    |
| `'`       | single quote | literal string                              | `echo '`  | `echo '`    |
| `"`       | double quote | literal string, command substitution        | `echo "`  | `echo "`    |
| `~`       | tilde        | home directory, user directory, negation    | `echo ~`  | `echo ~`    |
| `&`       | ampersand    | background, history                         | `echo &`  | `echo &`    |
| `^`       | caret        | negation, beginning of line, history        | `echo ^`  | `echo ^`    |
| `#`       | hash         | comment, history                            | `echo #`  | `echo #`    |
| `[]`      | brackets     | character class                             | `echo []` | `echo []`   |
| `{}`      | braces       | brace expansion                             | `echo {}` | `echo {}`   |
| `()`      | parentheses  | grouping, command substitution              | `echo ()` | `echo ()`   |
| `;`       | semicolon    | command separator                           | `echo ;`  | `echo ;`    |
| `-`       | dash         | option, history                             | `echo -`  | `echo -`    |

## Command Line Editing 🏴‍☠️

The shell provides a number of features for editing the command line. These features are useful for correcting typos and editing commands.

| Key Combination | Description                                                         |
| --------------- | ------------------------------------------------------------------- |
| `Ctrl-a`        | Move to the beginning of the line.                                  |
| `Ctrl-e`        | Move to the end of the line.                                        |
| `Ctrl-b`        | Move back one character.                                            |
| `Ctrl-f`        | Move forward one character.                                         |
| `Ctrl-d`        | Delete the character under the cursor.                              |
| `Ctrl-k`        | Delete the text from the cursor to the end of the line.             |
| `Ctrl-u`        | Delete the text from the cursor to the beginning of the line (CUT). |
| `Ctrl-y`        | Paste the text that was CUT with `Ctrl-u`                           |
| `Ctrl-w`        | Delete the word before the cursor.                                  |
| `Ctrl-l`        | Clear the screen.                                                   |
| `Ctrl-r`        | Search the history.                                                 |
| `Ctrl-g`        | Cancel the current command.                                         |
| `Ctrl-c`        | Cancel the current command.                                         |
| `Ctrl-z`        | Suspend the current command.                                        |
| `Ctrl-p`        | Move to the previous command in the history.                        |
| `Ctrl-n`        | Move to the next command in the history.                            |
| `Ctrl-_`        | Undo the last edit.                                                 |
| `Alt-b`         | Move back one word.                                                 |
| `Alt-f`         | Move forward one word.                                              |
| `Alt-d`         | Delete the word after the cursor.                                   |
| `Alt-Backspace` | Delete the word before the cursor.                                  |
| `Alt-<`         | Move to the beginning of the history.                               |
| `Alt->`         | Move to the end of the history.                                     |
| `Alt-.`         | Insert the last argument of the previous command.                   |
| `Alt-*`         | Insert all of the arguments of the previous command.                |
| `Alt-?`         | List the possible completions of the current word.                  |
| `Alt-Tab`       | Cycle through the possible completions of the current word.         |
| `Alt-Enter`     | Insert a newline.                                                   |
| `Alt-Left`      | Move back one word.                                                 |
| `Alt-Right`     | Move forward one word.                                              |
| `Alt-Up`        | Move to the previous command in the history.                        |
| `Alt-Down`      | Move to the next command in the history.                            |
| `Alt-Delete`    | Delete the word after the cursor.                                   |
| `Alt-Backspace` | Delete the word before the cursor.                                  |

---

## Change Password (passwd) 🏴‍☠️

```ssh
$ passwd
Current password:
New password:
Retype new password:
passwd: password updated successfully
```

---

## Text Editors 🏴‍☠️

A text editor is a program that allows you to edit plain text files. It is a very basic tool that is used by programmers to create and edit source code. It is also used by non-programmers to create and edit text files, such as configuration files, documentation files, and so on.

## Text Editors in Linux 🏴‍☠️

- [**Vim**](https://www.tutorialspoint.com/vim/index.htm): Vim is a highly configurable text editor built to enable efficient text editing.
- [**Emacs**](https://www.gnu.org/software/emacs/tour/): Emacs is an extensible, customizable text editor—and more. At its core is an interpreter for Emacs Lisp, a dialect of the Lisp programming language with extensions to support text editing.
- [**Nano**](https://www.tutorialspoint.com/how-to-use-nano-text-editor): Nano is a small and friendly text editor. It aims to replace Pico, the default editor on most Unix systems.
- [**Gedit**](): Gedit is a text editor for the GNOME desktop environment. It is designed to be simple and easy to use, while still providing all the necessary features for advanced users.

## Vim 🏴‍☠️

| Description | Example        |
| ----------- | -------------- |
| Open a file | `vim filename` |
| Edit        | `i`            |
| Save a file | `:w`           |
| Exit        | `:q`           |

Note: Vim is an editor that is used to edit text files, you can check how to use Vim in the [Vim Tutorial](https://www.tutorialspoint.com/vim/index.htm).

---
