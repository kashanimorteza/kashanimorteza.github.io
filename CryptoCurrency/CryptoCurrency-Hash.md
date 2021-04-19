<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C}
.blue{color:#3498DB}
.green{color:##28B463}
</style>


# [<span style="color:black;">Crypto Currency Hash</span>](file:./CryptoCurrency.md)
[Diagram](CryptoCurrency-Diagram.md) | 
[Bitcoin](CryptoCurrency-Bitcoin.md) |
[Hash](CryptoCurrency-Hash.md) |
[Signature](CryptoCurrency-Signature.md) |
[Blockchain](CryptoCurrency-Blockchain.md) |
[Ethereum](CryptoCurrency-Ethereum.md)


<div class="md3"></div>
<a href="#diagram">Diagram</a> - 
<a href="#resource">Resource</a> - 
<a href="#structure">Structure</a> - 
<a href="#concept">Concept</a> - 
<a href="#libreary">Libreary</a> - 
<a href="#command">Command</a> - 
<a href="#script">Script</a> - 
<a href="#question">Question</a> - 








<div class="md1"></div>

## Diagram

![](Diagram/CryptoCurrency-Hashing.jpeg)






<div class="md1"></div>

## Resource

hash break website




<div class="md0"></div>

## Structure

Function 



<div class="md0"></div>

## Concept

#### <span class="red">General</span>

<div align="right" dir="rtl">
<span>یک تابع که یک ورودی بگیرد و همیشه یک خرجی ثابت بابت این ورودی بدهد</span>
<div class="md4"></div>
<span>چون خروجی‌ ثابت است و ورودی بی‌ نهایت، پس ۱۰۰ درصد ورودی‌های مختلف با خروجی یکسان خواهیم داشت، اما خروجی‌ اینقدر بزرگ که این مساله اصلا مهم نیست</span>
</div>

#### <span class="red">Properties</span>

Free input size

Specific output length

Efficiency computed

Collision resistance
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<span>نتونن ورودی رو جوری تغییر بدن که به هش مورد نظرشون برسن</span>


Hiding
&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;
<span>نباید از هش به دیتا برسم</span>


Puzzle friendliness
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<span>خیلی سریع تولید نشه</span>


#### <span class="red">Salt</span>




<div class="md0"></div>

## Libreary

sha256





<div class="md0"></div>

## Command

    echo hello | sha256sum




<div class="md0"></div>

## Script

    import hashlib

    for i in range(1,1000000):

        data='my name is jadi and my 123456 is my student number. ' + str(i)
        m = hashlib.sha256()
        m.update(data.encode('utf-8'))
        hash = m.hexdigest()

        if hash[-4:] == "1111" :
            print('found it ',i, data)
            break




<div class="md0"></div>

## Question

1 -
<br>
2 - 
<br>
3 - 
<br>
4 - 
<br>
5 - 