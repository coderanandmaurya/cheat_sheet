List of the **most useful Hadoop HDFS Linux commands** along with their specifications:

| Sr. No. | Hadoop Commands          | Command Specification |
|---------|--------------------------|-----------------------|
| 1       | `hadoop fs` or `hdfs dfs` | Base command to interact with HDFS and perform various operations. |
| 2       | `hadoop fs -ls` or `hdfs dfs -ls` | Lists the contents of a directory in HDFS. |
| 3       | `hadoop fs -put` or `hdfs dfs -put` | Uploads files from the local file system to HDFS. |
| 4       | `hadoop fs -get` or `hdfs dfs -get` | Downloads files from HDFS to the local file system. |
| 5       | `hadoop fs -mkdir` or `hdfs dfs -mkdir` | Creates a directory in HDFS. |
| 6       | `hadoop fs -rm` or `hdfs dfs -rm` | Removes a file from HDFS. |
| 7       | `hadoop fs -rmdir` or `hdfs dfs -rmdir` | Removes a directory from HDFS. |
| 8       | `hadoop fs -mv` or `hdfs dfs -mv` | Moves a file or directory within HDFS. |
| 9       | `hadoop fs -cp` or `hdfs dfs -cp` | Copies files or directories within HDFS. |
| 10      | `hadoop fs -cat` or `hdfs dfs -cat` | Displays the content of a file in the console. |
| 11      | `hadoop fs -tail` or `hdfs dfs -tail` | Displays the last kilobyte of a file in the console. |
| 12      | `hadoop fs -du` or `hdfs dfs -du` | Shows the space used by files and directories in HDFS. |
| 13      | `hadoop fs -chown` or `hdfs dfs -chown` | Changes ownership of files or directories in HDFS. |
| 14      | `hadoop fs -chmod` or `hdfs dfs -chmod` | Changes the permissions of files or directories in HDFS. |
| 15      | `hadoop fs -chgrp` or `hdfs dfs -chgrp` | Changes the group ownership of files or directories in HDFS. |
| 16      | `hadoop fs -setrep` or `hdfs dfs -setrep` | Sets the replication factor for a file in HDFS. |
| 17      | `hadoop fs -getmerge` or `hdfs dfs -getmerge` | Concatenates files in HDFS to a local file. |
| 18      | `hadoop fs -touchz` or `hdfs dfs -touchz` | Creates an empty file in HDFS. |
| 19      | `hadoop fs -getfacl` or `hdfs dfs -getfacl` | Retrieves Access Control Lists (ACLs) for files and directories. |
| 20      | `hadoop fs -setfacl` or `hdfs dfs -setfacl` | Sets Access Control Lists (ACLs) for files and directories in HDFS. |
| 21      | `hadoop fs -getfattr` or `hdfs dfs -getfattr` | Retrieves extended attributes for files and directories in HDFS. |
| 22      | `hadoop fs -setfattr` or `hdfs dfs -setfattr` | Sets extended attributes for files and directories in HDFS. |
| 23      | `hadoop fs -count` or `hdfs dfs -count` | Counts directories, files, and bytes under specified paths in HDFS. |
| 24      | `hadoop fs -test` or `hdfs dfs -test` | Tests existence or permissions of a file in HDFS. |
| 25      | `hadoop fs -expunge` or `hdfs dfs -expunge` | Permanently deletes files from HDFS by emptying the trash. |
| 26      | `hadoop fs -df` or `hdfs dfs -df` | Displays free and used space in HDFS. |
| 27      | `hadoop fs -getchecksum` or `hdfs dfs -getchecksum` | Retrieves the checksum of a file in HDFS. |
| 28      | `hadoop fs -stat` or `hdfs dfs -stat` | Displays details of a file or directory, like owner, permissions, size, etc. |
| 29      | `hadoop fs -copyFromLocal` or `hdfs dfs -copyFromLocal` | Copies files from the local file system to HDFS, similar to `-put`. |
| 30      | `hadoop fs -copyToLocal` or `hdfs dfs -copyToLocal` | Copies files from HDFS to the local file system, similar to `-get`. |

This table lists the most common and useful commands when working with HDFS using Hadoop in Linux environments.

<hr>

More detailed explanation of some **Hadoop HDFS commands** along with their **additional options**:

### 1. `hadoop fs -ls` or `hdfs dfs -ls`
Lists the contents of a directory in HDFS.

- **`-ls`**: Lists files and directories.
- **`-ls -R`**: Recursively lists all files in the directory and its subdirectories.
- **`-ls -d`**: Lists only directories instead of their contents.

**Example**:
```bash
hadoop fs -ls /user/hadoop/ # Lists all files and directories in /user/hadoop
hadoop fs -ls -R /user/hadoop/ # Recursively lists files in all subdirectories
```

### 2. `hadoop fs -put` or `hdfs dfs -put`
Uploads files from the local file system to HDFS.

- **`-f`**: Forces the overwrite of an existing file.
- **`-p`**: Preserves the attributes (permissions, ownership, etc.) of the source file.

**Example**:
```bash
hadoop fs -put -f localfile.txt /user/hadoop/ # Forcefully uploads file, overwriting existing one
```

### 3. `hadoop fs -get` or `hdfs dfs -get`
Downloads files from HDFS to the local file system.

- **`-ignorecrc`**: Ignores checksum errors during the copy.
- **`-f`**: Forcefully overwrites the file in the local file system if it exists.

**Example**:
```bash
hadoop fs -get -f /user/hadoop/hdfsfile.txt /local/path/ # Downloads and overwrites if necessary
```

### 4. `hadoop fs -mkdir` or `hdfs dfs -mkdir`
Creates a directory in HDFS.

- **`-p`**: Creates parent directories if they do not exist.

**Example**:
```bash
hadoop fs -mkdir -p /user/hadoop/newdir/subdir # Creates newdir and subdir if not present
```

### 5. `hadoop fs -rm` or `hdfs dfs -rm`
Removes a file from HDFS.

- **`-r`**: Removes directories recursively.
- **`-skipTrash`**: Permanently deletes files without moving them to the trash.

**Example**:
```bash
hadoop fs -rm -r /user/hadoop/dir # Recursively deletes the directory
hadoop fs -rm -skipTrash /user/hadoop/file.txt # Permanently deletes the file
```

### 6. `hadoop fs -mv` or `hdfs dfs -mv`
Moves files or directories within HDFS.

- **Note**: The `-mv` command does not have many specific options but will move a file from one directory to another. It will overwrite files with the same name in the destination directory.

**Example**:
```bash
hadoop fs -mv /user/hadoop/file1.txt /user/hadoop/archive/ # Moves file1 to archive
```

### 7. `hadoop fs -cp` or `hdfs dfs -cp`
Copies files or directories within HDFS.

- **`-p`**: Preserves file attributes (permissions, modification time, replication, etc.).

**Example**:
```bash
hadoop fs -cp -p /user/hadoop/file1.txt /user/hadoop/archive/ # Copies file and preserves attributes
```

### 8. `hadoop fs -cat` or `hdfs dfs -cat`
Displays the content of a file in the console.

- **Note**: This command has no additional options, but it works for viewing small files in HDFS.

**Example**:
```bash
hadoop fs -cat /user/hadoop/file1.txt # Outputs the content of the file
```

### 9. `hadoop fs -du` or `hdfs dfs -du`
Displays disk usage for files and directories in HDFS.

- **`-s`**: Displays the summary of disk usage.
- **`-h`**: Shows disk usage in human-readable format (MB, GB, etc.).

**Example**:
```bash
hadoop fs -du -h /user/hadoop/ # Shows the size of files and directories in human-readable format
hadoop fs -du -s /user/hadoop/dir # Shows the total size of the directory
```

### 10. `hadoop fs -chown` or `hdfs dfs -chown`
Changes ownership of files and directories in HDFS.

- **Note**: You can change both the user and the group ownership, or only one of them.

**Example**:
```bash
hadoop fs -chown newowner:newgroup /user/hadoop/file.txt # Changes both owner and group
hadoop fs -chown newowner /user/hadoop/file.txt # Changes only owner
```

### 11. `hadoop fs -chmod` or `hdfs dfs -chmod`
Changes file permissions in HDFS.

- **`-R`**: Recursively changes permissions for files in a directory.

**Example**:
```bash
hadoop fs -chmod 755 /user/hadoop/file.txt # Changes permissions to rwxr-xr-x
hadoop fs -chmod -R 755 /user/hadoop/dir/ # Recursively changes permissions for all files in a directory
```

### 12. `hadoop fs -getmerge` or `hdfs dfs -getmerge`
Concatenates files in HDFS to a local file.

- **Note**: This command is useful for combining smaller files into one large file on your local system.

**Example**:
```bash
hadoop fs -getmerge /user/hadoop/dir/ localfile.txt # Merges all files in dir into localfile.txt
```

### 13. `hadoop fs -touchz` or `hdfs dfs -touchz`
Creates an empty file in HDFS.

- **Note**: The file will have a size of 0 bytes.

**Example**:
```bash
hadoop fs -touchz /user/hadoop/emptyfile.txt # Creates an empty file
```

### 14. `hadoop fs -test` or `hdfs dfs -test`
Tests the existence of files and directories in HDFS or verifies permissions.

- **`-e`**: Tests if a path exists.
- **`-z`**: Tests if the file is empty.
- **`-d`**: Tests if the path is a directory.
- **`-f`**: Tests if the path is a file.

**Example**:
```bash
hadoop fs -test -e /user/hadoop/file.txt # Tests if the file exists
hadoop fs -test -z /user/hadoop/file.txt # Tests if the file is empty
```

### 15. `hadoop fs -df` or `hdfs dfs -df`
Displays the amount of free and used space in HDFS.

- **`-h`**: Shows the space usage in a human-readable format (MB, GB, etc.).

**Example**:
```bash
hadoop fs -df -h / # Displays the HDFS space usage in a human-readable format
```

### 16. `hadoop fs -setrep` or `hdfs dfs -setrep`
Sets the replication factor of a file in HDFS.

- **`-w`**: Waits for the replication to be completed before returning.

**Example**:
```bash
hadoop fs -setrep 3 /user/hadoop/file.txt # Sets the replication factor to 3
```

### 17. `hadoop fs -stat` or `hdfs dfs -stat`
Displays file or directory statistics.

- **`%b`**: Prints the number of blocks in the file.
- **`%F`**: Prints the file type.
- **`%o`**: Prints the file owner.
- **`%g`**: Prints the group name.
- **`%n`**: Prints the file name.

**Example**:
```bash
hadoop fs -stat "%n %o %g" /user/hadoop/file.txt # Outputs the file name, owner, and group
```

These commands with options make it easier to manage files, directories, and permissions within HDFS. By adding options, you can tailor commands to suit specific use cases, like handling recursion, permissions, and file preservation.

