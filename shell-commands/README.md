# Linux Shell Commands

## File System Commands

| id | command | description | example |
| --- | --- | --- | --- |
| 1 | `ls` | list directory contents | `ls -l` |
| 2 | `cd` | change directory | `cd /home` |
| 3 | `pwd` | print working directory | `pwd` |
| 4 | `mkdir` | make directories | `mkdir -p /home/user1/dir1/dir2` |
| 5 | `rmdir` | remove empty directories | `rmdir /home/user1/dir1/dir2` |
| 6 | `cp` | copy files and directories | `cp -r /home/user1/dir1 /home/user2/dir1` |
| 7 | `mv` | move (rename) files | `mv /home/user1/dir1 /home/user2/dir1` |
| 8 | `rm` | remove files or directories | `rm -r /home/user1/dir1` |
| 9 | `ln` | create links between files | `ln -s /home/user1/dir1 /home/user2/dir1` |
| 10 | `touch` | change file timestamps | `touch /home/user1/dir1/file1` |
| 11 | `cat` | concatenate files and print on the standard output | `cat /home/user1/dir1/file1` |
| 12 | `more` | page through a file | `more /home/user1/dir1/file1` |
| 13 | `less` | page through a file | `less /home/user1/dir1/file1` |
| 14 | `head` | output the first part of files | `head -n 10 /home/user1/dir1/file1` |
| 15 | `tail` | output the last part of files | `tail -n 10 /home/user1/dir1/file1` |
| 16 | `wc` | print newline, word, and byte counts for each file | `wc -l /home/user1/dir1/file1` |
| 17 | `find` | search for files in a directory hierarchy | `find /home/user1/dir1 -name file1` |
| 18 | `locate` | search for files in a database | `locate file1` |
| 19 | `grep` | print lines matching a pattern | `grep -i "hello" /home/user1/dir1/file1` |
| 20 | `diff` | compare files line by line | `diff /home/user1/dir1/file1 /home/user2/dir1/file1` |
| 21 | `sort` | sort lines of text files | `sort /home/user1/dir1/file1` |
| 22 | `uniq` | report or omit repeated lines | `uniq /home/user1/dir1/file1` |
| 23 | `cut` | remove sections from each line of files | `cut -d: -f1 /etc/passwd` |
| 24 | `paste` | merge lines of files | `paste /home/user1/dir1/file1 /home/user2/dir1/file1` |
| 25 | `join` | join lines of two files on a common field | `join /home/user1/dir1/file1 /home/user2/dir1/file1` |
| 26 | `comm` | compare two sorted files line by line | `comm /home/user1/dir1/file1 /home/user2/dir1/file1` |
| 27 | `split` | split a file into pieces | `split -b 1M /home/user1/dir1/file1` |
| 28 | `md5sum` | compute and check MD5 message digest | `md5sum /home/user1/dir1/file1` |
| 29 | `tar` | create, extract, or list files from a tar archive | `tar -xf /home/user1/dir1/file1.tar` |
| 30 | `gzip` | compress or expand files | `gzip -d /home/user1/dir1/file1.gz` |
| 31 | `bzip2` | compress or expand files | `bzip2 -d /home/user1/dir1/file1.bz2` |
| 32 | `zip` | compress or expand files | `zip -d /home/user1/dir1/file1.zip` |
| 33 | `unzip` | list, test, or extract files from a ZIP archive | `unzip /home/user1/dir1/file1.zip` |


