<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Python Structure</span>](Python.md)
[Basic](Python-Basic.md) |
[Structure](Python-Structure.md) | 
[Script](Python-Script.md)


<div class="md3"></div>
<a href="#data-types">Data types</a> - 
<a href="#Variable">Variable</a> - 
<a href="#data-structures">Data structures</a> - 
<a href="#Operators">Operators</a> - 
<a href="#Conditions">Conditions</a> - 
<a href="#loop">Loop</a> - 
<a href="#Function">Function</a> - 
<a href="#OOP">OOP</a>
<a href="#Iterator">Iterator</a> - 
<a href="#Generator">Generator</a> - 
<a href="#decorator">Decorator</a>









<div class="md1"></div>

## Data types
#### Text
#### Numeric
#### Boolean
#### Binary
#### Complex







<div class="md0"></div>

## Variable
#### Name mangling 









<div class="md0"></div>

## Data structures 
#### List	
#### Tuple	
#### Range
#### Dictionary
#### set
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












<div class="md0"></div>

## Decorator

<div align="right" dir="rtl">
 پیاده سازی این مفهوم این امکان را به ما می دهد که ماهیت یک فانکشن را تغییر و توسعه بدهیم
 <br><br>
 decorator تابعی است، که تابع دیگر را دریافت می‌کند و رفتار آن را تغییر می‌دهد 
</div>
