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


# [<span style="color:black;">Postgresql Command</span>]( Index.md)

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
	Show all Users : \du

	Change password : ALTER USER postgres WITH PASSWORD '123456';

	Create User : CREATE USER morteza WITH SUPERUSER PASSWORD '123456';
	
</div>






## Schema 

<div class="md1">

	CREATE SCHEMA tick;
	
	DROP SCHEMA tick;
</div>






## Database

<div class="md0">

	SHOW DATABASES;
	CREATE DATABASE Forex;
	CREATE DATABASE IF NOT EXISTS Forex;
	DROP DATABASE IF EXISTS Forex;
	USE Forex;

	CREATE DATABASE forex;
	
	\l
	
	\c forex;
	
	DROP DATABASE forex;
	
	DROP DATABASE IF EXISTS forex;
	
</div>








## Table

<div class="md1">

	SHOW TABLES;

	DESCRIBE EURUSD;

	CREATE TABLE EURUSD (
	Id TINYINT UNSIGNED NOT NULL AUTO_INCREMENT,
	Date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
	PRIMARY KEY (Id)
	)ENGINE=InnoDB DEFAULT CHARSET=utf8;


	\d
	
	\d eurusd_m1
	
	DROP TABLE eurusd_m1;
	
</div>








## Statement

<div class="md1">

#### Select

#### Insert

#### Update

#### Delete

</div>

