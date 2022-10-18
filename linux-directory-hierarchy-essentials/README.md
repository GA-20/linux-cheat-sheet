## Linux Directory Hierarchy Essentials

```bash
├── /
    ├── bin/
    ├── dev/
    ├── etc/
    ├── usr/
        ├── bin/
        ├── man/
        ├── lib/
        ├── local/
        ├── sbin/
        ├── share/
    ├── home/
    ├── lib/
    ├── sbin/
    ├── tmp/
    ├── var/
        ├── log/
        ├── tmp/
    ├── root/
        ├── boot/
```

## Main Directories

- `/bin` - contains user binaries, executable files, Linux commands that are used in single user mode, and common commands that are used by all the users, like cat, cp, cd, ls, etc.
- `/dev` - contains device files, which are used to access hardware devices.
- `/etc` - contains system configuration files, like /etc/passwd, /etc/shadow, /etc/group, etc.
- `/home` - holds home directories of all users.
- `/lib` - contains libraries, which are used by the system and the binaries. There are two types of libraries, static and dynamic. Static libraries are used to link the binaries at compile time, and dynamic libraries are used to link the binaries at run time.
- `/proc` - contains information about the processes running on the system. Much of the `/proc` subdirectory structure on Linux is unique, but it is similar in many other Unix variants.
- `/run` - Contains runtime data, such as sockets, named pipes, IDs, etc. This is relatively recent addition to the Linux directory hierarchy.
- `/sys` - Similar to `/proc`, but contains information about the hardware devices and system interfaces.
- `/sbin` - System executables for the system management, so regular users usually don't have component to execute these files.
- `/tmp` - Temporary files, which are deleted on reboot.
- `/usr` - Contain a large directory hierarchy, including the bulk of the Linux system.
- `/var` - The variable subdirectory, where programs record information that can change over the course of time.
- `/root` - The home directory of the root user.

## Subdirectories of `/root`

- `/root/boot` - Contains the kernel and the boot loader files.
- `/root/media` - Contains mount points for removable media, such as USB drives, CD-ROMs, etc.
- `/root/opt` - This may contain additional third-party software.

## Subdirectories of `/usr`

- `/include` - Contains header files for the C and C++ programming languages.
- `/local` - Is where administrators can install their own software.
- `/man` - Contains manual pages for the commands.
- `/share` - Contain files that should work on other kinds of Unix machines. These are auxiliary data files that programs and libraries read as necessary.

## Kernel Location

The kernel is located in the `/boot` directory. The kernel is the most important file in the Linux system. It is the first file that is loaded into the memory when the system is booted. The kernel is responsible for loading the rest of the system into the memory and starting the system services.
