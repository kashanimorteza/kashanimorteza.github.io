# [<span style="color:black;">Git Structure</span>](file:./0-Git.md)
[Basic](file:./1-Git-Basic.md) | [Structure](file:./2-Git-Structure.md) | [Example](file:./3-Git-Example.md) 

<br>

## Getting and Creating Projects
| Command | Explain |
| ------ | ------ |
| git init | <span align="right" dir="rtl"> شروع پروژه <span>  |
| git clone https://github.com/atom/atom.git | <span align="right" dir="rtl"> دانلود و شروع پروژه <span>  |


<br><br>
## Basic
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


<br><br>
## Difference
| Command | Explain |
| ------ | ------ |
| vim test.text | <span align="right" dir="rtl"> یه تغییراتی در فایل میدهیم <span>  |
| git diff head | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه سوم (head) <span>  |
| git add test.txt | <span align="right" dir="rtl"> بردن فایل به لایه دوم (Stage) <span>  |
| git diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |
| vim test.text | <span align="right" dir="rtl"> یه تغییراتی در فایل میدهیم <span>  |
| git diff --staged | <span align="right" dir="rtl"> تفاوت محتوای فایل در لایه اول (working directory) با لایه دوم (stage) <span>  |


<br><br>
## Return
| Command | Explain |
| ------ | ------ |
| git reset test.txt | <span align="right" dir="rtl"> برگشت از stage به work directory <span>  |
| git checkout -- test.txt | <span align="right" dir="rtl"> برگشت از head به work directory <span>  |
| git reset hash code | <span align="right" dir="rtl"> برگشت از commit به work directory <span>  |


<br><br>
## Branch & Merge
| Command | Explain |
| ------ | ------ |
| git branch | <span align="right" dir="rtl"> لیست branch <span>  |
| git checkout –b dev | <span align="right" dir="rtl"> ساخت branch <span>  |
| git checkout dev | <span align="right" dir="rtl"> سوئیچ به branch <span>  |
| git branch –d dev | <span align="right" dir="rtl"> حذف branch <span>  |
| git merge dev | <span align="right" dir="rtl"> یکی کردن branch <span>  |


<br><br>
## Log
| Command | Explain |
| ------ | ------ |
| git log | <span align="right" dir="rtl"> لیست commit های انجام شده را نشان می دهد <span>  |
| stash | <span align="right" dir="rtl"> میتونی چندین استش درست کنی و فایل ها رو که تغییر میدی داخلش نگه داری<br> و هر وقت دوست داشتی برشون گردونی به work directory <span>  |


<br><br>
## Git Ignore
| Command | Explain |
| ------ | ------ |
| touch .gitignore | <span align="right" dir="rtl"> اول یک فایل میسازیم  <span>  |
| videos/ <br> sound/1.mp3 <br> *.dll <br> !myfolder/m.dll | <span align="right" dir="rtl"> آدرس فایل ها رو قرار می دهیم <span>  |


<br><br>
## Remote
| Command | Explain |
| ------ | ------ |
| Git clone [url] | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Git remote add origin [url]  | <span align="right" dir="rtl"> گرفتن یک ریپازیتوری از ریموت <span>  |
| Git push Origin master  | <span align="right" dir="rtl"> یعنی اطلاعات رو بفرست به ریموت <span>  |
| Git pull Origin master  | <span align="right" dir="rtl"> اطلاعات رو از ریپازیتوری بگیر <span>  |


<br><br>
## Tag
| Command | Explain |
| ------ | ------ |
| Git tag | <span align="right" dir="rtl"> لیست تگ ها رو نشون میده <span>  |
| Git tag –a v.a | <span align="right" dir="rtl">  <span>  |
| Git push origin --tags | <span align="right" dir="rtl">  <span>  |
| Git tag | <span align="right" dir="rtl">  <span>  |