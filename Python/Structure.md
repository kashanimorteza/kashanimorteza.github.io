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

# [<span style="color:black;">Structure</span>](Index.md)

<div class="md3"></div>

[Basic](Basic.md) |
[Structure](Structure.md) | 
[Script](Script.md) | 
[Script](Flask.md)

<div class="md3">
<a href="#data-type" >Data Type</a> - 
<a href="#Variable" >Variable</a> - 
<a href="#data-structures" >Data structures</a> - 
<a href="#Operators">Operators</a> - 
<a href="#Conditions">Conditions</a> - 
<a href="#loop">Loop</a> - 
<a href="#function" >Function</a> -
<a href="#module">Module</a> -
<a href="#API">API</a> -
<a href="#Database">Database</a> -
<a href="#Error">Error</a>
<div class="md4"></div>
<a href="#oop" >OOP</a> -
<a href="#Iterator">Iterator</a> - 
<a href="#Generator">Generator</a> - 
<a href="#decorator">Decorator</a> -
<a href="#Example">Example</a>
<div class="md4"></div>
<a href="#socket">Socket</a> -
<a href="#multi-processing">Multi Processing</a> -
<a href="#multi-threading">Multi Threading</a> - 
<a href="#syncasync">Sync/Async</a>
</div>





## Diagram

<div class="md1">

![](Diagram/Programming.jpeg)

</div>








<div class="md1"></div>

## Data types
#### String
#### Numeric : Integer , Float 
#### Boolean
#### Complex
#### Binary
#### Convert Data Type







<div class="md0"></div>

## Variable

#### Variable Assignment

#### Name mangling 









<div class="md0"></div>

## Data structures 

#### List	

#### Dictionary

#### Tuple	

<div align="right" dir="rtl">
بعد از پیاده سازی دیگر قابل تغییر نیستند
<br><br>
سرعت بسیار بیشتری از لیست دارد
</div>

#### Set

<div align="right" dir="rtl">
آیتم تکراری نمی پذیرد و همچنین ترتیب ندارد و دسترسی بر اساس index امکانپذیر نیست 
</div>

#### Range

#### frozenset	
	
	
	







<div class="md0"></div>

## Operators 
#### Arithmetic 
#### Comparison
#### Logical 
#### Assignment 
#### Bitwise 
#### Ternary








<div class="md0"></div>

## Conditions  
#### IF Statement
#### Expression
#### Truthiness and Falsiness








<div class="md0"></div>

## Loop 
#### For
#### While








<div class="md0"></div>

## Function 
#### normal function
#### function With Return Value	
#### function With parameters	
#### function With Default parameter values	
#### function With Definition parameters
#### function With dynamic parameters
#### Anonymous functions(lambda)
#### Built-in function(Map, filter, all, any, sort, reversed, max-min , Len , Abs , Sum و Round , zip)

<div align="right" dir="rtl">
اگر در ورودی فانکشن از args* استفاده کنیم یعنی مهم نیست فانکشن رو با یک ورودی صدا کردی یا 100 تا
<br><br>
اگر در ورودی فانکشن از kwarg* استفاده کنیم تمام ورودی را بصورت یک دیکشنری می گیرد
</div>











<div class="md0"></div>

## OOP
#### Abstraction
#### Encapsulation
#### Class, Object
#### Method, Constructor
#### Attribute, Property , Setter  , Getter
#### Inheritance , Super , multiple inheritance, Method resolution order
#### Polymorphisms









<div class="md0"></div>

## Iterator
<div align="right" dir="rtl">
پیاده سازی این مفهوم برای پیمایش دیتا کاربرد دارد
<br><br>
حلقه های تکرار از همین مفهوم استفاده می کنند
<br><br>
با پیاده سازی این مفهوم میتوانیم بر روی کلاس های خود با حلقه های تکرار پیمایش کنیم
<br><br>
مناسب برای کار با big data
<br><br>
<span style="color:blue">Iterable :</span> کلاس هایی مثل List که امان اضافه کردن آیتم را دارند 
<br><br>
<span style="color:blue">Iterator :</span> کلاسی که با متد()iter قابل پیمایش  شده است 
<br><br>
<span style="color:blue">Iterate :</span> هر یک از آیتم ها که پیمایش می شود 
<br><br>
با متد ()iter کلاس های Iterable تبدیل به Iterator می شوند
<br><br>
آیتم های یک Iterator با متد ()next پیمایش می شوند
</div>











<div class="md0"></div>

## Generator
<div align="right" dir="rtl">
هر Generator یک Iterator است
<br><br> 
میتوان متد هایی ایجاد کرد که استیت متد نگه داشته شود و با اجرای هر بار متد ()next استیت تغییر کند
<br><br>
برای کار با دیتاهای عظیم و امثالی مثل فیبوناچی با این روش خیلی بهتر انجام میشه
<br><br>
یک فانکشن معمولی که به جای return از yield استفاده می شود
</div>














## Decorator

<div class="md1">
<div align="right" dir="rtl">
 پیاده سازی این مفهوم این امکان را به ما می دهد که ماهیت یک فانکشن را تغییر و توسعه بدهیم
 <br><br>
 decorator تابعی است، که تابع دیگر را دریافت می‌کند و رفتار آن را تغییر می‌دهد 
</div>
</div>




## Socket

<div class="md1">

</div>





## Multi Processing

<div class="md1">

</div>





## Multi-Threading

<div class="md1">

</div>







## Sync/Async

<div class="md1">

Blocking 

Non Blocking

<div class="md1" align="right" dir="rtl">
یک تابع آسنکرون در داخل پایتون Coroutine نامیده میشه

این دو، توابع خاصی هستن که وقتی صدا زده بشن آبجکتی به نام coroutine object رو بر می گردونن

</div>


process
thread
task


## Socket

<div class="md1">


</div>






## Error

<div class="md0">

#### Debugging

#### Return raise

#### try except

</div>












## API

<div class="md0">

pip install request

</div>
