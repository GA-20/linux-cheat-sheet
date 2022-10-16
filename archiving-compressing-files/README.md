## Archiving and Compressing Files

**Compress:** The compressing files is a process of reducing the size of a file or a group of files.

**Archiving:** The archiving files is a process of combining multiple files into a single file.

### Gzip

**Gzip** It is a compression and archiving utility for Linux/UNIX. The gzip command in Linux can only be used to compress a single file.

```bash
 gzip [Options] [filenames]
```

| Option  | Description                                                       | Example                          |
| ------- | ----------------------------------------------------------------- | -------------------------------- |
| -f      | Force overwrite of output file if it already exists               | gzip -f file1.txt                |
| -k      | Keep the original file after compression                          | gzip -k file1.txt                |
| -c      | Compresses the file and writes the output to the standard output. | gzip -c file1.txt > file1.txt.gz |
| -d      | Decompresses the file.                                            | gzip -d file1.txt.gz             |
| -l      | Lists the compressed file.                                        | gzip -l file1.txt.gz             |
| -r      | Recursively compresses the files in the directory.                | gzip -r dir1                     |
| -t      | Tests the integrity of the compressed file.                       | gzip -t file1.txt.gz             |
| -v      | Displays the progress of the compression.                         | gzip -v file1.txt.gz             |
| [-1,-9] | Compresses the file with maximum compression.                     | gzip -9 file1.txt.gz             |

### Tar

**Tar** It is a utility for Linux/UNIX that is used to create, extract, and manipulate archives. The tar command in Linux can be used to compress multiple files into a single file.

```bash
 tar [Options] [filenames]
```

| Option | Description                                                                  | Example          |
| ------ | ---------------------------------------------------------------------------- | ---------------- |
| -c     | Creates a new archive                                                        | tar -c file1.txt |
| -x     | Extracts the files from the archive                                          | tar -x file1.txt |
| -t     | Lists the contents of the archive                                            | tar -t file1.txt |
| -f     | Specifies the name of the archive file                                       | tar -f file1.txt |
| -v     | Displays the progress of the compression                                     | tar -v file1.txt |
| -z     | Compresses the archive using gzip                                            | tar -z file1.txt |
| -j     | Compresses the archive using bzip2                                           | tar -j file1.txt |
| -C     | Extracts the files to the specified directory                                | tar -C file1.txt |
| -r     | Appends the files to the end of the archive                                  | tar -r file1.txt |
| -u     | Appends the files that are newer than the corresponding files in the archive | tar -u file1.txt |
| -p     | Preserves the file permissions                                               | tar -p file1.txt |
| -A     | Appends the files to the end of the archive                                  | tar -A file1.txt |
| -d     | Creates a diff archive                                                       | tar -d file1.txt |
| -M     | Lists the contents of the archive                                            | tar -M file1.txt |
| -N     | Lists the contents of the archive                                            | tar -N file1.txt |
| -T     | Lists the contents of the archive                                            | tar -T file1.txt |
| -X     | Lists the contents of the archive                                            | tar -X file1.txt |
| -Z     | Compresses the archive using compress                                        | tar -Z file1.txt |
| -w     | Verifies the archive                                                         | tar -w file1.txt |

**Basic Tutorial**

```bash
  tar -cvf archive.tar file1.txt file2.txt # Create a new archive
  tar -xvf archive.tar # Extract the files from the archive
  tar -tvf archive.tar # List the contents of the archive
  tar -cvzf archive.tar.gz file1.txt file2.txt # Create a new archive and compress it using gzip
  tar -xvzf archive.tar.gz # Extract the files from the archive and decompress it using gzip
  tar -cvjf archive.tar.bz2 file1.txt file2.txt # Create a new archive and compress it using bzip2
```

### tar.gz

**tar.gz** It is a combination of tar and gzip. It is used to compress multiple files into a single file and compress it using gzip.

```bash
 tar -cvzf archive.tar.gz file1.txt file2.txt # Create a new archive and compress it using gzip
 tar -xvzf archive.tar.gz # Extract the files from the archive and decompress it using gzip
```
