<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Git Basic</span>](Git.md)
[Basic](Git-Basic.md) | 
[Structure](Git-Structure.md) | 
[Script](Git-Script.md)


<div class="md3"></div>
<a href="#Resource">Resource</a> - 
<a href="#Install">Install</a> - 
<a href="#Tools">Tools</a> - 
<a href="#Concept">Concept</a>





<div class="md3"></div>

![](Git.jpeg)





<div class="md1"></div>

## Resource

#### General

<a href="http://git-scm.com" target="_blank">git-scm</a> - <a href="http://github.com" target="_blank">github</a> - <a href="http://gitlab.com" target="_blank">gitlab</a>

#### Tutorial

<a href="http://faradars.org" target="_blank">faradars</a> - <a href="http://roocket.ir" target="_blank">roocket</a> - <a href="http://clicksite.org" target="_blank">clicksite</a> - <a href="http://faranesh.com" target="_blank">faranesh</a> -








<div class="md0"></div>

## Install

#### Ubuntu

    sudo apt install git-core

    sudo apt install git-all

#### Centos

    dnf --enablerepo="epel" install git





<div class="md0"></div>

## Tools
    Ohmyzsh  گرافیک git

    git --version





<div class="md0"></div>

## Concept

<div align="right" dir="rtl">
گیت یک مخزن (repository) می سازه که از سه لایه منطقی به فایل ها نگاه میکنه :
<br>
1 – لایه اول یا همان (working tree) که هنوز اقدامی برای ثبت تغییرات انجام نشده و فایل ها در حال تغییر هستند 
<br>
2 – لایه دوم یا همان (stage)که با وارد کردن فایل ها به این لایه، آنها آماده ثبت تغییر می شوند
<br>
3 – لایه سوم (Repository) که تمام تغییرات فایل ها ثبت می شوند
</div>
<br>
<div align="right" dir="rtl">
fork کردن در واقع یعنی یه کپی از پروژه گرفتن و تغییر دادنش
<br>
میشود از سازندش در خواست کرد تغیییرات رو ببینه و با پروژه اصلی خودش مرج کنه
</div>