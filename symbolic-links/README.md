## Symbolic Links

A symlink is a symbolic Linux/ UNIX link that points to another file or folder on your computer, or a connected file system. This is similar to a Windows shortcut.

### Symbolic Links

Soft links are similar to shortcuts, and can point to another file or directory in any file system.

### Hard Links

Hard links are also shortcuts for files and folders, but a hard link cannot be created for a folder or file in a different file system.

### Creating symbolic links

To create a symbolic link, use the `ln` command:

```bash
$ ln -s <target> <link-name> # Create a symbolic link
```

### Creating hard links

To create a hard link, use the `ln` command:

```bash
$ ln <target> <link-name> # Create a hard link
```

### Listing symbolic links

To list symbolic links, use the `ls` command:

```bash
$ ls -l # List symbolic links
lrwxrwxrwx 1 dev dev   18 Oct 16 14:40 personal -> Projects/personal/
```

### Removing symbolic links

To remove a symbolic link, use the `rm` command:

```bash
$ rm <link-name> # Remove a symbolic link
$ unlink <link-name> # Remove a symbolic link
```
