# sql-basics-to-pro
sql user login admin, database creation, filter and join tables

## Login to mysql on command line
`$ mysql -u root -p secretpasword ;`

## Create user
`$ CREATE USER 'webuser'@'localhost';`
`$ CREATE USER 'webuser'@'localhost' IDENTIFIED BY 'secretpasword';`

## Change passwords
`$ ALTER USER 'webuser'@'localhost' IDENTIFIED BY 'secretpassword';`
`$ SET PASSWORD FOR 'jeffrey'@'localhost' = 'auth_string';`

## Permissions for users.   
```$ GRANT ALL PRIVILEGES ON globe_bank.* TO 'webuser'@'localhost';```  
```$ GRANT ALL PRIVILEGES ON orderingXX.* TO 'pmauser'@'localhost';```
`$ SHOW GRANTS FOR 'webuser'@'localhost';`   
`$ SHOW GRANTS FOR 'root'@'localhost';`  

##  Create,Use and Drop database

`$ SHOW DATABASES;`
`$ USE db_name;`
`$ DROP db_name;`


##  Create Table and Drop if Exists using Primary Key Constraint and Default Values

`$ DROP TABLE IF EXISTS `subjects`;`

```sql
CREATE TABLE `subjects` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `menu_name` varchar(255) DEFAULT NULL,
  `position` int(3) DEFAULT NULL,
  `visible` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`)
);
```
'$ INSERT INTO `subjects` VALUES (1,'About Globe Bank',1,1),(2,'Consumer',2,1),(3,'Small Business',3,0);'

`$ DROP TABLE IF EXISTS `pages`;`
```sql  

# ONE TO MANY RELATIONSHIPS with foreign key feature of Relational database

##  Create Another Table using Foreign Key, Primary Key Constraint and Default Values

$ CREATE TABLE `pages` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `subject_id` int(11) DEFAULT NULL,
  `menu_name` varchar(255) DEFAULT NULL,
  `position` int(3) DEFAULT NULL,
  `visible` tinyint(1) DEFAULT NULL,
  `content` text,
  PRIMARY KEY (`id`),
  KEY `fk_subject_id` (`subject_id`)
);
```
##  Insert into Table  

`$ INSERT INTO `pages` VALUES (1,1,'Globe Bank',1,1,NULL),(2,1,'History',2,1,NULL),(3,1,'Leadership',3,1,NULL),(4,1,'Contact Us',4,1,NULL),(5,2,'Banking',1,1,NULL),(6,2,'Credit Cards',2,1,NULL),(7,2,'Mortgages',3,1,NULL),(8,3,'Checking',1,1,NULL),(9,3,'Loans',2,1,NULL),(10,3,'Merchant Services',3,1,NULL);` 

`$ INSERT INTO `subjects` VALUES (1,'About Globe Bank',1,1),(2,'Consumer',2,1),(3,'Small Business',3,0);`  
`$ `

##  After we create table, we can add too.


`$ ALTER TABLE ADD INDEX index_name (column);`
`$ ALTER TABLE ADD INDEX fk_name (column);`


##  Stored Procedures and Routines pl/sql

`$ `
`$ `
`$ `

[SQL | DDL, DQL, DML, DCL and TCL Commands](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)
