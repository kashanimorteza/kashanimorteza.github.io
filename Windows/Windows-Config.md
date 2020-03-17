<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Windows Config</span>](Windows.md)
[Config](Windows-Config.md) | [Script](Windows-Script.md) 

<div class="md1"></div>

## Create Windows Bootable Disk
    open cmd run as administrator 
	------------------------
    diskpart
    select disk 1
    clean
	convert gpt
	select partition 1
	delete partition override
	------
	CREATE PARTITION PRIMARY SIZE=1
	format quick fs=fat32
	assign letter=s
	------
    CREATE PARTITION PRIMARY SIZE=6144    
    format quick fs=ntfs
	assign letter=w
	-------
	exit	
	------
    extract windows image to partition i
	copy efi folder fro, rufus to s partition
    ------
	for mbr partition table
    open cmd with administrator 
    i:
    cd boot 
    bootsect.exe /nt60 i: /force
	------
    restart computer and boot from hard disk

<div class="md1"></div>

## Windows Startup Repair
    bootrec /fixmbr
    bootrec /fixboot
    --- or ---
    bootsect.exe /nt60 i: /force
    --- or ---
    diskpart
    select disc 1
    active
	
	

<div class="md1"></div>	
	
## Create EFI Partitions
	open cmd run as administrator 
	-----------------------------
    diskpart	
	list disk
    select disk X
	------
    clean
	convert gpt
	select partition 1
	delete partition override
	------
	CREATE PARTITION PRIMARY SIZE=50
	format quick label=UEFI fs=fat32
	assign letter=m
	------
	Copy EFI folder from linux iso file to this partition
