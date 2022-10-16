## Users

### Commands Used

| Command   | Description                                |
| --------- | ------------------------------------------ |
| `whoami`  | Displays the current user                  |
| `id`      | Displays the current user id and groups id |
| `su`      | Switch user                                |
| `sudo`    | Run a command as another user              |
| `chown`   | Change the owner of a file                 |
| `chgrp`   | Change the group of a file                 |
| `useradd` | Add a new user                             |
| `userdel` | Delete a user                              |
| `passwd`  | Change a user password                     |

### User Shell

Each user has a shell associated with it, The default shell is `/bin/bash`.

### Types of Shell Users

There are three types of users:

- **System Users**: A system user is a user who has no home directory and cannot log in. They are used for system services, such as the `mysql` user.
- **Normal Users**: A normal user is a user who has a home directory and can log in. They are used for normal users, such as the `joe` user.
- **System Administrators**: A system administrator is a user who has a home directory and can log in. They are used for system administrators, such as the `root` user.

### List All Users

The following command lists all users, in the output all users that admit login will end with `*sh`:

```bash
$ cat /etc/passwd # List all users
$ cat /etc/passwd | grep "sh$" # List all users that admit login
$ cat /etc/passwd | grep "sh$" | awk '{print $1}' FS=":" #  List all users names that admit login
$ cut -d: -f1 /etc/passwd # List all users names
```

### Add a User

The following command adds a user:

```bash
$ mkdir /home/<user-dir> # Create the home directory
$ useradd -c "user comment" <username> # Add the user
$ useradd -d /home/<user-dir> <username> # Add a specific home directory
$ useradd -g /home/<user-dir> <username> # Add the primary group of the user
$ useradd -G <group1>,<group2> <username> # Add the user to groups multiple groups
$ chown root:<root-username> <username> # Set the root of the user
$ passwd <username> # Set the password
$ su <username> # Switch to the user
```

NOTE 1: The `useradd` command will create a home directory, a suer group and a user id for the user.
NOTE 2: The `useradd` use the `/etc/default/useradd`, `/etc/login/defs` file to set the default values, see this values with `cat /etc/login.defs | grep 'PASS\|UID\|GID'` or `useradd -D`.

### Delete a User

The following command deletes a user:

```bash
$ userdel -r <username> # Delete the user and the home directory
```

### Change a User Password

The following command changes a user password:

```bash
$ passwd <username> # Change the password
```

### Update a User

The command `useradd` can be used to update a user, with the following options:

| flag | Description                 |
| ---- | --------------------------- |
| `-l` | Change the user name        |
| `-d` | Change the home directory   |
| `-m` | Move the home directory     |
| `-g` | Change the primary group    |
| `-G` | Change the secondary groups |
| `-c` | Change the user comment     |
| `-s` | Change the user shell       |

## Files and Permissions

### Type of permissions

There are three types of permissions, which can be applied to files and directories:

- **write**: can modify the file
- **read**: can read the file
- **execute**: can run the file

### Permissions entities

There are three entities that can be granted permissions:

- **owner**: the user who created the file
- **group**: the group of users who own the file
- **others**: all other users

### Understanding permissions

- `ls -la` shows all hidden and non-hidden files and directories, including permissions.

```bash
$ ls -la
total 52
drwxr-xr-x 12 dev dev 4096 Oct  6 14:54 .
drwxr-xr-x 24 dev dev 4096 Oct  5 18:48 ..
drwxr-xr-x  8 dev dev 4096 Oct  5 23:49 .git
-rw-r--r--  1 dev dev 2228 Oct  5 23:48 README.md
drwxr-xr-x  2 dev dev 4096 Oct  5 02:45 architecture-overview
drwxr-xr-x  2 dev dev 4096 Oct  5 02:45 change-password
drwxr-xr-x  2 dev dev 4096 Oct  5 02:45 commands
drwxr-xr-x  2 dev dev 4096 Oct  5 02:45 editors
drwxr-xr-x  2 dev dev 4096 Oct  5 02:45 env-shell-variables
drwxr-xr-x  2 dev dev 4096 Oct  6 14:56 file-permissions
drwxr-xr-x  2 dev dev 4096 Oct  5 23:20 input-output-error
drwxr-xr-x  2 dev dev 4096 Oct  4 03:43 media
```

Each column represents a information type of the file, like the following example:

| Permissions | number of linked hard links | owner | group | size | date & time | file/directory        |
| ----------- | --------------------------- | ----- | ----- | ---- | ----------- | --------------------- |
| drwxr-xr-x  | 12                          | dev   | dev   | 4096 | Oct 6 14:54 | .                     |
| drwxr-xr-x  | 24                          | dev   | dev   | 4096 | Oct 5 18:48 | ..                    |
| drwxr-xr-x  | 8                           | dev   | dev   | 4096 | Oct 5 23:49 | .git                  |
| -rw-r--r--  | 1                           | dev   | dev   | 2228 | Oct 5 23:48 | README.md             |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 02:45 | architecture-overview |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 02:45 | change-password       |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 02:45 | commands              |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 02:45 | editors               |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 02:45 | env-shell-variables   |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 6 14:56 | file-permissions      |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 5 23:20 | input-output-error    |
| drwxr-xr-x  | 2                           | dev   | dev   | 4096 | Oct 4 03:43 | media                 |

### Anatomy of permissions

The permissions are represented by a string of 10 characters, which are divided into three groups of three characters each. The first character is a special character that represents the type of file, which can be:

- `-`: regular file
- `d`: directory
- `l`: symbolic link
- `b`: block device
- `c`: character device
- `s`: socket
- `p`: pipe

The next three characters represent the permissions for the owner, the next three for the group, and the last three for others.

### Character meaning

A permission bit is a character that can be either `r`, `w`, or `x`. The meaning of each character is:

- `r`: read bit
- `w`: write bit
- `x`: execute bit
- `s`: setuid bit (It's an executable file that runs with the permissions of the file's owner, rather than the user who runs it.)

### Changing permissions

The following command changes the permissions of a file:

```bash
$ chmod <permissions> <file> # Change the permissions of a file
```

#### Absolute permissions

The absolute permissions are represented by a three-digit number, where each digit represents the permissions for the owner, the group, and others, respectively.

| Number | Permissions Type  | Symbolic Representation |
| ------ | ----------------- | ----------------------- |
| 0      | No permissions    | ---                     |
| 1      | Execute           | --x                     |
| 2      | Write             | -w-                     |
| 3      | Write and Execute | -wx                     |
| 4      | Read              | r--                     |
| 5      | Read and Execute  | r-x                     |
| 6      | Read and Write    | rw-                     |
| 7      | All permissions   | rwx                     |

```bash
sudo chmod 777 file.txt # Change the permissions of a file to all permissions
sudo chmod 755 file.txt # owner: all, group: read and execute, others: read and execute
```

#### Symbolic permissions

The symbolic permissions are represented by a string of three characters, where each character represents the permissions for the owner, the group, and others, respectively.

| Symbol | Permissions Type | Symbolic Representation |
| ------ | ---------------- | ----------------------- |
| u      | User             | rwx                     |
| g      | Group            | rwx                     |
| o      | Others           | rwx                     |
| a      | All              | rwx                     |

```bash
sudo chmod ugo+rwx file.txt # Change the permissions of a file to all permissions
sudo chmod u+rwx,g+rwx,o+rwx file.txt # Change the permissions of a file to all permissions
```
