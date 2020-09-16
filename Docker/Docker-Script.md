<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Docker Script</span>](Docker.md)
[Basic](Docker-Basic.md) | 
[Structure](Docker-Structure.md) | 
[Script](Docker-Script.md)


<div class="md3"></div>
<a href="#Config">Config</a> - 
<a href="#Docker-ignore">Docker Ignore</a> - 
<a href="#Dockerlab-add-ssh-key">Add ssh key</a> -
<a href="#basic-command">Basic command</a>
<br>
<a href="#init">init</a> - 
<a href="#clone">clone</a>
<br>
<a href="#add">add</a> - 
<a href="#mv">mv</a> - 
<a href="#restore">restore</a> - 
<a href="#rm">rm</a> - 
<a href="#sparse-checkout">sparse-checkout</a>
<br>
<a href="#bisect">bisect</a> - 
<a href="#diff">diff</a> - 
<a href="#grep">grep</a> - 
<a href="#log">log</a> - 
<a href="#show">show</a> - 
<a href="#status">status</a> - 
<br>
<a href="#branch">branch</a>
<a href="#commit">commit</a> - 
<a href="#merge">merge</a> - 
<a href="#rebase">rebase</a> - 
<a href="#reset">reset</a> - 
<a href="#switch">switch</a> - 
<a href="#tag">tag</a> - 
<a href="#Collaborate">Collaborate</a>
<br>
<a href="#fetch">fetch</a> - 
<a href="#pull">pull</a> - 
<a href="#push">push</a> -
<a href="#remote">remote</a>






<div class="md1"></div>

## Config

#### User

    Docker config --global user.email "kashani.morteza@gmail.com"      
    Docker config --global user.name "morteza"

#### Color highlighting

    Docker config --global color.ui true
    Docker config --global color.status auto
    Docker config --global color.branch auto

#### Setting default editor
    
    Docker config --global core.editor vim

#### Setting default merge tool

    Docker config --global merge.tool vimdiff

#### Listing Docker settings
    
    Docker config --list    







<div class="md0"></div>

## Docker Ignore
| Command | Explain |
| ------ | ------ |
| touch .Dockerignore | <span align="right" dir="rtl"> اول یک فایل میسازیم  <span>  |
| videos/ <br> sound/1.mp3 <br> *.dll <br> !myfolder/m.dll | <span align="right" dir="rtl"> آدرس فایل ها رو قرار می دهیم <span>  |







<div class="md0"></div>

## Dockerlab Add ssh key

    ssh -V
    cd /home/morteza/.ssh/
    ssh-keygen -t rsa -b 2048 -C "kashani.morteza@gmail.com"
    add thes address : /home/morteza/.ssh/Dockerlab

    cat /home/morteza/.ssh/Dockerlab.pub
    copy code and paste to Dockerlab : Settings > SSH Keys

    ssh -T Docker@Dockerlab.com
    
    vim /home/morteza/.ssh/config     
    Host kashani.morteza.Dockerlab.com
     Preferredauthentications publickey
     IdentityFile ~/.ssh/Dockerlab





<div class="md0"></div>

## Basic command

| Command | Explain |
| ------ | ------ |
| Docker init | <span align="right" dir="rtl"> اول باید به گیت گفت این پوشه رو تحت مدیریت خودت قرار بده <span>  |
| Docker status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| vim test.text | <span align="right" dir="rtl"> لایه اول : ساخت فایل test.txt <span>  |
| Docker status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| Docker add test.txt | <span align="right" dir="rtl"> لایه دوم : بردن فایل به لایه دوم (Stage) <span>  |
| Docker status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| Docker commit ‘first commit’ | <span align="right" dir="rtl"> لایه سوم : ثبت همه تغییرات <span>  |
| Docker status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| Docker log | <span align="right" dir="rtl"> گزارش کامیت ها <span>  |






<div class="md0"></div>

## Start a working area

#### init

| Command | Explain |
| ------ | ------ |
| Docker init | <span align="right" dir="rtl"> شروع پروژه <span>  |
| Docker clone https://Dockerhub.com/atom/atom.Docker | <span align="right" dir="rtl"> دانلود و شروع پروژه <span>  |

#### clone








<div class="md0"></div>

## Work on the current change

#### add

#### mv

#### restore

#### rm

#### sparse-checkout 








<div class="md0"></div>

## Examine the history and state 

#### bisect

####  diff

| Command | Explain |
| ------ | ------ |
| vim test.text | <span align="right" dir="rtl"> یه تغییراتی در فایل میدهیم <span>  |
| Docker diff head | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه سوم (head) <span>  |
| Docker add test.txt | <span align="right" dir="rtl"> بردن فایل به لایه دوم (Stage) <span>  |
| Docker diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |
| vim test.text | <span align="right" dir="rtl"> یه تغییراتی در فایل میدهیم <span>  |
| Docker diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |


####  grep

#### log

| Command | Explain |
| ------ | ------ |
| Docker log | <span align="right" dir="rtl"> لیست commit های انجام شده را نشان می دهد <span>  |
| stash | <span align="right" dir="rtl"> میتونی چندین استش درست کنی و فایل ها رو که تغییر میدی داخلش نگه داری<br> و هر وقت دوست داشتی برشون گردونی به work directory <span>  |

#### show

#### status    








<div class="md0"></div>

## grow, mark and tweak your common history

#### branch

| Command | Explain |
| ------ | ------ |
| Docker branch | <span align="right" dir="rtl"> لیست branch <span>  |
| Docker checkout –b dev | <span align="right" dir="rtl"> ساخت branch <span>  |
| Docker checkout dev | <span align="right" dir="rtl"> سوئیچ به branch <span>  |
| Docker branch –d dev | <span align="right" dir="rtl"> حذف branch <span>  |
| Docker merge dev | <span align="right" dir="rtl"> یکی کردن branch <span>  |

#### commit

#### merge

#### rebase

#### reset

| Command | Explain |
| ------ | ------ |
| Docker reset test.txt | <span align="right" dir="rtl"> برگشت از stage به work directory <span>  |
| Docker checkout -- test.txt | <span align="right" dir="rtl"> برگشت از head به work directory <span>  |
| Docker reset hash code | <span align="right" dir="rtl"> برگشت از commit به work directory <span>  |

#### switch

#### tag

| Command | Explain |
| ------ | ------ |
| Docker tag | <span align="right" dir="rtl"> لیست تگ ها رو نشون میده <span>  |
| Docker tag –a v.a | <span align="right" dir="rtl">  <span>  |
| Docker push origin --tags | <span align="right" dir="rtl">  <span>  |
| Docker tag | <span align="right" dir="rtl">  <span>  |








<div class="md0"></div>

## Collaborate

#### fetch

#### pull

#### push

#### remote

| Command | Explain |
| ------ | ------ |
| Docker clone [url] | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Docker remote add origin [url]  | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Docker push Origin master  | <span align="right" dir="rtl"> یعنی اطلاعات رو بفرست به ریموت <span>  |
| Docker pull Origin master  | <span align="right" dir="rtl"> اطلاعات رو از ریپازیتوری بگیر <span>  |