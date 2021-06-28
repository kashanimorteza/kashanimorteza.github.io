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


# [<span style="color:black;">Mysql Basic</span>](Mysql.md)


<div class="md3"></div>

[Basic](Basic.md) | 
[Structure](Structure.md) | 
[Command](Command.md)


<div class="md3">
<a href="#resource">Resource</a> - 
<a href="#install">Install</a> - 
<a href="#config">Config</a> - 
<a href="#question">Question</a> 
</div>





## Diagram

<div class="md3">

![](Diagram/Mysql.jpeg)

</div>





## Resource

<div class="md1">

#### General
<a href="https://www.mysql.com/" target="_blank">mysql</a>

#### Learn
<a href="https://www.tutorialspoint.com/mysql/index.htm" target="_blank">tutorialspoint</a> - 
<a href="https://www.w3schools.com/sql/" target="_blank">w3schools</a> - 
<a href="https://www.quackit.com/mysql/tutorial/" target="_blank">quackit</a>

</div>






## Install

<div class="md1">

#### Windows

    Add This address into PATH user variable : C:\Program Files\MySQL\MySQL Server 8.0\bin
    <div class="md5"></div>
    mysqladmin --version
    <div class="md5"></div>
    mysql -u root -p

#### Ubuntu

    sudo apt install mysql-server

    sudo apt remove --purge mysql*

</div>





## Config

<div class="md1">

#### Ubuntu

    security script 
    ---------------
    sudo mysql_secure_installation


    Network  
    ------------------------------------------
    sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf

    [mysql]
    bind-address            = 0.0.0.0



    Service
    ------------
    sudo service mysql status
    sudo service mysql restart

    sudo systemctl status mysql
    sudo systemctl restart mysql

    netstat -na | grep 3306


    Firewall
    ---------------
    sudo ufw enable
    sudo ufw allow mysql

</div>





## Question

<div class="md1">

</div>