<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Windows Config</span>](Windows.md)
[Config](Windows-Config.md)

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
	assign letter=i	
	-------
	exit	
	------
    extract windows image to partition i
	copy efi folder fro, rufus to s partition
    ------
	for mbr system
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
