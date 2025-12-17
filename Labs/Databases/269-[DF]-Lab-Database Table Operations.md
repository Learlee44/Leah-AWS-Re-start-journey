# Database Table Operations

## Scenario
The database operations team for an organization has configured a relational database instance. The team has asked you to practice creating and dropping (deleting) databases and tables.
---

This Lab demonstrates how to use some common database and table operations.
---

### Lab Architecture

A database client is installed on an instance.
![image](Architecture.png)
![image](Diagram.png)
A lab user creates a database and tables. Other displayed statements are SHOW, ALTER, and DROP.
---

## Task 1: Connect to the Command Host

In this task, I connect to an EC2 instance configured with a database client. The client is used to run structured query language(SQL) queries against a relational database.
---
### Steps taken:
1. In th AWS Management Console, Choose the Service menu. Choose Compute and then EC2.

2. In the left navigation menu, choose Instances.

3. Next to the instance labelled Command Host, select the check box  and then choose Connect.

4. For Connect to instance, choose the Session Manager tab.

5. Choose Connect to open a terminal window.

6. To configure the terminal to access all required tools and resources, run the following command:
 `sudo su`
`cd /home/ec2-user/`

7. To connect to the relational database instance, run the following command in the terminal. A password was configured when the database was installed.
 `mysql -u root --password='re:St@rt!9'`

![image](Dashboard.png)
![image](<EC2 Instances.png>)
![image](<Connect to Instance.png>)
![image](<Screenshot 2025-12-14 183901.png>)
---


## Task 2: Create a database and a table

In this task,I create a database named world and a table named country.I then alter the country table.
---
### Steps taken:

1. To show the existing databases, run the following query:
`SHOW DATABASES;`

2. To create a new database named world, run the following command:
`CREATE DATABASE world;`

3. To verify that the world database has been created, run the following query:
`SHOW DATABASES;`

![image](<Step 1.png>)
![image](<Step 2 - 3.png>)
---

4.  To create a table named country, run the following command:
 `CREATE TABLE world.country `(
  `Code` CHAR(3) NOT NULL DEFAULT '',
  `Name` CHAR(52) NOT NULL DEFAULT '',
  `Conitinent` enum('Asia','Europe','North America','Africa','Oceania','Antarctica','South  America') NOT NULL DEFAULT 'Asia',
  `Region` CHAR(26) NOT NULL DEFAULT '',
  `SurfaceArea` FLOAT(10,2) NOT NULL DEFAULT '0.00',
  `IndepYear` SMALLINT(6) DEFAULT NULL,
  `Population` INT(11) NOT NULL DEFAULT '0',
  `LifeExpectancy` FLOAT(3,1) DEFAULT NULL,
  `GNP` FLOAT(10,2) DEFAULT NULL,
  `GNPOld` FLOAT(10,2) DEFAULT NULL,
  `LocalName` CHAR(45) NOT NULL DEFAULT '',
  `GovernmentForm` CHAR(45) NOT NULL DEFAULT '',
  `HeadOfState` CHAR(60) DEFAULT NULL,
  `Capital` INT(11) DEFAULT NULL,
  `Code2` CHAR(2) NOT NULL DEFAULT '',
  PRIMARY KEY (`Code`)
  );

5. To verify that the country table was created, use the SHOW TABLES; command to list the tables in the database. You use the USE command to specify which database to run a query against. Run the following commands in your terminal:
 `USE world;`
 `SHOW TABLES;`

6. Use the SHOW COLUMNS query to list all the columns on a table. Run the following query to list all columns and their properties in the country table:
 `SHOW COLUMNS FROM world.country;`

7. The ALTER TABLE command is used to alter the table's schema. To fix the incorrectly spelled Continent column, run the following command:
 `ALTER TABLE world.country RENAME COLUMN Conitinent TO Continent;`

8. To verify that the Continent column name in the country table has been corrected, run the following query:
 `SHOW COLUMNS FROM world.country;`

 ![image](<Screenshot 2025-12-14 184014.png>)
 ![image](<Step 4.png>)
 ![image](<Steps 5 - 6.png>)
 ![image](<Steps 7 - 8.png>)
---

## Challenge 1
Create a table named city and add two columns named Name and Region. Both columns should use the CHAR data type
### Code:
`CREATE TABLE world.city (`Name` CHAR(52), `Region` CHAR(26));`

![image](<Challenge 1.png>)

## Task 3: Delete a database and table 
In this task,I delete the world database and country table.

### Steps taken

1. The DROP TABLE command is used to delete (drop) a table in a database. Once a table has been dropped, it cannot be recovered unless a backup is available. To drop the city table, run the following command:
 `DROP TABLE world.city;`

 ## Challenge 2 

 To drop the country table, run the following command:
  `DROP TABLE world.country;`

1. To verify that both tables have been dropped, run the following query:
 `SHOW TABLES;`

2. To drop the world database, run the following command:
 `DROP DATABASE world;`

3. To verify that the world database has been deleted, run the following query:
 `SHOW DATABASES;`


 ![image](<Challenge 2 show database.png>)
 ![image](<Lab complete.png>)
---

# Lab Complete