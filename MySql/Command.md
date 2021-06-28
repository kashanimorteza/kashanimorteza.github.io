<style>
.md0{padding-bottom: 150px;}
.md1{padding-bottom: 75px;}
.md2{padding-bottom: 50px;}
.md3{padding-bottom: 25px;}
.md4{padding-bottom: 5px;}
.md5{padding-bottom: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C}
.blue{color:#3498DB}
.green{color:##28B463}
table{border: 0px solid black;}
</style>


# [<span style="color:black;">Mysql Command</span>](Mysql.md)


<div class="md3"></div>

[Basic](Basic.md) | 
[Structure](Structure.md) | 
[Command](Command.md)


<div class="md3">
<a href="#administration">Administration</a> - 
<a href="#schema">Schema</a> - 
<a href="#database">Database</a> -
<a href="#table">Table</a> -
<a href="#statement">Statement</a>
</div>





## Administration

<div class="md1">

#### Engin
	psql --help
	psql --version

	sudo -i -u postgres
	psql
	\conninfo

	psql -h 127.0.0.1 -U postgres

#### User

	select host, user  from mysql.user;

	CREATE USER 'morteza'@'%' IDENTIFIED BY 'Morteza!@#$1234';

	ALTER USER 'morteza'@'%' IDENTIFIED BY 'Morteza!@#$1234';

	GRANT ALL PRIVILEGES ON *.* TO 'morteza'@'%';
	
</div>








<div class="md1"></div>

## Schema
	CREATE SCHEMA FruitShop;






<div class="md0"></div>

## Database
	SHOW DATABASES;

	CREATE DATABASE Forex;

	CREATE DATABASE IF NOT EXISTS Forex;

	DROP DATABASE IF EXISTS Forex;

	USE Forex;






<div class="md0"></div>

## Table
	SHOW TABLES;

	DESCRIBE EURUSD;

	CREATE TABLE EURUSD (
	Id TINYINT UNSIGNED NOT NULL AUTO_INCREMENT,
	Date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
	PRIMARY KEY (Id)
	)ENGINE=InnoDB DEFAULT CHARSET=utf8;



<div class="md0"></div>

## Statements

#### Select

#### Insert

#### Update

#### Delete

