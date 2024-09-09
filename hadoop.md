A comprehensive guide to the basic Hadoop commands, including file creation, permissions management (chmod), and more:

### 1. **HDFS (Hadoop Distributed File System) Basic Commands**

#### **Listing Directories & Files**

- **`hadoop fs -ls /`**
  - Lists all files and directories in the root of the HDFS.
  
- **`hadoop fs -ls /path/to/directory`**
  - Lists the files in the specified directory in HDFS.

- **`hadoop fs -ls -R /path/to/directory`**
  - Recursively lists all files and directories in the specified path.

#### **Creating Directories**

- **`hadoop fs -mkdir /path/to/directory`**
  - Creates a new directory in HDFS.

- **`hadoop fs -mkdir -p /path/to/parentDir/childDir`**
  - Creates parent directories if they don’t exist.

#### **Creating and Uploading Files**

- **`hadoop fs -put /local/path/file.txt /hdfs/path/`**
  - Uploads a local file from the local filesystem to HDFS.

- **`hadoop fs -copyFromLocal /local/path/file.txt /hdfs/path/`**
  - Copies a file from the local filesystem to HDFS.

- **`hadoop fs -touchz /hdfs/path/newfile.txt`**
  - Creates an empty file in HDFS.

#### **Viewing Files**

- **`hadoop fs -cat /hdfs/path/file.txt`**
  - Displays the content of a file in HDFS.

- **`hadoop fs -tail /hdfs/path/file.txt`**
  - Displays the last 1KB of a file (useful for log files).

- **`hadoop fs -text /hdfs/path/file.txt`**
  - Displays the file content in a human-readable format (supports compressed files).

#### **Downloading Files from HDFS**

- **`hadoop fs -get /hdfs/path/file.txt /local/directory/`**
  - Downloads a file from HDFS to the local filesystem.

- **`hadoop fs -copyToLocal /hdfs/path/file.txt /local/directory/`**
  - Copies a file from HDFS to the local filesystem.

#### **Moving and Renaming Files**

- **`hadoop fs -mv /hdfs/path/source /hdfs/path/destination`**
  - Moves or renames a file or directory within HDFS.

#### **Deleting Files and Directories**

- **`hadoop fs -rm /hdfs/path/file.txt`**
  - Deletes a file from HDFS.

- **`hadoop fs -rm -r /hdfs/path/directory`**
  - Recursively deletes a directory and its contents from HDFS.

- **`hadoop fs -rmdir /hdfs/path/emptyDir`**
  - Deletes an empty directory.

- **`hadoop fs -expunge`**
  - Permanently deletes files from the HDFS trash.

#### **Checking Disk Usage**

- **`hadoop fs -du /hdfs/path/`**
  - Displays disk usage for the specified directory in HDFS.

- **`hadoop fs -df -h`**
  - Displays free space on HDFS in a human-readable format.

---

### 2. **File and Directory Permissions**

#### **Changing Ownership**

- **`hadoop fs -chown user:group /hdfs/path/file.txt`**
  - Changes the owner and group of a file or directory.

- **`hadoop fs -chown -R user:group /hdfs/path/dir/`**
  - Recursively changes the owner and group of all files and directories.

#### **Changing File Permissions (chmod)**

- **`hadoop fs -chmod 755 /hdfs/path/file.txt`**
  - Changes the permissions of a file or directory (`755` means full permissions for the owner, and read+execute for others).

- **`hadoop fs -chmod -R 777 /hdfs/path/dir/`**
  - Recursively changes the permissions of all files and directories under the specified path (`777` means full permissions for everyone).

#### **Viewing Permissions**

- **`hadoop fs -ls /hdfs/path/`**
  - Shows file listing along with permissions, ownership, and file size.

---

### 3. **Advanced HDFS Commands**

#### **File Merging**

- **`hadoop fs -getmerge /hdfs/directory/ /local/directory/outputFile.txt`**
  - Merges all files in a directory into one and downloads it to the local filesystem.

#### **File Count**

- **`hadoop fs -count /hdfs/path/`**
  - Displays the number of files, directories, and bytes in a directory.

#### **File Status**

- **`hadoop fs -stat /hdfs/path/file.txt`**
  - Displays metadata such as size, modification date, and replication factor of a file.

#### **File Block Locations**

- **`hadoop fsck /hdfs/path/file.txt`**
  - Runs a file system check and displays block locations, replication, and more for a file.

---

### 4. **YARN (Yet Another Resource Negotiator) Basic Commands**

#### **Listing YARN Applications**

- **`yarn application -list`**
  - Lists all currently running YARN applications.

- **`yarn application -status <application_id>`**
  - Shows the status of a specific YARN application.

#### **Killing YARN Applications**

- **`yarn application -kill <application_id>`**
  - Terminates a YARN application by its ID.

#### **Node Management**

- **`yarn node -list`**
  - Lists all YARN nodes in the cluster.

#### **Logs**

- **`yarn logs -applicationId <application_id>`**
  - Retrieves logs for a specific YARN application.

---

### 5. **Hadoop Administrative Commands**

#### **Format NameNode**

- **`hadoop namenode -format`**
  - Formats the NameNode (only use this before starting the Hadoop cluster for the first time or when reformatting is necessary).

#### **Report HDFS Health**

- **`hadoop dfsadmin -report`**
  - Provides a detailed report on the HDFS filesystem, including available disk space, the number of DataNodes, and their health.

#### **Safemode Management**

- **`hadoop dfsadmin -safemode get`**
  - Checks if HDFS is in safemode (read-only mode during maintenance).

- **`hadoop dfsadmin -safemode leave`**
  - Exits HDFS safemode, allowing write operations.

#### **Decommissioning a DataNode**

- **`hadoop dfsadmin -decommission <datanode>`**
  - Decommissions a DataNode by safely removing it from the cluster.

#### **Rebalancing the Cluster**

- **`hadoop balancer`**
  - Rebalances the data blocks across all DataNodes to maintain uniform distribution.

---

### 6. **MapReduce Commands**

#### **Running a MapReduce Job**

- **`hadoop jar /path/to/jarfile.jar MainClass /input /output`**
  - Runs a MapReduce job using the specified `.jar` file, main class, and input/output paths.

#### **Job Status**

- **`hadoop job -status <job_id>`**
  - Displays the status of a running MapReduce job.

#### **Killing a Job**

- **`hadoop job -kill <job_id>`**
  - Terminates a running MapReduce job.

#### **Listing All Jobs**

- **`hadoop job -list`**
  - Lists all currently running MapReduce jobs.

---

### 7. **Miscellaneous Hadoop Commands**

#### **Hadoop Version**

- **`hadoop version`**
  - Displays the installed Hadoop version.

#### **Hadoop Classpath**

- **`hadoop classpath`**
  - Shows the classpath needed to run Hadoop.

#### **Hadoop Help**

- **`hadoop fs -help`**
  - Displays help for Hadoop filesystem commands.

This covers a wide range of Hadoop operations, from file handling to administrative tasks like permissions management and MapReduce job control, helping users to interact effectively with the Hadoop ecosystem.
