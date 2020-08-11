<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Mysql Script</span>](Mysql.md)
[Basic](Mysql-Basic.md) | [Structure](Mysql-Structure.md) | [Script](Mysql-Script.md)




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

