





# Overview

## What is SQL ? 
**SQL** is a database computer language designed for the retrieval and management of data in a relational database. **SQL** stands for **Structured Query Language**. This tutorial will give you a quick start to SQL. It covers most of the topics required for a basic understanding of SQL and to get a feel of how it works.

SQL is the standard language for Relational Database System. All the Relational Database Management Systems (RDBMS) like MySQL, MS Access, Oracle, Sybase, Informix, Postgres and SQL Server use SQL as their standard database language.

## What Can SQL do?

-   SQL can execute queries against a database
-   SQL can retrieve data from a database
-   SQL can insert records in a database
-   SQL can update records in a database
-   SQL can delete records from a database
-   SQL can create new databases
-   SQL can create new tables in a database
-   SQL can create stored procedures in a database
-   SQL can create views in a database
-   SQL can set permissions on tables, procedures, and views

# RDBMS Concepts

## What is RDBMS?

RDBMS stands for **R**elational **D**atabase **M**anagement **S**ystem. RDBMS is the basis for SQL, and for all modern database systems like MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

A Relational database management system (RDBMS) is a database management system (DBMS) that is based on the relational model as introduced by E. F. Codd.

## What is a table?

The data in an RDBMS is stored in database objects which are called as **tables**. This table is basically a collection of related data entries and it consists of numerous columns and rows.

Remember, a table is the most common and simplest form of data storage in a relational database. The following program is an example of a table 

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/1.PNG?raw=true)
## What is a field?

Every table is broken up into smaller entities called fields. The fields in the CUSTOMERS table consist of ID, NAME, AGE, ADDRESS and SALARY.

A field is a column in a table that is designed to maintain specific information about every record in the table.

## What is a Record or a Row?

A record is also called as a row of data is each individual entry that exists in a table. For example, there are 7 records in the above table. Following is a single row of data or record in the table

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/2.PNG?raw=true)
A record is a horizontal entity in a table.

## What is a column?

A column is a vertical entity in a table that contains all information associated with a specific field in a table.

For example, a column in the table is ADDRESS, which represents location description and would be as shown below

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/4.PNG?raw=true)
## What is a NULL value?

A NULL value in a table is a value in a field that appears to be blank, which means a field with a NULL value is a field with no value.

It is very important to understand that a NULL value is different than a zero value or a field that contains spaces. A field with a NULL value is the one that has been left blank during a record creation.

## SQL Constraints

Constraints are the rules enforced on data columns on a table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database.

Constraints can either be column level or table level. Column level constraints are applied only to one column whereas, table level constraints are applied to the entire table.

Following are some of the most commonly used constraints available in SQL.

-   NOT NULL Constraint − Ensures that a column cannot have a NULL value.
    
-   DEFAULT Constraint − Provides a default value for a column when none is specified.
    
-   UNIQUE Constraint − Ensures that all the values in a column are different.
    
-   PRIMARY Key − Uniquely identifies each row/record in a database table.
    
-   FOREIGN Key − Uniquely identifies a row/record in any another database table.

    
-   INDEX − Used to create and retrieve data from the database very quickly.

# SQL Constraints

## DEFAULT Constraint
The DEFAULT constraint provides a default value to a column when the INSERT INTO statement does not provide a specific value.

### Example

For example, the following SQL creates a new table called CUSTOMERS and adds five columns. Here, the SALARY column is set to 5000.00 by default, so in case the INSERT INTO statement does not provide a value for this column, then by default this column would be set to 5000.00.

    CREATE TABLE CUSTOMERS(
     ID   INT    NOT NULL, NAME VARCHAR (20) NOT NULL, 
     AGE  INT    NOT NULL, ADDRESS  CHAR (25)  ,
     SALARY      DECIMAL (18,  2) DEFAULT 5000.00,
     PRIMARY KEY (ID)  
    );


## UNIQUE Constraint

The UNIQUE Constraint prevents two records from having identical values in a column. In the CUSTOMERS table, for example, you might want to prevent two or more people from having an identical age.

### Example

For example, the following SQL query creates a new table called CUSTOMERS and adds five columns. Here, the AGE column is set to UNIQUE, so that you cannot have two records with the same age.

    CREATE TABLE CUSTOMERS( 
       ID   INT   NOT NULL, NAME VARCHAR (20) NOT NULL,
       AGE  INT   NOT NULL UNIQUE, ADDRESS  CHAR (25)  ,
       SALARY     DECIMAL (18,  2), PRIMARY KEY (ID)  
    );


## Primary Key
A primary key is a field in a table which uniquely identifies each row/record in a database table. Primary keys must contain unique values. A primary key column cannot have NULL values.

A table can have only one primary key, which may consist of single or multiple fields. When multiple fields are used as a primary key, they are called a composite key.

If a table has a primary key defined on any field(s), then you cannot have two records having the same value of that field(s).

**Note** − You would use these concepts while creating database tables.

### Create Primary Key

Here is the syntax to define the ID attribute as a primary key in a CUSTOMERS table.

    CREATE TABLE CUSTOMERS(
       ID   INT              NOT NULL,
       NAME VARCHAR (20)     NOT NULL,
       AGE  INT              NOT NULL,
       ADDRESS  CHAR (25) ,
       SALARY   DECIMAL (18, 2),       
       PRIMARY KEY (ID)
    );

## Foreign Key
A foreign key is a key used to link two tables together. This is sometimes also called as a referencing key.

A Foreign Key is a column or a combination of columns whose values match a Primary Key in a different table.

**The relationship between 2 tables matches the Primary Key in one of the tables with a Foreign Key in the second table.**


### Example

Consider the structure of the following two tables.

**CUSTOMERS table**

    CREATE TABLE CUSTOMERS( 
      ID   INT  NOT NULL, NAME VARCHAR (20) NOT NULL,
      AGE  INT  NOT NULL, ADDRESS  CHAR (25)  ,
      PRIMARY KEY (ID)  
    );

**ORDERS table**

    CREATE TABLE ORDERS ( 
      ID           INT        NOT NULL,
      DATE         DATETIME,
      CUSTOMER_ID  INT references CUSTOMERS(ID),
      AMOUNT       double,
      PRIMARY KEY  (ID)
     );

## NOT NULL Constraint
By default, a column can hold NULL values. If you do not want a column to have a NULL value, then you need to define such a constraint on this column specifying that NULL is now not allowed for that column.

A NULL is not the same as no data, rather, it represents unknown data.

## Example

For example, the following SQL query creates a new table called CUSTOMERS and adds five columns, three of which, are ID NAME and AGE, In this we specify not to accept NULLs.

    CREATE TABLE CUSTOMERS( 
      ID   INT              NOT NULL,
      NAME VARCHAR (20)     NOT NULL,
      AGE  INT              NOT NULL,
      ADDRESS               CHAR (25)  ,
      SALARY                DECIMAL (18,  2),
      PRIMARY KEY (ID)  
    );




# RDBMS Databases
There are many popular RDBMS available to work with. This tutorial gives a brief overview of some of the most popular RDBMS’s. This would help you to compare their basic features.

## MySQL

MySQL is an open source SQL database, which is developed by a Swedish company – MySQL AB. MySQL is pronounced as "my ess-que-ell," in contrast with SQL, pronounced "sequel."

MySQL is supporting many different platforms including Microsoft Windows, the major Linux distributions, UNIX, and Mac OS X.

MySQL has free and paid versions, depending on its usage (non-commercial/commercial) and features. MySQL comes with a very fast, multi-threaded, multi-user and robust SQL database server.

### History

-   Development of MySQL by Michael Widenius & David Axmark beginning in 1994.
    
-   First internal release on 23rd May 1995.
    
-   Windows Version was released on the 8th January 1998 for Windows 95 and NT.
    
-   Version 3.23: beta from June 2000, production release January 2001.
    
-   Version 4.0: beta from August 2002, production release March 2003 (unions).
    
-   Version 4.1: beta from June 2004, production release October 2004.
    
-   Version 5.0: beta from March 2005, production release October 2005.
    
-   Sun Microsystems acquired MySQL AB on the 26th February 2008.
    
-   Version 5.1: production release 27th November 2008.
    

### Features

-   High Performance.
-   High Availability.
-   Scalability and Flexibility Run anything.
-   Robust Transactional Support.
-   Web and Data Warehouse Strengths.
-   Strong Data Protection.
-   Comprehensive Application Development.
-   Management Ease.
-   Open Source Freedom and 24 x 7 Support.
-   Lowest Total Cost of Ownership.

## MS SQL Server

MS SQL Server is a Relational Database Management System developed by Microsoft Inc. Its primary query languages are −

-   T-SQL
-   ANSI SQL

### History

-   1987 - Sybase releases SQL Server for UNIX.
    
-   1988 - Microsoft, Sybase, and Aston-Tate port SQL Server to OS/2.
    
-   1989 - Microsoft, Sybase, and Aston-Tate release SQL Server 1.0 for OS/2.
    
-   1990 - SQL Server 1.1 is released with support for Windows 3.0 clients.
    
-   Aston - Tate drops out of SQL Server development.
    
-   2000 - Microsoft releases SQL Server 2000.
    
-   2001 - Microsoft releases XML for SQL Server Web Release 1 (download).
    
-   2002 - Microsoft releases SQLXML 2.0 (renamed from XML for SQL Server).
    
-   2002 - Microsoft releases SQLXML 3.0.
    
-   2005 - Microsoft releases SQL Server 2005 on November 7th, 2005.
    

### Features

-   High Performance
-   High Availability
-   Database mirroring
-   Database snapshots
-   CLR integration
-   Service Broker
-   DDL triggers
-   Ranking functions
-   Row version-based isolation levels
-   XML integration
-   TRY...CATCH
-   Database Mail

## ORACLE

It is a very large multi-user based database management system. Oracle is a relational database management system developed by 'Oracle Corporation'.

Oracle works to efficiently manage its resources, a database of information among the multiple clients requesting and sending data in the network.

It is an excellent database server choice for client/server computing. Oracle supports all major operating systems for both clients and servers, including MSDOS, NetWare, UnixWare, OS/2 and most UNIX flavors.

### History

Oracle began in 1977 and celebrating its 32 wonderful years in the industry (from 1977 to 2009).

-   1977 - Larry Ellison, Bob Miner and Ed Oates founded Software Development Laboratories to undertake development work.
    
-   1979 - Version 2.0 of Oracle was released and it became first commercial relational database and first SQL database. The company changed its name to Relational Software Inc. (RSI).
    
-   1981 - RSI started developing tools for Oracle.
    
-   1982 - RSI was renamed to Oracle Corporation.
    
-   1983 - Oracle released version 3.0, rewritten in C language and ran on multiple platforms.
    
-   1984 - Oracle version 4.0 was released. It contained features like concurrency control - multi-version read consistency, etc.
    
-   1985 - Oracle version 4.0 was released. It contained features like concurrency control - multi-version read consistency, etc.
    
-   2007 - Oracle released Oracle11g. The new version focused on better partitioning, easy migration, etc.
    

### Features

-   Concurrency
-   Read Consistency
-   Locking Mechanisms
-   Quiesce Database
-   Portability
-   Self-managing database
-   SQL*Plus
-   ASM
-   Scheduler
-   Resource Manager
-   Data Warehousing
-   Materialized views
-   Bitmap indexes
-   Table compression
-   Parallel Execution
-   Analytic SQL
-   Data mining
-   Partitioning

## MS ACCESS

This is one of the most popular Microsoft products. Microsoft Access is an entry-level database management software. MS Access database is not only inexpensive but also a powerful database for small-scale projects.

MS Access uses the Jet database engine, which utilizes a specific SQL language dialect (sometimes referred to as Jet SQL).

MS Access comes with the professional edition of MS Office package. MS Access has easyto-use intuitive graphical interface.

-   1992 - Access version 1.0 was released.
    
-   1993 - Access 1.1 released to improve compatibility with inclusion the Access Basic programming language.
    
-   The most significant transition was from Access 97 to Access 2000.
    
-   2007 - Access 2007, a new database format was introduced ACCDB which supports complex data types such as multi valued and attachment fields.
    

### Features

-   Users can create tables, queries, forms and reports and connect them together with macros.
    
-   Option of importing and exporting the data to many formats including Excel, Outlook, ASCII, dBase, Paradox, FoxPro, SQL Server, Oracle, ODBC, etc.
    
-   There is also the Jet Database format (MDB or ACCDB in Access 2007), which can contain the application and data in one file. This makes it very convenient to distribute the entire application to another user, who can run it in disconnected environments.
    
-   Microsoft Access offers parameterized queries. These queries and Access tables can be referenced from other programs like VB6 and .NET through DAO or ADO.
    
-   The desktop editions of Microsoft SQL Server can be used with Access as an alternative to the Jet Database Engine.
    
-   Microsoft Access is a file server-based database. Unlike the client-server relational database management systems (RDBMS), Microsoft Access does not implement database triggers, stored procedures or transaction logging.

# Syntax
SQL is a declarative language, therefore, its syntax reads like a natural language. An SQL statement begins with a verb that describes the action, for example, [SELECT](https://www.sqltutorial.org/sql-select/), [INSERT](https://www.sqltutorial.org/sql-insert/), [UPDATE](https://www.sqltutorial.org/sql-update/) or [DELETE](https://www.sqltutorial.org/sql-delete/). Following the verb are the subject and predicate.

A predicate specifies conditions that can be evaluated as true, false, or unknown.

See the following SQL statement:

    SELECT 
        first_name
    FROM
        employees
    WHERE
        YEAR(hire_date) = 2000;

As you see, it reads like a normal sentence.

Get the first names of employees who were hired in 2000.

The `SELECT first_name`, `FROM employees`, and [WHERE](https://www.sqltutorial.org/sql-where/) are clauses in the SQL statement. Some clauses are mandatory e.g., the `SELECT` and `FROM` clauses whereas others are optional such as the `WHERE` clause.

Because SQL was designed specifically for the non-technical people in mind, it is very simple and easy to understand. To write an SQL statement, you just need to tell what you want instead of how you want it like other imperative languages such as PHP, Java, and C++.

SQL is a user-friendly language because it is mainly for the users who perform ad-hoc queries and generate reports.

Nowadays, SQL is used by the highly technical people like data analysts, data scientists, developers, and database administrators.

## SQL commands

SQL is made up of many commands. Each SQL command is typically terminated with a semicolon (;). For example, the following are two different SQL commands separated by a semicolon (;).

```sql
SELECT 
    first_name, last_name
FROM
    employees;

DELETE FROM employees 
WHERE
    hire_date < '1990-01-01';
```

SQL uses the semicolon (;) to mark the end of a command.

Each command is composed of tokens that can be literals, keywords, identifiers, or expressions. Tokens are separated by space, tabs, or newlines.

## Literals

Literals are explicit values which are also known as constants. SQL provides three kinds of literals: string, numeric, and binary.

String literal consists of one or more alphanumeric characters surrounded by single quotes, for example:

```sql
'John'
'1990-01-01'
'50'
```
50 is a number. However, if you surround it with single quotes e.g., `'50'`, SQL treats it as a string literal.

Typically, SQL is _case sensitive_ with respect to string literals, so the value `'John'` is not the same as `'JOHN'`.

Numeric literals are the integer, decimal, or scientific notation, for example:
```sql
200
-5
6.0221415E23
```
SQL represents binary value using the notation `x'0000'`, where each digit is hexadecimal value, for example:
```sql
x'01'
x'0f0ff'
```
## Keywords

SQL has many keywords that have special meanings such as [SELECT](https://www.sqltutorial.org/sql-select/), [INSERT](https://www.sqltutorial.org/sql-insert/), [UPDATE](https://www.sqltutorial.org/sql-update/), [DELETE](https://www.sqltutorial.org/sql-delete/), and [DROP](https://www.sqltutorial.org/sql-drop-table/). These keywords are the reserved words, therefore, you cannot use them as the name of tables, columns, indexes, views, stored procedures, triggers, or other database objects.

## Identifiers

Identifiers refer to specific objects in the database such as tables, columns, indexes, etc. SQL is case-insensitive with respect to keywords and identifiers.

The following statements are equivalent.

    Select  * From employees;
    
    SELECT * FROM EMPLOYEES;
    
    select * from employees;
    
    SELECT * FROM employees;`



To make the SQL commands more readable and clear, we will use the SQL keywords in uppercase and identifiers in lower case throughout the tutorials.

## Comments

To document SQL statements, you use the SQL comments. When parsing SQL statements with comments, the database engine ignores the characters in the comments.

A comment is denoted by two consecutive hyphens ( `--`) that allow you to comment the remaining line. See the following example.

    SELECT 
        employee_id, salary
    FROM
        employees
    WHERE
        salary < 3000; -- employees with low salary

This is an SQL comment.

    -- employees with low salary
    


To document the code that can span multiple lines, you use the multiline C-style notation ( `/**/`) as the shown in the following statement:

    /* increase 5% for employees whose salary is less than 3,000 */
    UPDATE employees 
    SET 
        salary = salary * 1.05
    WHERE
        salary < 3000;

In this tutorial, we have introduced you to the SQL syntax that helps you understand each component of an SQL statement.

# Data Types
SQL Data Type is an attribute that specifies the type of data of any object. Each column, variable and expression has a related data type in SQL. You can use these data types while creating your tables. You can choose a data type for a table column based on your requirement.

SQL Server offers six categories of data types for your use which are listed below.

## Exact Numeric Data Types
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/5.PNG?raw=true)
## Approximate Numeric Data Types
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/6.PNG?raw=true)
## Date and Time Data Types
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/7.PNG?raw=true)
**Note** − Here, datetime has 3.33 milliseconds accuracy where as smalldatetime has 1 minute accuracy.

## Character Strings Data Types
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/8.PNG?raw=true)
## Binary Data Types
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/9.PNG?raw=true)
# Operators
## What is an Operator in SQL?

An operator is a reserved word or a character used primarily in an SQL statement's WHERE clause to perform operation(s), such as comparisons and arithmetic operations. These Operators are used to specify conditions in an SQL statement and to serve as conjunctions for multiple conditions in a statement.

-   Arithmetic operators
-   Comparison operators
-   Logical operators
-   Operators used to negate conditions
## SQL Arithmetic Operators

Assume **'variable a'** holds 10 and **'variable b'** holds 20, then

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/10.PNG?raw=true)
## SQL Comparison Operators

Assume **'variable a'** holds 10 and **'variable b'** holds 20, then

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/11.PNG?raw=true)
## SQL Logical Operators

Here is a list of all the logical operators available in SQL.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/12.PNG?raw=true)
# Expressions
An expression is a combination of one or more values, operators and SQL functions that evaluate to a value. These SQL EXPRESSIONs are like formulae and they are written in query language. You can also use them to query the database for a specific set of data.

### Syntax

Consider the basic syntax of the SELECT statement as follows

    SELECT column1, column2, columnN 
    FROM table_name 
    WHERE [CONDITION|EXPRESSION];
    
There are different types of SQL expressions, which are mentioned below −

-   Boolean
-   Numeric
-   Date

Let us now discuss each of these in detail.

## Boolean Expressions

SQL Boolean Expressions fetch the data based on matching a single value. Following is the syntax

    SELECT column1, column2, columnN 
    FROM table_name 
    WHERE SINGLE VALUE MATCHING EXPRESSION;

Consider the CUSTOMERS table having the following records
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/13.PNG?raw=true)

The following table is a simple example showing the usage of various SQL Boolean Expressions
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/14.PNG?raw=true)
## Numeric Expression

These expressions are used to perform any mathematical operation in any query. Following is the syntax.

    SELECT numerical_expression as  OPERATION_NAME
    [FROM table_name
    WHERE CONDITION] ;

Here, the numerical_expression is used for a mathematical expression or any formula. Following is a simple example showing the usage of SQL Numeric Expressions.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/15.PNG?raw=true)

There are several built-in functions like avg(), sum(), count(), etc., to perform what is known as the aggregate data calculations against a table or a specific table column.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/16.PNG?raw=true)
## Date Expressions

Date Expressions return current system date and time values.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/17.PNG?raw=true)
Another date expression is as shown below.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/18.PNG?raw=true)
# CREATE Database
The SQL **CREATE DATABASE** statement is used to create a new SQL database.

## Syntax

The basic syntax of this CREATE DATABASE statement is as follows.

    CREATE DATABASE DatabaseName;

Always the database name should be unique within the RDBMS.

## Example

If you want to create a new database <testDB>, then the CREATE DATABASE statement would be as shown below

    SQL> CREATE DATABASE testDB;
    
Make sure you have the admin privilege before creating any database. Once a database is created, you can check it in the list of databases as follows.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/19.PNG?raw=true)
# DROP or DELETE Database
The SQL **DROP DATABASE** statement is used to drop an existing database in SQL schema

## Syntax

The basic syntax of DROP DATABASE statement is as follows.

    DROP DATABASE DatabaseName;

Always the database name should be unique within the RDBMS.

## Example

If you want to delete an existing database <testDB>, then the DROP DATABASE statement would be as shown below.

    SQL> DROP DATABASE testDB;
    
**NOTE** − Be careful before using this operation because by deleting an existing database would result in loss of complete information stored in the database.

Make sure you have the admin privilege before dropping any database. Once a database is dropped, you can check it in the list of the databases as shown below.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/20.PNG?raw=true)
# SELECT Database, USE Statement
When you have multiple databases in your SQL Schema, then before starting your operation, you would need to select a database where all the operations would be performed.

The SQL **USE** statement is used to select any existing database in the SQL schema.
## Syntax

The basic syntax of the USE statement is as shown below.

    USE DatabaseName;

Always the database name should be unique within the RDBMS.

## Example

You can check the available databases as shown below

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/21.PNG?raw=true)
Now, if you want to work with the AMROOD database, then you can execute the following SQL command and start working with the AMROOD database.

    SQL> USE AMROOD;

# CREATE Table
Creating a basic table involves naming the table and defining its columns and each column's data type.

The SQL **CREATE TABLE** statement is used to create a new table.

## Syntax

The basic syntax of the CREATE TABLE statement is as follows.

    CREATE TABLE table_name(
       column1 datatype,
       column2 datatype,
       column3 datatype,
       .....
       columnN datatype,
       PRIMARY KEY( one or more columns )
    );

CREATE TABLE is the keyword telling the database system what you want to do. In this case, you want to create a new table. The unique name or identifier for the table follows the CREATE TABLE statement.

Then in brackets comes the list defining each column in the table and what sort of data type it is. The syntax becomes clearer with the following example.

## Example

The following code block is an example, which creates a CUSTOMERS table with an ID as a primary key and NOT NULL are the constraints showing that these fields cannot be NULL while creating records in this table

    SQL> CREATE TABLE CUSTOMERS(
	     ID   INT  NOT NULL,
	     NAME VARCHAR (20) NOT NULL,
	     AGE  INT              NOT NULL,
       ADDRESS  CHAR (25)  ,
       SALARY   DECIMAL (18,  2),
       PRIMARY KEY (ID)  
    );

You can verify if your table has been created successfully by looking at the message displayed by the SQL server, otherwise you can use the **DESC** command as follows.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/22.PNG?raw=true)
Now, you have CUSTOMERS table available in your database which you can use to store the required information related to customers.

# DROP or DELETE Table
The SQL **DROP TABLE** statement is used to remove a table definition and all the data, indexes, triggers, constraints and permission specifications for that table.

**NOTE** − You should be very careful while using this command because once a table is deleted then all the information available in that table will also be lost forever.

## Syntax

The basic syntax of this DROP TABLE statement is as follows.

    DROP TABLE table_name;

## Example

Let us first verify the CUSTOMERS table and then we will delete it from the database as shown below.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/23.PNG?raw=true)
This means that the CUSTOMERS table is available in the database, so let us now drop it as shown below.

    SQL> DROP TABLE CUSTOMERS;
    Query OK, 0 rows affected (0.01 sec)

Now, if you would try the DESC command, then you will get the following error.

    SQL> DESC CUSTOMERS;
    ERROR 1146 (42S02): Table 'TEST.CUSTOMERS' doesn't exist

Here, TEST is the database name which we are using for our examples.

# INSERT Query
The SQL **INSERT INTO** Statement is used to add new rows of data to a table in the database.

### Syntax

There are two basic syntaxes of the INSERT INTO statement which are shown below.

    INSERT INTO TABLE_NAME (column1, column2, column3,...columnN)  
    VALUES (value1, value2, value3,...valueN);
Here, column1, column2, column3,...columnN are the names of the columns in the table into which you want to insert the data.

You may not need to specify the column(s) name in the SQL query if you are adding values for all the columns of the table. But make sure the order of the values is in the same order as the columns in the table.

The **SQL INSERT INTO** syntax will be as follows.

    INSERT INTO TABLE_NAME VALUES (value1,value2,value3,...valueN);

### Example

The following statements would create six records in the CUSTOMERS table.

    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
    VALUES (1,  'Ramesh',  32,  'Ahmedabad',  2000.00  );
    
    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
    VALUES (2,  'Khilan',  25,  'Delhi',  1500.00  );
    
    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
    VALUES (3,  'kaushik',  23,  'Kota',  2000.00  ); 
    
    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
    VALUES (4,  'Chaitali',  25,  'Mumbai',  6500.00  ); 
    
    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
    VALUES (5,  'Hardik',  27,  'Bhopal',  8500.00  ); 
    
    INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
    VALUES (6,  'Komal',  22,  'MP',  4500.00  );

You can create a record in the CUSTOMERS table by using the second syntax as shown below.

    INSERT INTO CUSTOMERS 
    VALUES (7, 'Muffy', 24, 'Indore', 10000.00 );

All the above statements would produce the following records in the CUSTOMERS table as shown below.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/24.PNG?raw=true)
## Populate one table using another table

You can populate the data into a table through the select statement over another table; provided the other table has a set of fields, which are required to populate the first table.

Here is the syntax.

    INSERT INTO first_table_name [(column1, column2, ... columnN)] 
       SELECT column1, column2, ...columnN 
       FROM second_table_name
       [WHERE condition];

# SELECT Query
The SQL **SELECT** statement is used to fetch the data from a database table which returns this data in the form of a result table. These result tables are called result-sets.

## Syntax

The basic syntax of the SELECT statement is as follows.

    SELECT column1, column2, columnN FROM table_name;

Here, column1, column2... are the fields of a table whose values you want to fetch. If you want to fetch all the fields available in the field, then you can use the following syntax.

    SELECT * FROM table_name;

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/25.PNG?raw=true)The following code is an example, which would fetch the ID, Name and Salary fields of the customers available in CUSTOMERS table.

    SQL> SELECT ID, NAME, SALARY FROM CUSTOMERS;
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/26.PNG?raw=true)
If you want to fetch all the fields of the CUSTOMERS table, then you should use the following query.

    SQL> SELECT * FROM CUSTOMERS;

This would produce the result as shown below.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/27.PNG?raw=true)
# WHERE Clause
The SQL **WHERE** clause is used to specify a condition while fetching the data from a single table or by joining with multiple tables. If the given condition is satisfied, then only it returns a specific value from the table. You should use the WHERE clause to filter the records and fetching only the necessary records.

The WHERE clause is not only used in the SELECT statement, but it is also used in the UPDATE, DELETE statement, etc., which we would examine in the subsequent chapters.

## Syntax

The basic syntax of the SELECT statement with the WHERE clause is as shown below.

    SELECT column1, column2, columnN 
    FROM table_name
    WHERE [condition]
You can specify a condition using the comparison or logical operators like >, <, =, **LIKE, NOT**, etc. The following examples would make this concept clear.

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/28.PNG?raw=true)
The following code is an example which would fetch the ID, Name and Salary fields from the CUSTOMERS table, where the salary is greater than 2000.

    SQL> SELECT ID, NAME, SALARY 
    FROM CUSTOMERS
    WHERE SALARY >  2000;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/29.PNG?raw=true)The following query is an example, which would fetch the ID, Name and Salary fields from the CUSTOMERS table for a customer with the name **Hardik**.

Here, it is important to note that all the strings should be given inside single quotes (''). Whereas, numeric values should be given without any quote as in the above example.

    SQL> SELECT ID, NAME, SALARY 
    FROM CUSTOMERS
    WHERE NAME =  'Hardik';
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/30.PNG?raw=true)
# AND and OR Conjunctive Operators
The SQL **AND** & **OR** operators are used to combine multiple conditions to narrow data in an SQL statement. These two operators are called as the conjunctive operators.

These operators provide a means to make multiple comparisons with different operators in the same SQL statement.

## The AND Operator

The **AND** operator allows the existence of multiple conditions in an SQL statement's WHERE clause.

### Syntax

The basic syntax of the AND operator with a WHERE clause is as follows.

    SELECT column1, column2, columnN 
    FROM table_name
    WHERE [condition1] AND [condition2]...AND [conditionN];
You can combine N number of conditions using the AND operator. For an action to be taken by the SQL statement, whether it be a transaction or a query, all conditions separated by the AND must be TRUE.

### Example

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/32.PNG?raw=true)
Following is an example, which would fetch the ID, Name and Salary fields from the CUSTOMERS table, where the salary is greater than 2000 and the age is less than 25 years.

    SQL> SELECT ID, NAME, SALARY 
    FROM CUSTOMERS
    WHERE SALARY >  2000 AND age <  25;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/33.PNG?raw=true)
## The OR Operator

The OR operator is used to combine multiple conditions in an SQL statement's WHERE clause.

### Syntax

The basic syntax of the OR operator with a WHERE clause is as follows.

    SELECT column1, column2, columnN 
    FROM table_name
    WHERE [condition1] OR [condition2]...OR [conditionN]
You can combine N number of conditions using the OR operator. For an action to be taken by the SQL statement, whether it be a transaction or query, the only any ONE of the conditions separated by the OR must be TRUE.

### Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/35.PNG?raw=true)
The following code block hasa query, which would fetch the ID, Name and Salary fields from the CUSTOMERS table, where the salary is greater than 2000 OR the age is less than 25 years.

    SQL> SELECT ID, NAME, SALARY 
    FROM CUSTOMERS
    WHERE SALARY >  2000 OR age <  25;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/36.PNG?raw=true)
# UPDATE Query
The SQL **UPDATE** Query is used to modify the existing records in a table. You can use the WHERE clause with the UPDATE query to update the selected rows, otherwise all the rows would be affected.

## Syntax

The basic syntax of the UPDATE query with a WHERE clause is as follows.

    UPDATE table_name
    SET column1 = value1, column2 = value2...., columnN = valueN
    WHERE [condition];
You can combine N number of conditions using the AND or the OR operators.

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/37.PNG?raw=true)
The following query will update the ADDRESS for a customer whose ID number is 6 in the table.

    SQL> UPDATE CUSTOMERS
    SET ADDRESS =  'Pune' WHERE ID =  6;
Now, the CUSTOMERS table would have the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/38.PNG?raw=true)
If you want to modify all the ADDRESS and the SALARY column values in the CUSTOMERS table, you do not need to use the WHERE clause as the UPDATE query would be enough as shown in the following code block.

    SQL> UPDATE CUSTOMERS
    SET ADDRESS =  'Pune', SALARY =  1000.00;

Now, CUSTOMERS table would have the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/39.PNG?raw=true)
# DELETE Query
The SQL DELETE Query is used to delete the existing records from a table.

You can use the WHERE clause with a DELETE query to delete the selected rows, otherwise all the records would be deleted.

## Syntax

The basic syntax of the DELETE query with the WHERE clause is as follows.

    DELETE FROM table_name
    WHERE [condition];

You can combine N number of conditions using AND or OR operators.

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/40.PNG?raw=true)
The following code has a query, which will DELETE a customer, whose ID is 6.

    SQL> DELETE FROM CUSTOMERS
    WHERE ID =  6;

Now, the CUSTOMERS table would have the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/41.PNG?raw=true)
If you want to DELETE all the records from the CUSTOMERS table, you do not need to use the WHERE clause and the DELETE query would be as follows.

    SQL> DELETE FROM CUSTOMERS;
Now, the CUSTOMERS table would not have any record.

# LIKE Clause
The SQL **LIKE** clause is used to compare a value to similar values using wildcard operators. There are two wildcards used in conjunction with the LIKE operator.

-   The percent sign (%)
-   The underscore (_)

The percent sign represents zero, one or multiple characters. The underscore represents a single number or character. These symbols can be used in combinations.

## Syntax

The basic syntax of % and _ is as follows.

    SELECT FROM table_name
    WHERE column LIKE 'XXXX%'
    
    or 
    
    SELECT FROM table_name
    WHERE column LIKE '%XXXX%'
    
    or
    
    SELECT FROM table_name
    WHERE column LIKE 'XXXX_'
    
    or
    
    SELECT FROM table_name
    WHERE column LIKE '_XXXX'
    
    or
    
    SELECT FROM table_name
    WHERE column LIKE '_XXXX_'

You can combine N number of conditions using AND or OR operators. Here, XXXX could be any numeric or string value.

## Example

The following table has a few examples showing the WHERE part having different LIKE clause with '%' and '_' operators.

![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/42.PNG?raw=true)
Let us take a real example, consider the CUSTOMERS table having the records as shown below.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/43.PNG?raw=true)
Following is an example, which would display all the records from the CUSTOMERS table, where the SALARY starts with 200.

    SQL> SELECT * FROM CUSTOMERS
    WHERE SALARY LIKE '200%';

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/44.PNG?raw=true)
# TOP, LIMIT or ROWNUM Clause
The SQL **TOP** clause is used to fetch a TOP N number or X percent records from a table.

**Note** − All the databases do not support the TOP clause. For example MySQL supports the **LIMIT** clause to fetch limited number of records while Oracle uses the **ROWNUM** command to fetch a limited number of records.

## Syntax

The basic syntax of the TOP clause with a SELECT statement would be as follows.

    SELECT TOP number|percent column_name(s)
    FROM table_name
    WHERE [condition]

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/45.PNG?raw=true)
The following query is an example on the SQL server, which would fetch the top 3 records from the CUSTOMERS table.

    SQL> SELECT TOP 3  * FROM CUSTOMERS;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/46.PNG?raw=true)
If you are using MySQL server, then here is an equivalent example.

    SQL> SELECT * FROM CUSTOMERS
    LIMIT 3;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/47.PNG?raw=true)
If you are using an Oracle server, then the following code block has an equivalent example.

    SQL> SELECT * FROM CUSTOMERS
    WHERE ROWNUM <=  3;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/48.PNG?raw=true)
# ORDER BY Clause
The SQL **ORDER BY** clause is used to sort the data in ascending or descending order, based on one or more columns. Some databases sort the query results in an ascending order by default.

## Syntax

The basic syntax of the ORDER BY clause is as follows.

    SELECT column-list 
    FROM table_name 
    [WHERE condition] 
    [ORDER BY column1, column2, .. columnN] [ASC | DESC];

You can use more than one column in the ORDER BY clause. Make sure whatever column you are using to sort that column should be in the column-list.

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/49.PNG?raw=true)
The following code block has an example, which would sort the result in an ascending order by the NAME and the SALARY.

    SQL> SELECT * FROM CUSTOMERS
       ORDER BY NAME, SALARY;

This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/50.PNG?raw=true)
The following code block has an example, which would sort the result in the descending order by NAME.

    SQL> SELECT * FROM CUSTOMERS
       ORDER BY NAME DESC;
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/51.PNG?raw=true)
# Group By
The SQL **GROUP BY** clause is used in collaboration with the SELECT statement to arrange identical data into groups. This GROUP BY clause follows the WHERE clause in a SELECT statement and precedes the ORDER BY clause.

## Syntax

The basic syntax of a GROUP BY clause is shown in the following code block. The GROUP BY clause must follow the conditions in the WHERE clause and must precede the ORDER BY clause if one is used.

    SELECT column1, column2
    FROM table_name
    WHERE [ conditions ]
    GROUP BY column1, column2
    ORDER BY column1, column2
## Example

Consider the CUSTOMERS table is having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/52.PNG?raw=true)
If you want to know the total amount of the salary on each customer, then the GROUP BY query would be as follows.

    SQL> SELECT NAME, SUM(SALARY) FROM CUSTOMERS
       GROUP BY NAME;

   This would produce the following result.
   ![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/53.PNG?raw=true)
   Now, let us look at a table where the CUSTOMERS table has the following records with duplicate names.
   ![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/54.PNG?raw=true)
   Now again, if you want to know the total amount of salary on each customer, then the GROUP BY query would be as follows.

       SQL> SELECT NAME, SUM(SALARY) FROM CUSTOMERS
       GROUP BY NAME;

   This would produce the following result.
   ![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/55.PNG?raw=true)
# Distinct Keyword
The SQL **DISTINCT** keyword is used in conjunction with the SELECT statement to eliminate all the duplicate records and fetching only unique records.

There may be a situation when you have multiple duplicate records in a table. While fetching such records, it makes more sense to fetch only those unique records instead of fetching duplicate records.

## Syntax

The basic syntax of DISTINCT keyword to eliminate the duplicate records is as follows.

    SELECT DISTINCT column1, column2,.....columnN 
    FROM table_name
    WHERE [condition]

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/56.PNG?raw=true)
First, let us see how the following SELECT query returns the duplicate salary records.

    SQL> SELECT SALARY FROM CUSTOMERS
       ORDER BY SALARY;

This would produce the following result, where the salary (2000) is coming twice which is a duplicate record from the original table.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/57.PNG?raw=true)
Now, let us use the DISTINCT keyword with the above SELECT query and then see the result.

    SQL> SELECT DISTINCT SALARY FROM CUSTOMERS
       ORDER BY SALARY;

This would produce the following result where we do not have any duplicate entry.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/58.PNG?raw=true)
# SORTING Results
The SQL **ORDER BY** clause is used to sort the data in ascending or descending order, based on one or more columns. Some databases sort the query results in an ascending order by default.

## Syntax

The basic syntax of the ORDER BY clause which would be used to sort the result in an ascending or descending order is as follows.

    SELECT column-list 
    FROM table_name 
    [WHERE condition] 
    [ORDER BY column1, column2, .. columnN] [ASC | DESC];

You can use more than one column in the ORDER BY clause. Make sure that whatever column you are using to sort, that column should be in the column-list.

## Example

Consider the CUSTOMERS table having the following records.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/59.PNG?raw=true)
Following is an example, which would sort the result in an ascending order by NAME and SALARY.

    SQL> SELECT * FROM CUSTOMERS
       ORDER BY NAME, SALARY;
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/60.PNG?raw=true)
The following code block has an example, which would sort the result in a descending order by NAME.

    SQL> SELECT * FROM CUSTOMERS
       ORDER BY NAME DESC;
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/61.PNG?raw=true)
To fetch the rows with their own preferred order, the SELECT query used would be as follows.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/62.PNG?raw=true)
This would produce the following result.
![enter image description here](https://github.com/gitmag-group-admin/SQL/blob/main/63.PNG?raw=true)
This will sort the customers by ADDRESS in your **ownoOrder** of preference first and in a natural order for the remaining addresses. Also, the remaining Addresses will be sorted in the reverse alphabetical order.



                                                                                                                                                            
