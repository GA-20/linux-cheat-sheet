## Standard Input (STDIN)

Standard input is the default input stream for a program. It is the stream that the program reads from when it is expecting input from the user. It is usually the keyboard, but it can be redirected to read from a file instead.

## Standard Output (STDOUT)

A program's standard output is the stream that it writes its output to. It is usually the screen, but it can be redirected to write to a file instead.

## Standard Error (STDERR)

It is the stream that the program writes to when it is expecting to send error messages to the user. It is usually the screen, but it can be redirected to write to a file instead.

## Redirecting Standard Input, Output and Error

The standard input, output and error can be redirected to files or to other programs. This is done using the following symbols:

| Symbol | Meaning                                     | Example Command              | Redirection Type |
| ------ | ------------------------------------------- | ---------------------------- | ---------------- |
| `<`    | Redirect standard input                     | `cat < file.txt`             | Input            |
| `>`    | Redirect standard output                    | `cat file.txt > file2.txt`   | Output           |
| `>>`   | Append standard output                      | `cat file.txt >> file2.txt`  | Output           |
| `&>`   | Redirect standard output and standard error | `cat file.txt &> file2.txt`  | Output and Error |
| `&>>`  | Append standard output and standard error   | `cat file.txt &>> file2.txt` | Output and Error |
| `2>>`  | Append standard error                       | `cat file.txt 2>> file2.txt` | Error            |
| `2>`   | Redirect standard error                     | `cat file.txt 2> file2.txt`  | Error            |
| `2>&1` | Redirect standard error to standard output  | `cat file.txt 2>&1`          | Error            |

### Pipe (|)

The pipe symbol (`|`) is used to redirect the output of one program to the input of another program. This is called piping.

The following command will print the contents of the file `file.txt` to the screen, but it will only print the first 10 lines:

```bash

cat file.txt | head -n 10
```

## Understanding Error Messages

When a program fails to execute, it will usually print an error message to the screen. The error message will tell you what went wrong and why the program failed to execute. The error message will also tell you how to fix the problem.

### Anatomy of an Error Message

- Program name: The name of the program that failed to execute.
- File name: The name of the file that caused the error.
- The error message: The error message will tell you what went wrong and why the program failed to execute.

### Error Messages vs Warnings

- Error messages: Error messages are messages that tell you that the program failed to execute. They are usually printed to the screen in red.
- Warnings: Warnings are messages that tell you that something went wrong, but the program was able to execute. They are usually printed to the screen in yellow.

### Common Error Messages

| Error Message               | Meaning                                                | Example Command  | Example Error Message                      |
| --------------------------- | ------------------------------------------------------ | ---------------- | ------------------------------------------ |
| `command not found`         | The command was not found.                             | `cat file.txt`   | `cat: command not found`                   |
| `No such file or directory` | The file was not found.                                | `cat file.txt`   | `cat: file.txt: No such file or directory` |
| `File exists`               | The file already exists.                               | `touch file.txt` | `touch: file.txt: File exists`             |
| `Not a directory`           | The file is not a directory                            | `cd file.txt`    | `cd: file.txt: Not a directory`            |
| `Permission denied`         | Permission denied.                                     | `rm file.txt`    | `rm: file.txt: Permission denied`          |
| `No space left on device`   | No space left on device.                               | `rm file.txt`    | `rm: file.txt: No space left on device`    |
| `Operation not permitted`   | Operation not permitted.                               | `rm file.txt`    | `rm: file.txt: Operation not permitted`    |
| `Segmentation fault`        | Tried to access a part of a memory that is not allowed | `rm file.txt`    | `Segmentation fault`                       |

## Control Operators

Control operators are used to control the flow of a program. They are used to change the order in which commands are executed.

### ;

The semicolon (`;`) is used to separate multiple commands on the same line, excute commands synchronously.

```bash
ls; touch file.txt; cat file.txt
```

### &

The ampersand (`&`) is used to separate multiple commands on the same line, excute commands asynchronously. Create a new process in the background.

```bash
ls & touch file.txt & cat file.txt
```

### &&

The `&&` operator is used to execute the second command only if the first command was successful. If the first command fails, the second command will not be executed.

```bash
sudo apt-get update && sudo apt-get upgrade
```

### ||

The `||` operator is used to execute the second command only if the first command fails. If the first command is successful, the second command will not be executed.

```bash
sudo apt-get update || sudo apt-get upgrade
```

### ()

The parentheses (`()`) are used to group commands together. This is useful when you want to execute multiple commands in a single command.

```bash
touch file.txt && (cat file.txt; rm file.txt)
```

### {}

The curly braces (`{}`) are used to group commands together. This is useful when you want to execute multiple commands in a single command.

```bash
touch file.txt && { cat file.txt; rm file.txt }
```

### \#

The hash (`#`) is used to add comments to a script. Anything after the hash will be ignored by the shell.

```bash
# This is a comment
```
