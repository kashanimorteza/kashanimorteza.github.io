<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Docker Command</span>](Docker.md)
[Basic](Docker-Basic.md) | 
[Structure](Docker-Structure.md) | 
[Command](Docker-Command.md) |
[Script](Docker-Script.md)


<div class="md3"></div>
<a href="#manage">Manage</a> - 
<a href="#general">General</a> - 
<a href="#dockerfile">Dockerfile</a>




<div class="md1"></div>

## Manage

#### builder

#### config

#### container

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center">prune</td>
<td align="left">docker container prune</td>
<td align="center">تمام کانتینرهای خارج شده را حذف می کند </td>
</tr>
</tbody></table>

#### context

#### engine

#### image

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center" rowspan="10">ls</td>
<td align="left">docker image ls</td>
<td align="center">ایمیج های موجود را نشان می دهد</td>
</tr>
<tr>
<td align="left">docker image ls --filter dangling=true</td>
<td align="center">ایمیج هایی که تگ ندارند را نشان می دهد</td>
</tr>
<tr>
<td align="left">docker image ls --filter reference="*:latest"</td>
<td align="center">ایمیج هایی که تگ  لیتست هستند را نشان می دهد</td>
</tr>
<tr>
<td align="left">docker image ls --format "{{.Size}}"</td>
<td align="center">با این فرمت نشان بده</td>
</tr>
<tr>
<td align="left">docker image ls --format "{{.Repository}} {{.Size}}"</td>
<td align="center">با این فرمت نشان بده</td>
</tr>
</tbody></table>

#### network


<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center"></td>
<td align="left">docker network</td>
<td align="center">لیست دستورات را بر می گرداند</td>
</tr>
<tr>
<td align="center">create</td>
<td align="left">docker network create test</td>
<td align="center">یک شبکه می سازد</td>
</tr>
<tr>
<td align="center">ls</td>
<td align="left">docker network ls</td>
<td align="center">لیست شبکه ها را نشان می دهد</td>
</tr>
<tr>
<td align="center">inspect</td>
<td align="left">docker network inspect test</td>
<td align="center">اطلاعات جزیی از  شبکه را نشان می دهد</td>
</tr>
<tr>
<td align="center">rm</td>
<td align="left">docker network rm test</td>
<td align="center">شبکه را حذف می کند</td>
</tr>
<tr>
<td align="center">prune</td>
<td align="left">docker network prune</td>
<td align="center">تمام شبکه ها را پاک می کند</td>
</tr>
</tbody></table>


#### node

#### plugin

#### secret

#### service

#### stack

#### swarm

#### system

#### trust

#### volume

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center">create</td>
<td align="left">docker volume create test</td>
<td align="center">یک والیوم می سازد</td>
</tr>
<tr>
<td align="center">ls</td>
<td align="left">docker volume ls</td>
<td align="center">لیست والیوم ها را نشان می دهد</td>
</tr>
<tr>
<td align="center">inspect</td>
<td align="left">docker volume inspect test</td>
<td align="center">اطلاعات جزیی از  والیوم را نشان می دهد</td>
</tr>
<tr>
<td align="center">rm</td>
<td align="left">docker volume rm test</td>
<td align="center">والیوم را حذف می کند</td>
</tr>
<tr>
<td align="center">prune</td>
<td align="left">docker volume prune</td>
<td align="center">تمام والیوم ها را پاک می کند</td>
</tr>
</tbody></table>






<div class="md0"></div>

## General

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center">version</td>
<td align="left">docker version</td>
<td align="center">ورژن داکر را نمایش می دهد</td>
</tr>
<tr>
<td align="center">help</td>
<td align="left">docker help</td>
<td align="center">داکیومنت داکر را نشان می  دهد</td>
</tr>
<tr>
<td align="center">info</td>
<td align="left">docker info naughty_austin</td>
<td align="center">یک سری اطلاعات در مورد داکر به ما می دهد</td>
</tr>
<tr>
<td align="center">create</td>
<td align="left">docker create ubuntu</td>
<td align="center">کانتینر را میسازد</td>
</tr>
<tr>
<td align="center">start</td>
<td align="left">docker start ubuntu</td>
<td align="center">کانتینر را استارت می کند</td>
</tr>
<tr>
<td align="center">kill</td>
<td align="left">docker kill naughty_austin</td>
<td align="center">کانتینر را می کشد</td>
</tr>
<tr>
<td align="center">stop</td>
<td align="left">docker stop naughty_austin</td>
<td align="center">کانتینر را استوپ می کند</td>
</tr>
<tr>
<td align="center">pause</td>
<td align="left">docker pause naughty_austin</td>
<td align="center">کانتینر را نگه می دارد</td>
</tr>
<tr>
<td align="center">unpause</td>
<td align="left">docker unpause naughty_austin</td>
<td align="center">کانتینر را آزاد می کند</td>
</tr>
<tr>
<td align="center">restart</td>
<td align="left">docker restart naughty_austin</td>
<td align="center">کانتینر را راه اندازی مجدد می کند</td>
</tr>
<tr>
<td align="center">inspect</td>
<td align="left">docker inspect naughty_austin</td>
<td align="center">یک سری اطلاعات در مورد کانتینر به ما می دهد</td>
</tr>
<tr>
<td align="center">log</td>
<td align="left">docker log naughty_austin</td>
<td align="center">لاگ های داکر را به ما نشان می دهد</td>
</tr>
<tr>
<td align="center">exec</td>
<td align="left">docker exec -it ubuntu bash</td>
<td align="center">یک دستور را در کانتینر در حال اجرا، اجرا می کند</td>
</tr>
<tr>
<td align="center">images</td>
<td align="left">docker images</td>
<td align="center">ایمیج های موجود را نشان می دهد</td>
</tr>
<td align="center">rmi</td>
<td align="left">docker rmi hello-world</td>
<td align="center">ایمیج مورد نظر را حذف می کند</td>
</tr>
<tr>
<td align="center">pull</td>
<td align="left">docker pull ubuntu</td>
<td align="center">برای دانلود ایمیج ها استفاده می شود</td>
</tr>
<tr>
<td align="center">push</td>
<td align="left">docker push ubuntu</td>
<td align="center">برای ارسال ایمیج ها استفاده می شود</td>
</tr>
<tr>
<td align="center">login</td>
<td align="left">docker login --username=kashanimorteza</td>
<td align="center"></td>
</tr>
<tr>
<td align="center">search</td>
<td align="left">docker search fedora</td>
<td align="center"></td>
</tr>
<tr>
<td align="center">build</td>
<td align="left">docker build . -t myimage</td>
<td align="center"></td>
</tr>
</tbody></table>

<div class="md3"></div>
<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center" rowspan="100">ps</td>
<td align="left">docker ps</td>
<td align="center">کانتینرهای در حال اجرا را نشان می دهد</td>
</tr>
<tr>
<td align="left">docker ps -a</td>
<td align="center">تمام کانتینرهای ساخته شده را نشان می دهد</td>
</tr>
</tbody></table>

<div class="md3"></div>
<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center" rowspan="100">run</td>
<td align="left">docker run ubuntu</td>
<td align="center">کانتینر ساخته می شود و سپس اجرا می شود<br> و سپس از حالت اجرا خارج می شود</td>
</tr>
<tr>
<td align="left">docker run -it ubuntu</td>
<td align="center">میتوان با کانتینر صحبت کرد</td>
</tr>
<tr>
<td align="left">docker run -it -d ubuntu</td>
<td align="center">کانتینر در حالت اجرا باقی می ماند</td>
</tr>
<tr>
<td align="left">docker run -it -d -p 3306:3306 ubuntu</td>
<td align="center">پورت کانتینر را به بیرون وصل  می کند</td>
</tr>
</tbody></table>






<div class="md0"></div>

## Dockerfile 

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center">FROM</td>
<td align="center"><div>ubuntu</div></td>
<td align="center">یک ایمیج مبنا (والد) تعریف می‌کند</td>
</tr>
<tr>
<td align="center">LABEL</td>
<td align="center">aaaa</td>
<td align="center">متادیتا ارائه می‌کند و مکان مناسبی برای گنجاندن اطلاعات فراداده است</td>
</tr>
<tr>
<td align="center">ENV</td>
<td align="center">aaaa</td>
<td align="center">یک متغیر محیطی دائمی را تعیین می‌کند</td>
</tr>
<tr>
<td align="center">RUN</td>
<td align="center">aaaa</td>
<td align="center">یک دستور را اجرا می‌کند و یک لایه ایمیج ایجاد می‌کند<br> از آن برای نصب بسته‌ها درون کانتینرها استفاده می‌شود</td>
</tr>
<tr>
<td align="center">COPY</td>
<td align="center">aaaa</td>
<td align="center">همه فایل‌ها و دایرکتوری‌ها را به کانتینر کپی می‌کند</td>
</tr>
<tr>
<td align="center">ADD</td>
<td align="center">aaaa</td>
<td align="center">فایل‌ها و دایرکتوری‌ها را به کانتینر کپی می‌کند <br> می‌تواند فایل‌های محلی rar. را از حالت فشرده خارج کند</td>
</tr>
<tr>
<td align="center">CMD</td>
<td align="center">aaaa</td>
<td align="center">یک دستور و آرگومان‌هایی برای یک کانتینر اجرایی ارائه می‌کند<br> پارامترها می‌توانند لغو شوند. تنها یک CMD می‌تواند وجود داشته باشد</td>
</tr>
<tr>
<td align="center">WORKDIR</td>
<td align="center">aaaa</td>
<td align="center">دایرکتوری کاری برای دستورالعمل‌هایی که در ادامه می‌آید تعیین می‌شود</td>
</tr>
<tr>
<td align="center">ARG</td>
<td align="center">aaaa</td>
<td align="center">یک متغیر تعریف می‌کند که در زمان ساخت به داکر ارسال می‌شود</td>
</tr>
<tr>
<td align="center">ENTRYPOINT</td>
<td align="center">aaaa</td>
<td align="center">یک دستور و آرگومان‌هایی برای یک کانتینر اجرایی ارائه می‌کند. آرگومان‌ها دائمی هستند</td>
</tr>
<tr>
<td align="center">EXPOSE</td>
<td align="center">aaaa</td>
<td align="center">یک پورت را باز (افشا) می‌کند.</td>
</tr>
<tr>
<td align="center">VOLUME</td>
<td align="center">aaaa</td>
<td align="center">یک نقطه نصب دایرکتوری تعیین می‌کند که به داده‌های دائمی دسترسی دارد <br>و آن‌ها را ذخیره می‌کند</td>
</tr>
</tbody></table>












