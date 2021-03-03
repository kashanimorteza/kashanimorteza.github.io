<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Git Script</span>](Git.md)
[Basic](Git-Basic.md) | 
[Structure](Git-Structure.md) | 
[Script](Git-Script.md)


<div class="md3"></div>
<a href="#Config">Config</a> - 
<a href="#git-ignore">Git Ignore</a> - 
<a href="#gitlab-add-ssh-key">Add ssh key</a> -
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

    git config --global user.email "kashani.morteza@gmail.com"      
    git config --global user.name "morteza"

#### Color highlighting

    git config --global color.ui true
    git config --global color.status auto
    git config --global color.branch auto

#### Setting default editor
    
    git config --global core.editor vim

#### Setting default merge tool

    git config --global merge.tool vimdiff

#### Listing Git settings
    
    git config --list    







<div class="md0"></div>

## Git Ignore
| Command | Explain |
| ------ | ------ |
| touch .gitignore | <span align="right" dir="rtl"> اول یک فایل میسازیم  <span>  |
| videos/ <br> sound/1.mp3 <br> *.dll <br> !myfolder/m.dll | <span align="right" dir="rtl"> آدرس فایل ها رو قرار می دهیم <span>  |







<div class="md0"></div>

## Gitlab Add ssh key

    ssh -V
    cd /home/morteza/.ssh/
    ssh-keygen -t rsa -b 2048 -C "kashani.morteza@gmail.com"
    add thes address : /home/morteza/.ssh/gitlab

    cat /home/morteza/.ssh/gitlab.pub
    copy code and paste to gitlab : Settings > SSH Keys

    ssh -T git@gitlab.com
    
    vim /home/morteza/.ssh/config     
    Host kashani.morteza.gitlab.com
     Preferredauthentications publickey
     IdentityFile ~/.ssh/gitlab





<div class="md0"></div>

## Basic command

| Command | Explain |
| ------ | ------ |
| git init | <span align="right" dir="rtl"> اول باید به گیت گفت این پوشه رو تحت مدیریت خودت قرار بده <span>  |
| git status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| vim test.text | <span align="right" dir="rtl"> لایه اول : ساخت فایل test.txt <span>  |
| git status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| git add test.txt | <span align="right" dir="rtl"> لایه دوم : بردن فایل به لایه دوم (Stage) <span>  |
| git status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| git commit ‘first commit’ | <span align="right" dir="rtl"> لایه سوم : ثبت همه تغییرات <span>  |
| git status | <span align="right" dir="rtl"> پوشه در چه وضعیتی هست <span>  |
| git log | <span align="right" dir="rtl"> گزارش کامیت ها <span>  |






<div class="md0"></div>

## Start a working area

#### init

| Command | Explain |
| ------ | ------ |
| git init | <span align="right" dir="rtl"> شروع پروژه <span>  |
| git clone https://github.com/atom/atom.git | <span align="right" dir="rtl"> دانلود و شروع پروژه <span>  |

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
| git diff head | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه سوم (head) <span>  |
| git add test.txt | <span align="right" dir="rtl"> بردن فایل به لایه دوم (Stage) <span>  |
| git diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |
| vim test.text | <span align="right" dir="rtl"> یه تغییراتی در فایل میدهیم <span>  |
| git diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |


####  grep

#### log

| Command | Explain |
| ------ | ------ |
| git log | <span align="right" dir="rtl"> لیست commit های انجام شده را نشان می دهد <span>  |
| stash | <span align="right" dir="rtl"> میتونی چندین استش درست کنی و فایل ها رو که تغییر میدی داخلش نگه داری<br> و هر وقت دوست داشتی برشون گردونی به work directory <span>  |

#### show

#### status    








<div class="md0"></div>

## grow, mark and tweak your common history

#### branch

| Command | Explain |
| ------ | ------ |
| git branch | <span align="right" dir="rtl"> لیست branch <span>  |
| git checkout –b dev | <span align="right" dir="rtl"> ساخت branch <span>  |
| git checkout dev | <span align="right" dir="rtl"> سوئیچ به branch <span>  |
| git branch –d dev | <span align="right" dir="rtl"> حذف branch <span>  |
| git merge dev | <span align="right" dir="rtl"> یکی کردن branch <span>  |

#### commit

#### merge

#### rebase

#### reset

| Command | Explain |
| ------ | ------ |
| git reset test.txt | <span align="right" dir="rtl"> برگشت از stage به work directory <span>  |
| git checkout -- test.txt | <span align="right" dir="rtl"> برگشت از head به work directory <span>  |
| git reset hash code | <span align="right" dir="rtl"> برگشت از commit به work directory <span>  |

#### switch

#### tag

| Command | Explain |
| ------ | ------ |
| Git tag | <span align="right" dir="rtl"> لیست تگ ها رو نشون میده <span>  |
| Git tag –a v.a | <span align="right" dir="rtl">  <span>  |
| Git push origin --tags | <span align="right" dir="rtl">  <span>  |
| Git tag | <span align="right" dir="rtl">  <span>  |








<div class="md0"></div>

## Collaborate

#### fetch

#### pull

#### push

#### remote

| Command | Explain |
| ------ | ------ |
| Git clone [url] | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Git remote add origin [url]  | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Git push Origin master  | <span align="right" dir="rtl"> یعنی اطلاعات رو بفرست به ریموت <span>  |
| Git pull Origin master  | <span align="right" dir="rtl"> اطلاعات رو از ریپازیتوری بگیر <span>  |






	Git global setup
	git config --global user.name "morteza kashani"
	git config --global user.email "kashani.morteza@gmail.com"

	Create a new repository
	git clone git@gitlab.com:kashani.morteza/morteza.git
	cd morteza
	touch README.md
	git add README.md
	git commit -m "add README"
	git push -u origin master

	Push an existing folder
	cd existing_folder
	git init
	git remote add origin git@gitlab.com:kashani.morteza/morteza.git
	git add .
	git commit -m "Initial commit"
	git push -u origin master

	Push an existing Git repository
	cd existing_repo
	git remote rename origin old-origin
	git remote add origin git@gitlab.com:kashani.morteza/morteza.git
	git push -u origin --all
	git push -u origin --tags