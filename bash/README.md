# Bash

## Shell Types

A shell is a command-line interpreter that allows users to interact with an operating system by typing commands and receiving output. In Linux and other Unix-like operating systems, there are several different types of shells that can be used, each with its own set of features and capabilities.

### SH (Bourne Shell)

This is the original shell developed by Steve Bourne at AT&T Bell Labs. It is the default shell in many Unix-like operating systems, including most versions of Linux.

### CSH (C Shell)

This shell was developed at the University of California, Berkeley, and it is based on the C programming language. It is known for its C-like syntax and its support for command line editing and aliases.

### KSH (Korn Shell)

This is a commercial shell that was developed by David Korn at AT&T Bell Labs. It is an extension of the Bourne shell and includes many of the same features, as well as additional features such as command line editing and arrays.

### BASH (Bourne Again Shell)

This is a popular, free, and open-source shell that is based on the Bourne shell. It is the default shell in many Linux distributions, including Ubuntu and Red Hat Enterprise Linux.

### ZSH (Z Shell)

This is a free and open-source shell that is similar to the Bourne Again shell. It is known for its advanced features, such as support for command line completion and globing.

## What is Bash?

Bash is a command-line interpreter that allows users to interact with an operating system by typing commands and receiving output. It is often used by system administrators to automate tasks and perform system maintenance, as well as by users to execute commands and run programs.

## Create and Run a Bash Script

To create a bash script, you will need to use a text editor to write the script and save it with a `.sh` file extension. The script can then be executed by running the `bash` command followed by the name of the script file.

Here are the steps to create a simple bash script:

1. Open a text editor, such as nano or vi, and create a new file.
2. In the file, type the following lines:

```bash
#!/bin/bash
echo "Hello, world!"
```

3. Save the file with a .sh file extension, such as hello_world.sh.
4. Make the script executable by running the following command:

```bash
chmod +x hello_world.sh
```

5. To run the script, use the bash command followed by the name of the script file:

```bash
bash hello_world.sh
```

**Note** that the first line of the script, #!/bin/bash, is known as the shebang line. It specifies the interpreter that should be used to execute the script, in this case the bash shell. It is important to include this line at the beginning of the script so that the operating system knows how to run it.

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

### Environment Variables

### Environment Variables

These are variables that are set by the operating system or other programs and are available to all programs and processes running on the system. Examples of environment variables include `PATH`, which specifies the directories where the system should search for executables, and `HOME`, which specifies the user's home directory.

```bash
#!/bin/bash

# Print the value of the HOME environment variable
echo "Your home directory is: $HOME"

# Check if the user is root
if [ "$USER" = "root" ]; then
  echo "You are logged in as the root user"
fi
```

### Local Variables

These are variables that are defined and used within a single script or function. They are not available to other programs or processes, and they are typically used to store temporary values or intermediate results.

```bash
#!/bin/bash

# Define a local variable
my_variable="Hello, world!"

# Print the value of the local variable
echo $my_variable

# Use the local variable in a function
my_function() {
  local my_variable="Goodbye, world!"
  echo $my_variable
}

# Call the function
my_function

# Print the value of the local variable again
echo $my_variable
```

In Bash, `local` is a keyword that is used to create a local variable. This means that the variable is only available within the current scope. In contrast, a variable that is not preceded by the `local` keyword is a global variable, which means it can be accessed from anywhere within the script.

```bash
#!/bin/bash

local my_variable="Hello, world!"
my_other_variable="Goodbye, world!"

echo $my_variable
echo $my_other_variable

my_function() {
  echo $my_variable # error
  echo $my_other_variable # Goodbye, world!
}
```

### Shell Variables

These are variables that are defined and used by the bash shell itself. They are typically used to control the behavior of the shell and its built-in commands. Examples of shell variables include `PS1`, which specifies the prompt displayed by the shell, and `IFS`, which specifies the field separator used by the `read` built-in command.

```bash
# This is a Bash script

# Define a shell variable called "my_variable"
my_variable="hello world"

# Print the value of "my_variable"
echo "$my_variable"

# Define a shell variable called "IFS"
# This variable controls the field separator used by the `read` built-in command
IFS=":"

# Use the `read` built-in command to read in a string and split it on the ":" character
read -a my_array <<< "this:is:a:test"

# Print the resulting array
echo "${my_array[@]}"
```

All Shell Variables:

| Shell Variable | Description                                           |
| -------------- | ----------------------------------------------------- |
| `read`         | built-in command to read in a string                  |
| `IFS`          | field separator used by `read`                        |
| `PS1`          | prompt displayed by the shell                         |
| `PS2`          | secondary prompt displayed by the shell               |
| `PS3`          | prompt displayed by the select command                |
| `PS4`          | prompt displayed by the set -x option                 |
| `BASH`         | path to the Bash executable                           |
| `BASH_VERSION` | version of Bash                                       |
| `HOME`         | path to the user's home directory                     |
| `PATH`         | directories where the system searches for executables |
| `PWD`          | path to the current working directory                 |
| `RANDOM`       | random number between 0 and 32767                     |
| `UID`          | user ID of the current user                           |
| `USER`         | name of the current user                              |

### User-defined Variables

These are variables that are defined by the user and can be used to store any values or information needed by the script. They can be local or global in scope, depending on how they are defined and used.

### Special Variables

| Variable | Description                                                                                                                                       |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| $0       | The name of the Bash script                                                                                                                       |
| $n       | These variables correspond to the arguments with which a script was invoked. For example, $1 is the first argument and $2 is the second argument. |
| $#       | The number of arguments supplied to a script                                                                                                      |
| $\*      | All the arguments are double quoted. If a script receives two arguments, $\* is equivalent to $1 $2.                                              |
| $@       | All the arguments are individually double quoted. If a script receives two arguments, $@ is equivalent to $1 $2.                                  |
| $?       | The exit status of the last command executed                                                                                                      |
| $$       | The process number of the current script                                                                                                          |
| $!       | The process number of the last background command                                                                                                 |
| $-       | The current options set for the shell                                                                                                             |
| $\_      | The last argument of the previous command                                                                                                         |

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

| Operator | Description    |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| \*       | Multiplication |
| /        | Division       |
| %        | Modulus        |
| \*\*     | Exponentiation |
| ++       | Increment      |
| --       | Decrement      |
| =        | Assignment     |

### Relational Operators

| Operator | Description                                                                    |
| -------- | ------------------------------------------------------------------------------ |
| -eq      | Returns true if the values are equal                                           |
| -ne      | Returns true if the values are not equal                                       |
| -gt      | Returns true if the left operand is greater than the right operand             |
| -ge      | Returns true if the left operand is greater than or equal to the right operand |
| -lt      | Returns true if the left operand is less than the right operand                |
| -le      | Returns true if the left operand is less than or equal to the right operand    |

### Logical Operators

| Operator | Description                                            |
| -------- | ------------------------------------------------------ |
| !        | Returns true if the statement is false                 |
| -o       | Returns true if either statement is true               |
| -a       | Returns true if both statements are true               |
| &&       | Returns true if both statements are true               |
| \|\|     | Returns true if either statement is true               |
| &        | Returns true if both statements are true               |
| \|       | Returns true if either statement is true               |
| ^        | Returns true if either statement is true, but not both |
| ~        | Returns true if the pattern matches                    |
| =~       | Returns true if the pattern matches                    |

### String Operators

| Operator | Description                               |
| -------- | ----------------------------------------- |
| =        | Returns true if the strings are equal     |
| !=       | Returns true if the strings are not equal |
| -z       | Returns true if the string is empty       |
| -n       | Returns true if the string is not empty   |
| str      | Returns true if the string is not empty   |

### File Operators

| Operator | Description                                                                                              |
| -------- | -------------------------------------------------------------------------------------------------------- |
| -b       | Returns true if the file is a block special file                                                         |
| -c       | Returns true if the file is a character special file                                                     |
| -d       | Returns true if the file is a directory                                                                  |
| -e       | Returns true if the file exists (note that this is not particularly portable, thus -f is generally used) |
| -f       | Returns true if the provided string is a file                                                            |
| -g       | Returns true if the group id is set on a file                                                            |
| -k       | Returns true if the sticky bit is set                                                                    |
| -p       | Returns true if the file is a named pipe                                                                 |
| -r       | Returns true if the file is readable                                                                     |
| -s       | Returns true if the file has a non-zero size                                                             |
| -t       | Returns true if the file descriptor is open and associated with a terminal                               |
| -u       | Returns true if the user id is set on a file                                                             |
| -w       | Returns true if the file is writable                                                                     |
| -x       | Returns true if the file is an executable                                                                |

## Arrays Variables

```bash
#!/bin/bash
my_array=("A" "B" "C" "D" "E")
```

### Accessing Array Elements

```bash
#!/bin/bash
my_array=("A" "B" "C" "D" "E")
echo ${my_array[0]}
echo ${my_array[1]}
echo ${my_array[2]}
echo ${my_array[3]}
```

### Append Elements to an Array

```bash
#!/bin/bash
my_array=("A" "B" "C" "D" "E")
my_array+=("F")
echo ${my_array[@]}
```

### Get the Length of an Array

```bash
#!/bin/bash
my_array=("A" "B" "C" "D" "E")
echo ${#my_array[@]}
```

### Get the Length of an Array Element

```bash
#!/bin/bash
my_array=("A" "B" "C" "D" "E")
echo ${#my_array[0]}
```

## Conditional Statements

### if Statement

```bash
#!/bin/bash
if [ 1 -eq 1 ]
then
    echo "1 -eq 1 : true"
fi
```

### if-else Statement

```bash
#!/bin/bash
if [ 1 -eq 1 ]
then
    echo "1 -eq 1 : true"
else
    echo "1 -eq 1 : false"
fi
```

### if-elif-else Statement

```bash
#!/bin/bash
if [ 1 -eq 1 ]
then
    echo "1 -eq 1 : true"
elif [ 1 -eq 2 ]
then
    echo "1 -eq 2 : true"
else
    echo "1 -eq 1 : false"
fi
```

### Nested if Statement

```bash
#!/bin/bash
if [ 1 -eq 1 ]
then
    echo "1 -eq 1 : true"
    if [ 1 -eq 2 ]
    then
        echo "1 -eq 2 : true"
    else
        echo "1 -eq 2 : false"
    fi
else
    echo "1 -eq 1 : false"
fi
```

### Case Statement

```bash
#!/bin/bash
echo "Enter a number between 1 and 3:"
read aNumber
case $aNumber in
    1) echo "You entered #1";;
    2) echo "You entered #2";;
    3) echo "You entered #3";;
    *) echo "You did not follow directions!";;
esac
```

### For Loop

```bash
#!/bin/bash
for i in 1 2 3 4 5
do
    echo "Welcome $i times"
done
```

### While Loop

```bash
#!/bin/bash
i=1
while [ $i -le 5 ]
do
    echo "Welcome $i times"
    i=$((i+1))
done
```

### Until Loop

```bash
#!/bin/bash
i=1
until [ $i -gt 5 ]
do
    echo "Welcome $i times"
    i=$((i+1))
done
```

### Break Statement

```bash
#!/bin/bash
for i in 1 2 3 4 5
do
    echo "Welcome $i times"
    if [ $i -eq 3 ]
    then
        break
    fi
done
```

### Continue Statement

```bash
#!/bin/bash
for i in 1 2 3 4 5
do
    if [ $i -eq 3 ]
    then
        continue
    fi
    echo "Welcome $i times"
done
```

### Select Statement

```bash
#!/bin/bash
select name in "Mark" "John" "Tom"
do
    echo "Hello $name"
done
```

## Shell Substitutions

The substitution is the process of replacing a portion of a string with another string. The shell performs substitution on a string when it is assigned to a variable or when it is used as an argument to a command.

### Command Substitution

```bash
#!/bin/bash
today=$(date)
echo "Today is $today"
```

### Arithmetic Substitution

```bash
#!/bin/bash
a=10
b=20
c=$((a+b))
echo "c = $c"
```

### Brace Expansion

```bash
#!/bin/bash
echo {A..Z}
echo {a..z}
echo {0..9}
```

| Escape Sequence | Description               |
| --------------- | ------------------------- |
| \\              | Backslash                 |
| \a              | Alert (Beep, Bell)        |
| \b              | Backspace                 |
| \c              | Produce no further output |
| \f              | Formfeed                  |
| \n              | Newline                   |
| \r              | Carriage Return           |
| \t              | Horizontal Tab            |
| \v              | Vertical Tab              |

### Variable Substitution

Enables you to substitute the value of a variable or the output of a command into a string.

| Escape Sequence          | Description                                                                                                                                                                                                                      |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ${var}                   | Substitute the value of var                                                                                                                                                                                                      |
| ${var:-word}             | If var is unset or null, the expansion of word is substituted. Otherwise, the value of var is substituted.                                                                                                                       |
| ${var:=word}             | If var is unset or null, the expansion of word is assigned to var. The value of var is then substituted.                                                                                                                         |
| ${var:?word}             | If var is unset or null, the expansion of word (or a message to that effect if word is not present) is written to the standard error and the shell, if it is not interactive, exits. Otherwise, the value of var is substituted. |
| ${var:+word}             | If var is null or unset, nothing is substituted, otherwise the expansion of word is substituted.                                                                                                                                 |
| ${#var}                  | The length of the value of var is substituted.                                                                                                                                                                                   |
| ${var:offset}            | The substring of var starting at offset is substituted. An offset of 0 is the first character of the string.                                                                                                                     |
| ${var:offset:length}     | The substring of var starting at offset and extending for length characters is substituted.                                                                                                                                      |
| ${var#word}              | The shortest match of the front of var against the regular expression pattern formed from word is deleted.                                                                                                                       |
| ${var##word}             | The longest match of the front of var against the regular expression pattern formed from word is deleted.                                                                                                                        |
| ${var%word}              | The shortest match of the back of var against the regular expression pattern formed from word is deleted.                                                                                                                        |
| ${var%%word}             | The longest match of the back of var against the regular expression pattern formed from word is deleted.                                                                                                                         |
| ${var/word/replacement}  | The first match of the regular expression pattern formed from word is replaced with replacement.                                                                                                                                 |
| ${var//word/replacement} | All matches of the regular expression pattern formed from word are replaced with replacement.                                                                                                                                    |
| ${var/#word/replacement} | If the front of var matches the regular expression pattern formed from word, then the match is replaced with replacement.                                                                                                        |
| ${var/%word/replacement} | If the back of var matches the regular expression pattern formed from word, then the match is replaced with replacement.                                                                                                         |

## Functions

```bash
#!/bin/bash
function hello {
    echo "Hello World"
}

hello
```
