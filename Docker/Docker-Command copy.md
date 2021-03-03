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

<table class="tbl1"><tbody>
<tr>
<td align="center" id="header">Command</td>
<td align="center" id="header">Example</td>
<td align="center" id="header">Description</td>
</tr>
<tr>
<td align="center">builder</td>
<td align="center">aaa</td>
<td align="center">Manage builds</td>
</tr>
<tr>
<td align="center">config</td>
<td align="center">aaa</td>
<td align="center">Manage Docker configs</td>
</tr>
<tr>
<td align="center">container</td>
<td align="center">aaa</td>
<td align="center">Manage containers</td>
</tr>
<tr>
<td align="center">context</td>
<td align="center">aaa</td>
<td align="center">Manage contexts</td>
</tr>
<tr>
<td align="center">engine</td>
<td align="center">aaa</td>
<td align="center">Manage the docker engine</td>
</tr>
<tr>
<td align="center">network</td>
<td align="center">aaa</td>
<td align="center">Manage networks</td>
</tr>
<tr>
<td align="center">Image</td>
<td align="center">docker images</td>
<td align="center">Manage images</td>
</tr>
<tr>
<td align="center">node</td>
<td align="center">aaa</td>
<td align="center">Manage Swarm nodes</td>
</tr>
<tr>
<td align="center">plugin</td>
<td align="center">aaa</td>
<td align="center">Manage plugins</td>
</tr>
<tr>
<td align="center">secret</td>
<td align="center">aaa</td>
<td align="center">Manage Docker secrets</td>
</tr>
<tr>
<td align="center">service</td>
<td align="center">aaa</td>
<td align="center">Manage services</td>
</tr>
<tr>
<td align="center">stack</td>
<td align="center">aaa</td>
<td align="center">Manage Docker stacks</td>
</tr>
<tr>
<td align="center">swarm</td>
<td align="center">aaa</td>
<td align="center">Manage Swarm</td>
</tr>
<tr>
<td align="center">system</td>
<td align="center">aaa</td>
<td align="center">Manage Docker</td>
</tr>
<tr>
<td align="center">trust</td>
<td align="center">aaa</td>
<td align="center">Manage trust on Docker images</td>
</tr>
<tr>
<td align="center">volume</td>
<td align="center">aaa</td>
<td align="center">Manage volumes</td>
</tr>
</tbody></table>



#### container
    qqqq


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
<td align="center">docker version</td>
<td align="center">ورژن داکر را نمایش می دهد</td>
</tr>
<tr>
<td align="center">help</td>
<td align="center">docker help</td>
<td align="center">داکیومنت داکر را نشان می  دهد</td>
</tr>
<tr>
<td align="center">prune</td>
<td align="center">docker container prune</td>
<td align="center">تمام کانتینرهای خارج شده را حذف می کند </td>
</tr>
<tr>
<td align="center">rmi</td>
<td align="center">docker rmi hello-world</td>
<td align="center">ایمیج مورد نظر را حذف می کند</td>
</tr>
<tr>
<td align="center">ps</td>
<td align="center">docker ps</td>
<td align="center">کانتینر هایی که فعال هستند را نشان می دهد</td>
</tr>
<tr>
<td align="center">images</td>
<td align="center">docker images</td>
<td align="center">ایمیج های موجود را نشان می دهد</td>
</tr>
<tr>
<td align="center">pull</td>
<td align="center">docker pull ubuntu</td>
<td align="center">برای دانلود ایمیج ها استفاده می شود</td>
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












