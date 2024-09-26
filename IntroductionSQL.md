# SQL-Learning-Journey

# Relational Databases

A **relational database** is a system for storing data in tables, each with columns and rows. Here’s a simplified explanation:

1. **Tables**: Data is stored in tables, such as customers, products, employees, etc.
2. **Columns and Rows**: Each table has columns (which define the type of data) and rows (actual data entries or records).
3. **CRUD Operations**: You can Create, Read, Update, and Delete records in the tables.
4. **Relationships**: Tables can be linked to each other through relationships (e.g., an employee works in a specific office).
5. **SQL (Structured Query Language)**: SQL is used to manage and retrieve data from the database.
6. **Hosting**: Databases can be hosted locally (on your computer) or in the cloud for access from anywhere.

## Entity Relationship Diagrams (ERD)

An ERD is a visual diagram that shows how different tables in the database are connected. Tools like LucidChart can be used to create ERDs.

## Popular Relational Database Software

There are various relational database software options, both free and paid. Examples include:

- MySQL
- Postgres
- SQLite
- Microsoft SQL Server
- MariaDB
- Oracle
- IBM DB2

In this tutorial, the focus is on MySQL, which is free and open-source.

## SQL (Structured Query Language)

SQL is the language used to interact with relational databases. It’s much simpler compared to general programming languages like Python or Java. SQL commands fall into three main categories:

1. **Data Definition Language (DDL)**: Deals with defining or modifying the structure of tables (e.g., creating a table, altering its structure).
2. **Data Control Language (DCL)**: Manages user access. The two main commands are:

   - **GRANT**: Give users permission.
   - **REVOKE**: Remove users’ permission.

3. **Data Manipulation Language (DML)**: Used for day-to-day operations like inserting, updating, and deleting data.

## SQL Syntax Tips

- SQL is case insensitive (you can write in uppercase or lowercase).
- Commands must end with a semicolon (`;`).
- The syntax might vary slightly between different database software, so always check the documentation.

In short, relational databases store data in organized tables and use SQL to manage and access that data.

## MySql Command

- `show databases;`-Shows databases

  - The following are default databases...

  ```sql
     Database           |
  +--------------------+
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys
  ```

- `create database <db name>`
- `create database if not exists classicmodels;`:

  ```sql
  mysql> create database classicmodels;
  mysql> show databases;
  +--------------------+
  | Database           |
  +--------------------+
  | classicmodels      |
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys                |
  +--------------------+
  5 rows in set (0.00 sec)
  mysql> create database classicmodels;
  ERROR 1007 (HY000): Cant create database 'classicmodels'; database exists
  mysql> create database if not exists classicmodels;
  Query OK, 1 row affected, 1 warning (0.01 sec)
  ```

- `use <dbname>` : After logging in ,we need to move into the database where we gonna build table
  ```sql
  mysql> use classicmodels
   Database changed
  ```
- `drop database <dbname>;`:Delete database permanently.
  ```sql
  mysql> drop database classicmodels;
   Query OK, 0 rows affected (0.05 sec)
  ```
  `create table <table_name>(col1 datatype constraints)`:
  ```sql
     CREATE TABLE `offices` (
    ->   `officeCode` varchar(10) NOT NULL,
    ->   `city` varchar(50) NOT NULL,
    ->   `phone` varchar(50) NOT NULL,
    ->   `addressLine1` varchar(50) NOT NULL,
    ->   `addressLine2` varchar(50),
    ->   `state` varchar(50),
    ->   `country` varchar(50) NOT NULL,
    ->   `postalCode` varchar(15) NOT NULL,
    ->   `territory` varchar(10) NOT NULL,
    ->   PRIMARY KEY (`officeCode`)
    -> );
  ```
  `describe offices;`:
  ```sql
    mysql> describe offices;
    +--------------+-------------+------+-----+---------+-------+
    | Field        | Type        | Null | Key | Default | Extra |
    +--------------+-------------+------+-----+---------+-------+
    | officeCode   | varchar(10) | NO   | PRI | NULL    |       |
    | city         | varchar(50) | NO   |     | NULL    |       |
    | phone        | varchar(50) | NO   |     | NULL    |       |
    | addressLine1 | varchar(50) | NO   |     | NULL    |       |
    | addressLine2 | varchar(50) | YES  |     | NULL    |       |
    | state        | varchar(50) | YES  |     | NULL    |       |
    | country      | varchar(50) | NO   |     | NULL    |       |
    | postalCode   | varchar(15) | NO   |     | NULL    |       |
    | territory    | varchar(10) | NO   |     | NULL    |       |
    +--------------+-------------+------+-----+---------+-------+
    9 rows in set (0.01 sec)
  ```

## SQL DATATYPE:

- Numeric
  - bit,tinyint,smallint,int,bigint,decimal,numeric.float,real
- Date/Time
  - Date,Time,Datetime,Timestamps,Year
- Character/String
  - Char,Varchar,Varchar(max),Text
- Unicode Character/String
  - NChar,NVarchar,NVarchar(max),NText
- Binary
  - Binary,Varbinary,Varbinary(max),image
- Misc.
  - Cob,Blob,XML,JSON
