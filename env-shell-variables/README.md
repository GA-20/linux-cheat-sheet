## Table of Content

- [Setting Variables](#setting-variables)
- [Variable Types](#variable-types)
  - [Local Variables](#local-variables)
  - [Environment Variables](#environment-variables)
- [Unsetting Variables](#unsetting-variables)
- [Variable Substitution](#variable-substitution)
- [Command Substitution](#command-substitution)
- [Path Commands](#path-commands)
  - [Setting the Path](#setting-the-path)
  - [Adding to the Path](#adding-to-the-path)
  - [Prepending to the Path](#prepending-to-the-path)
  - [Unsetting the Path](#unsetting-the-path)
- [Special Characters](#special-characters)
- [Command Line Editing](#command-line-editing)

## Shell Variables

Shell variables are a way to store information that can be accessed by the shell and programs that the shell runs. They are useful for passing information to scripts and storing configuration information.

### Setting Variables

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

### Variable Types

There are two types of variables: local and environment variables. Local variables are only available to the current shell and any programs that it runs. Environment variables are available to any program that the user runs.

#### Local Variables

Local variables are set by assigning a value to them using the `=` operator. They are used to store information for the current shell and any programs that it runs.

```bash
$ MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World
```

#### Environment Variables

Environment variables are set by assigning a value to them using the `export` command. They are used to store information for any program that the user runs.

```bash
$ export MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World
```

### Unsetting Variables

Variables can be unset by using the `unset` command. This removes the variable from the current shell.

```bash
$ MY_MESSAGE="Hello World"
$ echo $MY_MESSAGE
Hello World

$ unset MY_MESSAGE
$ echo $MY_MESSAGE

$
```

### Variable Substitution

Variables can be substituted into other strings using the `$` character. This is useful for constructing messages.

```bash
$ MY_MESSAGE="Hello World"
$ echo "I said $MY_MESSAGE"
I said Hello World
```

### Command Substitution

Commands can be substituted into other strings using the `$()` syntax. This is useful for constructing messages.

```bash
$ echo "I said $(echo Hello World)"
I said Hello World
```

## Path Commands

The `PATH` variable is a special environment variable that is used to store a list of directories. When a user runs a command, the shell looks for that command in each directory in the `PATH` variable. If the command is found, it is run. If the command is not found, an error is displayed. Restarting the shell will reload the `PATH` variable.

### Setting the Path

The `PATH` variable can be set using the `export` command.

```bash
$ export PATH="/usr/local/bin:/usr/bin:/bin"
```

### Adding to the Path

The `PATH` variable can be added to using the `:` operator.

```bash
$ export PATH="$PATH:/usr/local/bin"
```

### Prepending to the Path

The `PATH` variable can be prepended to using the `:` operator.

```bash
$ export PATH="/usr/local/bin:$PATH"
```

### Unsetting the Path

The `PATH` variable can be unset using the `unset` command.

```bash
$ unset PATH
```

## Special Characters

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

## Command Line Editing

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
