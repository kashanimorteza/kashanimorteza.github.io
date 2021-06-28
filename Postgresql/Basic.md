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


# [<span style="color:black;">Postgresql Basic</span>]( Index.md)

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

![](Diagram/Postgresql.jpeg)

</div>




## Resource

<div class="md1">

#### General

<a href="https://www. Postgresql.com/" target="_blank"> Postgresql</a>

#### Learn

<a href="https://www.tutorialspoint.com/ Postgresql/index.htm" target="_blank">tutorialspoint</a> - 
<a href="https://www.w3schools.com/sql/" target="_blank">w3schools</a> - 
<a href="https://www.quackit.com/ Postgresql/tutorial/" target="_blank">quackit</a>

</div>







## Install

<div class="md1">

#### Windows

    Add This address into PATH user variable : C:\Program Files\ Postgresql\ Postgresql Server 8.0\bin

#### Ubuntu

Install

    sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
    sudo apt-get update
    sudo apt-get -y install postgresql

</div>





## Config

<div class="md1">

#### Ubuntu

    sudo vim /etc/postgresql/12/main/postgresql.conf
    ------------------------------------------------
    listen_addresses = '*'

    sudo vim /etc/postgresql/12/main/pg_hba.conf
    --------------------------------------------
    host all all 0.0.0.0/0 md5

    sudo service postgresql restart

</div>





<div class="md0"></div>

## Question

1 - aaaaaaaa
<br>