# Linux Scentials Commands

## Table of Contents

- [Table of Content](#table-of-contents)
- [The shell](#the-shell)
- [The standard input, output and error](#the-standard-input-output-and-error)
  - [Standard input (stdin)](#standard-input-stdin)
  - [Standard output (stdout)](#standard-output-stdout)
  - [Standard error (stderr)](#standard-error-stderr)
- [Arguments](#arguments)
  - [--help](#help)
- [Wildcards](#wildcards)
- [Commands](#commands)
  - [Moving around](#moving-around)
  - [Creating and removing files and directories](#creating-and-removing-files-and-directories)
  - [Searching for Files](#searching-for-files)
    - [Find](#find)
    - [Grep](#grep)
    - [Less](#less)
    - [Pipe](#pipe)
    - [Redirect](#redirect)
    - [Some more useful commands](#some-more-useful-commands)

## The shell

The shell is program stored in the `/bin/sh` that run commands, these commands can be other programs or built-in features. The shell is also a programming language that can be used to automate tasks.

## The standard input, output and error

### Standard input (stdin)

The standard input is the input that a program receives from the keyboard. It is represented by the file descriptor 0.

### Standard output (stdout)

The standard output is the output that a program sends to the shell windows. It is represented by the file descriptor 1.

### Standard error (stderr)

The standard error is the output that a program sends to the shell windows when it encounters an error. It is represented by the file descriptor 2.

## Arguments

Arguments are the parameters that a program receives from the shell. They are separated by spaces.

### --help

The `--help` argument is a special argument that is used to display the help of a program.

example:

```bash
$ ls --help
```

## Wildcards

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

## Commands

### Moving around

| Command | Description                                                     | shell input     | shell output             |
| ------- | --------------------------------------------------------------- | --------------- | ------------------------ |
| `pwd`   | Print the current working directory                             | `pwd`           | `/home/user`             |
| `cd`    | Change the current working directory                            | `cd /home/user` | No output                |
| `ls`    | List the files and directories in the current working directory | `ls`            | `file1 file2 directory1` |

### Creating and removing files and directories

| Command | Description                                                                    | shell input                 | shell output  |
| ------- | ------------------------------------------------------------------------------ | --------------------------- | ------------- |
| `touch` | Create a file if it doesn't exist, otherwise update the last modification time | `touch file1`               | No output     |
| `mkdir` | Create a directory                                                             | `mkdir directory1`          | No output     |
| `rm`    | Remove a file or directory                                                     | `rm file1`                  | No output     |
| `rmdir` | Remove a directory                                                             | `rmdir directory1`          | No output     |
| `mv`    | Move a file or directory                                                       | `mv file1 directory1/file1` | No output     |
| `cp`    | Copy a file or directory                                                       | `cp file1 file2`            | No output     |
| `echo`  | Print the arguments                                                            | `echo hello world`          | `hello world` |

### Searching for files

#### find

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

#### Grep

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

### Less

The `less` command is used to view the contents of a file, see all the contents of a file without opening it.

```bash
$ less [file]
```

| Argument | Description           | Input          | Output          |
| -------- | --------------------- | -------------- | --------------- |
| file     | The file to view      | `less file`    | `hello world`   |
| -N       | Print the line number | `less -N file` | `1:hello world` |

Note: Use `--help` to see all the options.

### Pipe

The pipe `|` is used to send the output of one command to another command.

```bash
$ grep hello file | less # It will print the lines that contain the string "hello" in the file "file" and then it will open the file with less
```

### Redirect

The redirect `>` is used to redirect the output of a command to a file.

```bash
$ echo hello world > file # It will print "hello world" in the file "file"
```

### Some useful commands

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
