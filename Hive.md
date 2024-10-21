Here’s a detailed guide to **Hive commands in Cloudera**, along with explanations of **why** and **when** they are used.

---

### **1. Hive Shell Command**

- **Start Hive Shell**:
   ```bash
   hive
   ```
   **Why**: This command starts the **Hive shell**. It’s the main interface where you can run Hive queries and commands. After starting the shell, you can interact with Hive databases and tables.

---

### **2. Database Operations**

- **Show Databases**:
   ```sql
   SHOW DATABASES;
   ```
   **Why**: Use this to list all the available databases in Hive. It's useful to see the databases before selecting one to work with.

- **Create Database**:
   ```sql
   CREATE DATABASE database_name;
   ```
   **Why**: This creates a new database in Hive. Databases help organize and manage tables related to a specific project or data domain.

- **Use a Database**:
   ```sql
   USE database_name;
   ```
   **Why**: After creating or choosing a database, this command allows you to switch the active database context. All subsequent operations will be performed in this database.

- **Drop a Database**:
   ```sql
   DROP DATABASE database_name [CASCADE];
   ```
   **Why**: This deletes a database. If you use the `CASCADE` option, it will also remove all tables within the database.

- **Describe Database**:
   ```sql
   DESCRIBE DATABASE database_name;
   ```
   **Why**: Use this command to get detailed information about a specific database, such as its location in HDFS.

---

### **3. Table Operations**

- **Show Tables**:
   ```sql
   SHOW TABLES;
   ```
   **Why**: This command lists all the tables in the current database. It helps you know which tables are available to query or modify.

- **Create Table**:
   ```sql
   CREATE TABLE table_name (column1 datatype, column2 datatype, ...);
   ```
   **Why**: This creates a new table with specified columns and datatypes. Tables are used to store data in structured format.

- **Create External Table**:
   ```sql
   CREATE EXTERNAL TABLE table_name (column1 datatype, column2 datatype, ...)
   LOCATION 'hdfs_path';
   ```
   **Why**: External tables allow Hive to read data that is stored outside Hive’s warehouse directory (in HDFS). The `EXTERNAL` keyword tells Hive not to delete the data when the table is dropped.

- **Create Table Like Another Table**:
   ```sql
   CREATE TABLE new_table_name LIKE existing_table_name;
   ```
   **Why**: This creates a new table with the same structure as an existing table, without copying the data.

- **Describe Table**:
   ```sql
   DESCRIBE table_name;
   ```
   **Why**: This command provides information about the structure of a table, including column names, types, and other metadata.

- **Drop Table**:
   ```sql
   DROP TABLE table_name;
   ```
   **Why**: This deletes a table from the database, freeing up space and removing it from Hive.

- **Alter Table**:
   - **Rename Table**:
     ```sql
     ALTER TABLE old_table_name RENAME TO new_table_name;
     ```
     **Why**: This renames a table without losing data or structure.

   - **Add Columns**:
     ```sql
     ALTER TABLE table_name ADD COLUMNS (column_name datatype);
     ```
     **Why**: Use this to add new columns to an existing table when your data model changes or new data is collected.

   - **Change Column**:
     ```sql
     ALTER TABLE table_name CHANGE column_name new_column_name datatype;
     ```
     **Why**: This modifies the name or datatype of an existing column.

---

### **4. Data Loading and Insertion**

- **Load Data into Table**:
   ```sql
   LOAD DATA INPATH 'hdfs_path' INTO TABLE table_name;
   ```
   **Why**: This loads data from a specified HDFS location into a Hive table. It’s typically used to bring external data (e.g., CSV, JSON) into Hive for querying.

- **Insert Data into Table**:
   ```sql
   INSERT INTO TABLE table_name VALUES (value1, value2, ...);
   ```
   **Why**: This inserts a row of data into a table. It's used for adding new records one at a time, but generally more efficient methods exist for large datasets.

- **Insert Data from Another Table**:
   ```sql
   INSERT INTO TABLE target_table_name 
   SELECT * FROM source_table_name WHERE condition;
   ```
   **Why**: This command inserts data into a target table by selecting it from another table. It’s useful for transforming or filtering data during insertion.

- **Insert Overwrite Table**:
   ```sql
   INSERT OVERWRITE TABLE table_name 
   SELECT * FROM another_table WHERE condition;
   ```
   **Why**: This replaces the existing data in a table with new data from a `SELECT` query. It’s often used when you want to refresh the contents of a table.

- **Insert into Partitioned Table**:
   ```sql
   INSERT INTO TABLE partitioned_table PARTITION (partition_column=value)
   VALUES (value1, value2, ...);
   ```
   **Why**: This inserts data into a specific partition of a table. It’s useful for large datasets divided by a partitioning key like date or location.

---

### **5. Partitioning**

- **Create Partitioned Table**:
   ```sql
   CREATE TABLE table_name (column1 datatype, column2 datatype, ...)
   PARTITIONED BY (partition_column datatype);
   ```
   **Why**: Partitioning helps organize large datasets by splitting them based on certain columns, which improves query performance by scanning only relevant partitions.

- **Add Partition to Table**:
   ```sql
   ALTER TABLE table_name ADD PARTITION (partition_column=value);
   ```
   **Why**: This adds a new partition to an existing partitioned table, allowing you to insert new data under a specific partition.

- **Drop Partition**:
   ```sql
   ALTER TABLE table_name DROP PARTITION (partition_column=value);
   ```
   **Why**: Use this to delete a specific partition and its data from the table.

- **Show Partitions**:
   ```sql
   SHOW PARTITIONS table_name;
   ```
   **Why**: This lists all partitions of a table. It helps you understand how data is organized.

---

### **6. Bucketing**

- **Create Bucketed Table**:
   ```sql
   CREATE TABLE table_name (column1 datatype, column2 datatype, ...)
   CLUSTERED BY (column_name) INTO num_buckets BUCKETS;
   ```
   **Why**: Bucketing divides data into multiple buckets based on the value of a hash function on the specified columns. It helps with distributed processing and joins optimization.

---

### **7. Views**

- **Create View**:
   ```sql
   CREATE VIEW view_name AS SELECT * FROM table_name;
   ```
   **Why**: Views provide a saved query result that can be referenced like a table. They’re useful for simplifying complex queries.

- **Drop View**:
   ```sql
   DROP VIEW view_name;
   ```
   **Why**: This deletes a view when it’s no longer needed.

---

### **8. Indexing**

- **Create Index**:
   ```sql
   CREATE INDEX index_name ON TABLE table_name(column_name)
   AS 'index_type';
   ```
   **Why**: Indexes improve query performance by speeding up search operations on large tables, especially when filtering on specific columns.

- **Drop Index**:
   ```sql
   DROP INDEX index_name ON table_name;
   ```
   **Why**: Use this to delete an index when it’s no longer needed or if the index is no longer useful for query optimization.

---

### **9. Joins**

- **Inner Join**:
   ```sql
   SELECT a.*, b.* 
   FROM table1 a 
   JOIN table2 b ON a.column = b.column;
   ```
   **Why**: Inner joins return only the matching rows from both tables. It's the most common type of join for combining related data.

- **Left Outer Join**:
   ```sql
   SELECT a.*, b.*
   FROM table1 a
   LEFT OUTER JOIN table2 b ON a.column = b.column;
   ```
   **Why**: Left joins return all rows from the left table and the matched rows from the right table (null if there’s no match). It's useful when you want to retain all rows from the first table.

- **Right Outer Join**:
   ```sql
   SELECT a.*, b.*
   FROM table1 a
   RIGHT OUTER JOIN table2 b ON a.column = b.column;
   ```
   **Why**: Right joins return all rows from the right table and the matched rows from the left table (null if there’s no match).

- **Full Outer Join**:
   ```sql
   SELECT a.*, b.*
   FROM table1 a
   FULL OUTER JOIN table2 b ON a.column = b.column;
   ```
   **Why**: This join returns all rows when there is a match in either table. It’s used when you want all data from both tables, even if there are no matches.

---

### **10. Union**

- **Union All**:
   ```sql
   SELECT * FROM table1
   UNION ALL
   SELECT * FROM table2;
   ```
   **Why**: Union combines the results of two queries into a single result set. `UNION ALL` does not remove duplicates, which
