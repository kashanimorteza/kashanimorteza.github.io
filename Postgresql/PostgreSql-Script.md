<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;"> Postgresql Script</span>]( Postgresql.md)
[Basic]( Postgresql-Basic.md) | 
[Structure]( Postgresql-Structure.md) | 
[Script]( Postgresql-Script.md)


<div class="md3"></div>
<a href="#Command">Command</a> - 
<a href="#Database">Database</a> - 
<a href="#Statements">Statements</a> 





<div class="md1"></div>

## Administration

#### Engin
	psql --help
	psql --version

	sudo -i -u postgres
	psql
	\conninfo

	psql -h 127.0.0.1 -U postgres


#### User
	Show all Users : \du

	Change password : ALTER USER postgres WITH PASSWORD '123456';

	Create User : CREATE USER morteza WITH SUPERUSER PASSWORD '123456';
	





<div class="md0"></div>

## Schema 

	CREATE SCHEMA tick;
	
	DROP SCHEMA tick;





<div class="md0"></div>

## Database
	CREATE DATABASE forex;
	
	\l
	
	\c forex;
	
	DROP DATABASE forex;
	
	DROP DATABASE IF EXISTS forex;


#### Table	
	\d
	
	\d eurusd_m1
	
	DROP TABLE eurusd_m1;
	
<span><span>


#### View
	---------------------------------------------[Database]
	\l
	
<span><span>
	







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

