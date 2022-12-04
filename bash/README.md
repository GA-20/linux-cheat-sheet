# Bash


## Shell Types

### SH (Bourne Shell)

The original Unix shell, written by Steve Bourne. It is the default shell on most Unix systems.

### CSH (C Shell)

A shell written by Bill Joy. It is the default shell on most BSD systems, with a syntax similar to the C programming language.

### KSH (Korn Shell)

A shell written by David Korn. Combines the features of the KSH, XSH, SH and TSH shells.

### BASH (Bourne Again Shell)

A shell written by Brian Fox. It is the default shell on most Linux systems, and is a superset of the SH shell.

### ZSH (Z Shell)

A shell written by Paul Falstad. It is a superset of the KSH shell.


## What is Bash?

Bash is a command language interpreter that executes commands read from the standard input or from a file. Bash is a superset of the SH shell, and incorporates useful features from the KSH and CSH shells (see the comparison of shells).

## Create and Run a Bash Script

```bash
#!/bin/bash

pwd
ls
```

- add execute permission to the script

```bash
chmod +x script.sh
bash ./script.sh
./script.sh
```

## Variables

A variable could be a string, a number, a list of strings, a list of numbers, a list of lists, etc.

- **naming convention**: variable names can contain only letters, numbers, and the underscore character. They must begin with a letter,variable names are case sensitive.

```bash
#!/bin/bash
FIRST_NAME="John"
last_name="Doe"
age=25
```

### Scalar Variables

The simplest type of variable is a scalar variable, which contains a single value. A scalar variable can contain a string, a number, or a list of strings or numbers.

### Read-only Variables

```bash
#!/bin/bash
FIRST_NAME="John"
readonly FIRST_NAME
FIRST_NAME="Doe" # error
```

### Unsetting Variables

Unsetting a variable removes its value and makes it unavailable for use.

```bash
#!/bin/bash
FIRST_NAME="John"
unset FIRST_NAME
echo $FIRST_NAME # nothing
```

## Variable Types

### Local Variables

Local variables are variables that are available only within the current instance of the shell. Local variables are not passed to programs or scripts that are executed by the shell.

```bash
#!/bin/bash
function bash {
    local FIRST_NAME="John"
    echo $FIRST_NAME
}
bash
echo $FIRST_NAME # nothing
```

### Environment Variables

Environment variables are available to any child process of the shell. Environment variables are inherited by subshells, and can be passed to programs or scripts that are executed by the shell.

```bash
#!/bin/bash
FIRST_NAME="John"
export FIRST_NAME
bash
echo $FIRST_NAME # John
```

### Shell Variables

Shell variables are special variables that are set by the shell and are required for it to function properly.

```bash
#!/bin/bash
echo $BASH # /bin/bash
echo $BASH_VERSION # 4.4.12(1)-release
echo $HOME # /home/username
echo $PWD # /home/username
```

All shell variables:

| Variable | Description |
| --- | --- |
| $BASH | The full path of the bash executable |
| $BASH_VERSION | The version of bash |
| $HOME | The home directory of the current user |
| $PWD | The present working directory |
| $RANDOM | Returns a different random number each time is it referred to |
| $SECONDS | The number of seconds since the shell was started |
| $UID | The user ID of the current user |
| $USER | The username of the current user |
| $HOSTNAME | The hostname of the machine the shell is running on |
| $OSTYPE | The type of operating system the shell is running on |
| $MACHTYPE | The type of machine the shell is running on |
| $IFS | The Internal Field Separator |
| $LINENO | Returns the current line number in the Bash script |
| $PS1 | The primary prompt string |
| $PS2 | The secondary prompt string |
| $PS3 | The prompt string for select commands |
| $PS4 | The prompt string for debugging traces |
| $PATH | The search path for commands |
| $EDITOR | The default text editor for the shell |
| $MAIL | The location of the mailboxes |
| $MAILCHECK | The number of seconds between mail checks |
| $MAILPATH | The default location for new mail |
| $PAGER | The default program for paging output |
| $HISTSIZE | The number of commands to remember in the history list |
| $HISTFILESIZE | The number of commands to remember in the history file |
| $TERM | The type of terminal being used |
| $SHELL | The shell program being used |
| $OLDPWD | The previous working directory |
| $COLUMNS | The number of columns in the terminal |
| $LINES | The number of lines in the terminal |
| $TMOUT | The number of seconds of idle time before logout |
| $OPTIND | The index of the next argument to be processed by getopts |
| $OPTARG | The last option argument processed by getopts |
| $REPLY | The last line read by the read builtin command |
| $FUNCNAME | The name of the current function |

### Special Variables

| Variable | Description |
| --- | --- |
| $0 | The name of the Bash script |
| $n | These variables correspond to the arguments with which a script was invoked. For example, $1 is the first argument and $2 is the second argument. |
| $# | The number of arguments supplied to a script |
| $* | All the arguments are double quoted. If a script receives two arguments, $* is equivalent to $1 $2. |
| $@ | All the arguments are individually double quoted. If a script receives two arguments, $@ is equivalent to $1 $2. |
| $? | The exit status of the last command executed |
| $$ | The process number of the current script |
| $! | The process number of the last background command |
| $- | The current options set for the shell |
| $_ | The last argument of the previous command |


## Command Line Arguments

The arguments are stored in special variables. The first argument is stored in $1, the second in $2, and so on.

```bash
#!/bin/bash
echo $1 $2 $3 ' -> echo $1 $2 $3'
args=("$@")
echo ${args[0]} ${args[1]} ${args[2]} ' -> args=("$@"); echo ${args[0]} ${args[1]} ${args[2]}'

# ---------------

echo "File Name: $0"
echo "First Parameter : $1"
echo "Second Parameter : $2"
echo "Quoted Values: $@"
echo "Quoted Values: $*"
echo "Total Number of Parameters 
```



## Operators

### Arithmetic Operators

| Operator | Description |
| --- | --- |
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| % | Modulus |
| ** | Exponentiation |
| ++ | Increment |
| -- | Decrement |
| = | Assignment |

### Relational Operators

| Operator | Description |
| --- | --- |
| -eq | Returns true if the values are equal |
| -ne | Returns true if the values are not equal |
| -gt | Returns true if the left operand is greater than the right operand |
| -ge | Returns true if the left operand is greater than or equal to the right operand |
| -lt | Returns true if the left operand is less than the right operand |
| -le | Returns true if the left operand is less than or equal to the right operand |


### Logical Operators

| Operator | Description |
| --- | --- |
| ! | Returns true if the statement is false |
| -o | Returns true if either statement is true |
| -a | Returns true if both statements are true |
| && | Returns true if both statements are true |
| \|\| | Returns true if either statement is true |
| & | Returns true if both statements are true |
| \| | Returns true if either statement is true |
| ^ | Returns true if either statement is true, but not both |
| ~ | Returns true if the pattern matches |
| =~ | Returns true if the pattern matches |

### String Operators

| Operator | Description |
| --- | --- |
| = | Returns true if the strings are equal |
| != | Returns true if the strings are not equal |
| -z | Returns true if the string is empty |
| -n | Returns true if the string is not empty |
| str | Returns true if the string is not empty |

### File Operators

| Operator | Description |
| --- | --- |
| -b | Returns true if the file is a block special file |
| -c | Returns true if the file is a character special file |
| -d | Returns true if the file is a directory |
| -e | Returns true if the file exists (note that this is not particularly portable, thus -f is generally used) |
| -f | Returns true if the provided string is a file |
| -g | Returns true if the group id is set on a file |
| -k | Returns true if the sticky bit is set |
| -p | Returns true if the file is a named pipe |
| -r | Returns true if the file is readable |
| -s | Returns true if the file has a non-zero size |
| -t | Returns true if the file descriptor is open and associated with a terminal |
| -u | Returns true if the user id is set on a file |
| -w | Returns true if the file is writable |
| -x | Returns true if the file is an executable |

