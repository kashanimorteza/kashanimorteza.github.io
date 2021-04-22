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

# [<span style="color:black;">Crypto Currency Encryption </span>](CryptoCurrency.md)
[Diagram](CryptoCurrency-Diagram.md) | 
[Bitcoin](CryptoCurrency-Bitcoin.md) |
[Hash](CryptoCurrency-Hash.md) |
[Encryption](CryptoCurrency-Encryption.md) |
[Blockchain](CryptoCurrency-Blockchain.md) |
[Ethereum](CryptoCurrency-Ethereum.md)

<div class="md3"></div>
<a href="#diagram">Diagram</a> - 
<a href="#resource">Resource</a> - 
<a href="#method">Method</a> - 
<a href="#algorithm">Algorithm</a> - 
<a href="#structure">Structure</a> - 
<a href="#libreary">Libreary</a> - 
<a href="#command">Command</a> - 
<a href="#note">Note</a> - 
<a href="#question">Question</a> 


<div class="md3"></div>

## Diagram

![](Diagram/CryptoCurrency-Encryption.jpeg)






<div class="md1"></div>

## Resource

#### General

<a href="https://en.wikipedia.org/wiki/Pretty_Good_Privacy" target="_blank">PGP</a> - 
<a href="https://www.openpgp.org/" target="_blank">OpenPGP</a> - 
<a href="https://gnupg.org/" target="_blank">GnuPG</a>

#### Tutorial

<a href="https://www.devdungeon.com/content/gpg-tutorial" target="_blank">devdungeon</a>




<div class="md0"></div>

## Method

Symmetric

Asymmetric




<div class="md0"></div>

## Algorithm

Triple DES

RSA

AES

ECDSA








<div class="md0"></div>

## Structure

#### <span class="red">Key</span>

Private Key

Public Key

Revoke Key

<div class="md3"></div>

#### <span class="red">Action</span>

Encrypt

Decrypt

Sign

Revoke 










<div class="md0"></div>

## Libreary

PGP

OpenPGP

GnuPG 






<div class="md0"></div>

## Command

#### Generate

    gpg --full-generate-key

#### List
    gpg --list-keys
    gpg --list-secret-keys


#### Delete

    gpg --delete-key morteza
    gpg --delete-secret-key morteza


#### Import

    gpg --import public_key
    gpg --import private_key


#### Export

    gpg --export morteza > public_key
    gpg --export --armor morteza > public_key.asc

    gpg --export-secret-keys morteza > private_key
    gpg --export-secret-keys --armor morteza > private_key.asc


#### Encrypted / Decrypted

    gpg --out file.encrypted --recipient morteza --encrypt file.original
    gpg --out file.decrypted --decrypt file.encrypted


#### Signature
    gpg --local-user morteza --detach-sign --sign --armor --output file.sign file.original
    gpg --verify file.sign file.original
    

#### Revoke

    gpg --out file.revoke --gen-revoke morteza


<div class="md0"></div>

## Note

<div align="right" dir="rtl">

#### <div class="red"><span>روش</span> : <span>Method</span></div>

<div class="blue"><span>متقارن</span> : <span>Symmetric</span></div>
<div class="md4"></div>
<div> در این روش برای رمز کردن اطلاعات و همچنین باز کردن اطلاعات از یک کلید استفاده می‌‌شود</div>
<div class="md4"></div>
<div class="blue"><span>نامتقارن</span> : <span>Asymmetric</span></div>
<div class="md4"></div>
<div>در این روش از یک کلید برای رمز کردن اطلاعات و از یک کلید دیگر برای باز کردن اطلاعات استفاده می‌‌شود </div>

<div class="md2"></div>

#### <div class="red"><span>Algorithm</span> : <span>RSA</span></div>
<div class="md4"></div>
<div class="blue"><span>رمزنگاری</span> : <span>Encryption</span></div>
<div class="md4"></div>
<div >در این سیستم ما ۲ تا کلید داریم، یکی‌ برای رمزنگاری اطلاعات(Public Key) و یکی‌ برای رمزگشایی اطلاعات (Private Key)</div>
<div class="md3"></div>
<div>فرض کنید ۵ نفر می‌خواهد برای ما به صورت رمزشده اطلاعاتی‌ بفرستند، باید چی‌ کار کنیم ؟</div>
<div>ما (Public Key) را در اختیار همهٔ آنها  قرار میدهیم و آنها با (Public Key) اطلاعاتی‌ را رمزنگاری می‌‌کنند، اطلاعات رمز شده را فقط کسی‌ میتواند رمزگشایی کند که (Private Key) را در اختیار داشته باشد و اون شخص کسی‌ نیست جز خود ما </div>
<div class="md4"></div>
<div>حالا از کجا بفهمیم که هر پیغام برای چه کسی‌ است ؟</div>
<div></div>
<div></div>
<div></div>
<div></div>

<div class="md33"></div>

<div class="blue"><span>امضا</span> : <span>Signature</span></div>
<div class="md4"></div>
<div >
حالا اگر هر کسی‌ بتونه پیغام خودش رو امضا کنه و ما بتونیم امضای هر کسی‌ رو برسی‌ کنیم، میتونیم بفهمیم هر پیغام برای چه کسی‌ هست
پس با استفاده از یک فانکشن که Private_key و Data رو به عنوان ورودی میگیره و یک امضا برای اون دیتا درست می‌کنه، می‌تونیم دیتای خود را امضا کنیم و امضا رو در اختیار دیگران قرار می دهیم تا بررسی کنن اطلاعاتی که بدستشون میرسه از طرف ما هست یا نه
</div>
<div><span>اینجوری امضا می کنیم : </span><span>MySign = Sign(private_key, data)</span></div>
<div><span>اینجوری امضا رو چک می کنیم : </span><span>ValidateSign = Validate(public_key, MySign, data )</span></div>
<div></div>
<div></div>
<div></div>

</div>



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