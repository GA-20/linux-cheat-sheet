# Linux Scentials Commands

## The terminal

The terminal is a windows which allow to communicate with a shell.

## The shell 🏴‍☠️

The shell is program stored in the `/bin/sh` that run commands, these commands can be other programs or built-in features. The shell is also a programming language that can be used to automate tasks.

## The command

- Executable: a program that can be run by the shell, whriten in any language.
- Built-in: a feature of the shell, written in C.
- Shell function: extternal program written in with the shell language.
- Alias: a shortcut for a command.

A command is a program that can be run by the shell. A command can be a built-in feature or a program stored in the `/bin` directory.

## The standard input, output and error🏴‍☠️

### ✔ Standard input (stdin)

The standard input is the input that a program receives from the keyboard. It is represented by the file descriptor 0.

### ✔ Standard output (stdout)

The standard output is the output that a program sends to the shell windows. It is represented by the file descriptor 1.

### ✔ Standard error (stderr)

The standard error is the output that a program sends to the shell windows when it encounters an error. It is represented by the file descriptor 2.

## Arguments 🏴‍☠️

Arguments are the parameters that a program receives from the shell. They are separated by spaces.

### `--help`

The `--help` argument is a special argument that is used to display the help of a program.

example:

```bash
$ ls --help
```

### `whatis`

The `whatis` command is used to display the help of a program.

example:

```bash
$ whatis ls
```

### `man`

The `man` command is used to display the manual of a program.


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
| `?`    | Match a exactly one character  (`???` match tree char)                                  | `ls b?at`  | `boat` and `brat`     |
| `[[:upper:]]*`  | Match a string that start with an uppercase letter | `ls [[:upper:]]*` | `File1 File2` |
| `[[:lower:]]*`  | Match a string that start with an lowercase letter | `ls [[:lower:]]*` | `file1 file2` |
| `[[:digit:]]*`  | Match a string that start with a digit | `ls [[:digit:]]*` | `1file 2file` |
| `[[:alnum:]]*`  | Match a string that start with a digit or a letter | `ls [[:alnum:]]*` | `1file 2file File1 File2 file1 file2` |
| `[[:alpha:]]*`  | Match a string that start with a letter | `ls [[:alpha:]]*` | `File1 File2 file1 file2` |
| `[[:blank:]]*`  | Match a string that start with a space or a tab | `ls [[:blank:]]*` | ` File1 File2 file1 file2` |
| `[[:cntrl:]]*`  | Match a string that start with a control character | `ls [[:cntrl:]]*` | `` |
| `[[:graph:]]*`  | Match a string that start with a printable character except space | `ls [[:graph:]]*` | `File1 File2 file1 file2` |
| `[[:print:]]*`  | Match a string that start with a printable character | `ls [[:print:]]*` | ` File1 File2 file1 file2` |
| `[[:punct:]]*`  | Match a string that start with a punctuation character | `ls [[:punct:]]*` | ` File1 File2 file1 file2` |
| `[[:space:]]*`  | Match a string that start with a space | `ls [[:space:]]*` | ` File1 File2 file1 file2` |
| `[[:xdigit:]]*`  | Match a string that start with a hexadecimal digit | `ls [[:xdigit:]]*` | `1file 2file` |
| `[[:word:]]*`  | Match a string that start with a word character | `ls [[:word:]]*` | `1file 2file File1 File2 file1 file2` |
| `[[:ascii:]]*`  | Match a string that start with an ascii character | `ls [[:ascii:]]*` | `1file 2file File1 File2 file1 file2` |

## ✔ Moving around

### `ls` - List directory contents

```bash
$ ls
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-a`     | List all files, including hidden files                                      |
| `-l`     | List in long format                                                         |
| `-h`     | Print sizes in human readable format (e.g., 1K 234M 2G)                      |
| `-r`     | Reverse the order of the sort                                                |
| `-t`     | Sort by time modified (most recently modified first) before sorting the operands by lexicographical order. |
| `-R`     | Recursively list subdirectories encountered.                                |
| `-S`     | Sort files by size                                                          |

### `cd` - Change directory

  ```bash
  $ cd <directory>
  ```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-`      | Change to the previous directory                                            |
| `~`      | Change to the home directory                                                |
| `.`      | Change to the current directory                                             |
| `..`     | Change to the parent directory                                              |

### `nautlius` - File manager

Open the file manager.

 ```bash
 $ nautlius
 ```

## ✔ Creating and removing files and directories

### `tree`

List contents of directories in a tree-like format

```bash
$ tree
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-a`     | List all files, including hidden files                                      |
| `-d`     | List directories only                                                       |
| `-f`     | Print the full path prefix for each file                                    |
| `-L + N`     | Descend only level directories deep                                         |
| `-P`     | Print the full path prefix for each file                                    |
| `-I`     | Do not list files that match the given pattern                              |


### File

The `file` command is used to determine the type of a file.

```bash
$ file file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-b`     | Print the file type in brief mode                                           |
| `-i`     | Print the MIME type                                                         |
| `-h`     | Print the file type in human readable format                                |
| `-z`     | Print the file type in zero terminated format                               |
| `-Z`     | Print the SELinux security context of the file                              |

### `touch`

The `touch` command is used to create a file if it doesn't exist, otherwise update the last modification time.

```bash
$ touch file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-a`     | Change only the access time                                                 |
| `-c`     | Do not create any files                                                     |
| `-d`     | Parse STRING and use it instead of current time                             |
| `-m`     | Change only the modification time                                           |
| `-r`     | Use this file's times instead of current time                               |
| `-t`     | Parse STRING and use it instead of current time                             |

### `rm`

The `rm` command is used to remove a file or directory.

```bash
$ rm file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-f`     | Ignore nonexistent files and arguments, never prompt                         |
| `-i`     | Prompt before every removal                                                  |
| `-r`     | Remove directories and their contents recursively                            |
| `-v`     | Explain what is being done                                                   |

### `mv`

The `mv` command is used to move a file or directory.

```bash
$ mv file1 directory1/file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-f`     | Do not prompt before overwriting                                             |
| `-i`     | Prompt before overwrite                                                      |
| `-n`     | Do not overwrite an existing file                                            |
| `-u`     | Move only when the SOURCE file is newer than the destination file or when the destination file is missing |

### `cp`

The `cp` command is used to copy a file or directory.

```bash
$ cp file1 file2
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-a`     | this option preserves the original file's attributes                         |
| `-r`     | Copy directories recursively                                                 |
| `-f`     | Do not prompt before overwriting                                             |
| `-i`     | Prompt before overwrite                                                      |
| `-n`     | Do not overwrite an existing file                                            |
| `-u`     | Copy only when the SOURCE file is newer than the destination file or when the destination file is missing |
| `-v`     | Explain what is being done                                                   |
| `-l`     | Make hard links instead of copying                                          |
| `-s`     | Make symbolic links instead of copying                                       |
| `-P`     | Preserve the attributes of the original file                                 |

### `rmdir`

The `rmdir` command is used to remove a directory.

```bash
$ rmdir directory1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-p`     | Remove the parent directories as well                                        |
| `-v`     | Explain what is being done                                                   |
| `-i`     | Prompt before every removal                                                  |
| `-I`     | Ignore nonexistent directories, never prompt                                 |

### `echo`

The `echo` command is used to print the arguments.

```bash
$ echo hello world
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-e`     | Enable interpretation of backslash escapes                                   |
| `-n`     | Do not output the trailing newline                                           |
| `-E`     | Disable interpretation of backslash escapes                                  |


## Explore files

### `cat`

The `cat` command is used to concatenate files and print on the standard output.

```bash
$ cat file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-A`     | Equivalent to -vET                                                           |
| `-b`     | Number the non-blank output lines, starting at 1                             |
| `-e`     | Equivalent to -vE                                                            |
| `-E`     | Display $ at end of each line                                                |
| `-n`     | Number all output lines, starting at 1                                       |
| `-s`     | Squeeze multiple adjacent empty lines, causing the output to be single spaced |
| `-t`     | Equivalent to -vT                                                            |
| `-T`     | Display TAB characters as ^I                                                 |
| `-u`     | (ignored)                                                                   |
| `-v`     | Display non-printing characters so they are visible                          |

### `head`

The `head` command is used to output the first part of files.

```bash
$ head file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-c`     | Print the first NUM bytes of each file                                       |
| `-n`     | Print the first NUM lines instead of the first 10                            |
| `-q`     | Never print headers giving file names                                        |
| `-v`     | Always print headers giving file names                                       |

### `tail`

The `tail` command is used to output the last part of files.

```bash
tail file1
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-c`     | Print the last NUM bytes of each file                                        |
| `-n`     | Print the last NUM lines instead of the last 10                              |
| `-q`     | Never print headers giving file names                                        |
| `-v`     | Always print headers giving file names                                       |

### `less`

The `less` command is used to view the contents of a file.

```bash
$ less file1
```

Actions:

| Action | Description                                                                 |
| ------ | --------------------------------------------------------------------------- |
| `q`    | Quit                                                                         |
| `h`    | Show help                                                                    |
| `j`    | Scroll down                                                                  |
| `k`    | Scroll up                                                                    |
| `G`    | Go to the end of the file                                                    |
| `g`    | Go to the beginning of the file                                              |
| `/`    | Search for a string                                                          |
| `n`    | Go to the next search result                                                 |
| `N`    | Go to the previous search result                                             |

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-e`     | Quit if the file is empty                                                   |
| `-f`     | Quit if the file is smaller than the screen                                  |
| `-g`     | Quit if the file is smaller than the screen                                  |
| `-i`     | Ignore case when searching                                                  |
| `-m`     | Quit if the file is smaller than the screen                                  |
| `-N`     | Show line numbers                                                           |
| `-S`     | Chop long lines                                                             |

### Aliases

Aliases are a way to create shortcuts for commands. For example, you can create an alias for `git status` to `gs`. The life of an alias is limited to the current shell session. To make an alias permanent, you need to add it to your `~/.bashrc` file.

```bash
$ alias gs='git status'
```

Arguments:

| Argument | Description                                                                 |
| -------- | --------------------------------------------------------------------------- |
| `-p`     | Print the alias definition                                                   |
| `-r`     | Remove an alias                                                              |
| `-s`     | List all aliases                                                             |


## Searching for files

### `find`

The `find` command is used to search for files and directories based so some conditions like permissions, users, groups, file types, date, size, and other possible criteria.

```bash
$ find [path] [options] [expression]
```

| Argument  | Description                                   | Input                | Output                                                        |
| --------- | --------------------------------------------- | -------------------- | ------------------------------------------------------------- |
| path      | The path to search in                         | `find /home/user`    | `/home/user/file1` `/home/user/file2` `/home/user/directory1` |
| -name     | The name of the file                          | `find -name file`    | `/home/user/file1` `/home/user/file2`                         |
| -iname    | Find by name ignoring case                    | `find -iname file`   | `/home/user/file1` `/home/user/file2`                         |
| -type     | The type of the file                          | `find -type f`       | `/home/user/file1` `/home/user/file2`                         |
| -perm     | The permissions of the file                   | `find -perm 777`     | `/home/user/file1` `/home/user/file2`                         |
| -print    | Print the result                              | `find -print`        | `/home/user/file1` `/home/user/file2`                         |
| -depth    | Search in subfolders                          | `find -depth`        | `/home/user/file1` `/home/user/file2`                         |
| --version | Print the version of the command              | `find --version`     | `find (GNU findutils) 4.6.0`                                  |
| -cnewer   | Search for files that are newer than the file | `find -cnewer file1` | `/home/user/file2`                                            |

### Grep

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

