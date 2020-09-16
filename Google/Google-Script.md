<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Google Script</span>](Google.md)
[Basic](Google-Basic.md) | 
[Product](Google-Product.md) | 
[Script](Google-Script.md)


<div class="md3"></div>
<a href="#SDK" >SDK</a> - 
<a href="#compute-engine" >Compute Engine</a> - 
<a href="#app-engine">App Engine</a>






<div class="md1"></div>

## Cloud SDK 

#### Update components

    gcloud components update

#### Login 

    gcloud auth login
	
#### Set Project	

    gcloud config set project light-trail-276918 






<div class="md0"></div>

## Compute Engine

#### Instances list
	 
	 gcloud compute instances list
	 
#### Connect to Instances with Cloud SDK 
	
	gcloud compute ssh linux1
		
#### Connect to Instances with SSH
	
	Download PuTTYgen

	Run PuTTYgen and Generate
		Key comment : morteza
		Key passphrase : Morteza123456
		Confirm passphrase : Morteza123456	
	Save public key as : public_key
	Save Private key as : private_key.ppk

	Run PuTTYgen and load private_key.ppk
	copy code from top
	Go to Google cloud Console > Compute Engine > VM Instance > Select Instance
	In instance page go to edit
	finde "You have 0 SSH key" Option and go inside and paste the code
	save changes	 

	Open putty	
	Add path of private_key.ppk into connection > ssh > auth > private key for authentication 
	






<div class="md0"></div>

## App Engine