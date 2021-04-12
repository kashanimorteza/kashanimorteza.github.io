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


# [<span style="color:black;">Crypto Currency Encryption</span>](file:./CryptoCurrency.md)
[Diagram](CryptoCurrency-Diagram.md) | 
[Basic](CryptoCurrency-Basic.md) |
[Hash](CryptoCurrency-Hash.md) |
[Encryption](CryptoCurrency-Encryption.md) |
[Blockchain](CryptoCurrency-Blockchain.md)


<div class="md3"></div>
<a href="#resource">Resource</a> - 
<a href="#idioms">Idioms</a> - 
<a href="#structure">Structure</a> - 
<a href="#libreary">Libreary</a> - 
<a href="#command">Command</a> - 
<a href="#question">Question</a> - 







<div class="md1"></div>

## Resource

<a href="https://www.openpgp.org/" target="_blank">openpgp</a> - 
<a href="https://gnupg.org/" target="_blank">gnupg</a> - 







<div class="md0"></div>

## Idioms

Symmetric

Private Key / Public Key







<div class="md0"></div>

## Structure

Private Key

Public Key

Revoke Key

Encrypt

Decrypt

Signature










<div class="md0"></div>

## Libreary

OpenPGP

GnuPG 






<div class="md0"></div>

## Command

#### Generate Key

    gpg --gen-key

#### Export Public Key

    gpg --export kashani.morteza@gmail.com > morteza_public_key

#### Export Revoke
    gpg --out morteza_revoke.asc --gen-revoke kashani.morteza@gmail.com

#### Encrypt data

    gpg --out my_msg_encrypted --recipient kashani.morteza@gmail.com --encrypt my_msg_original

#### Import Public Key

    gpg --import morteza_public_key

#### Decrypt data

    gpg --out my_msg_unencrypted --decrypt my_msg_encrypted
    
#### Signature

    gpg --clearsign my_sign
    gpg --verify my_sign.asc




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