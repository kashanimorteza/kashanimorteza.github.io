<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Windows Script</span>](Windows.md)
[Config](Windows-Config.md) | [Script](Windows-Script.md) 

<div class="md1"></div>

## Run Diskpart
	diskpart /s list.txt > log.txt


<div class="md1"></div>

## Create Partitions

	select disk 2
	clean
	convert gpt
	select partition 1
	delete partition override

	CREATE PARTITION PRIMARY SIZE=50
	format quick label=UEFI fs=fat32
	assign letter=m

	CREATE PARTITION PRIMARY SIZE=2300
	format quick label=Fedora-Server-ISO fs=ntfs
	assign letter=n

	CREATE PARTITION PRIMARY SIZE=2100
	format quick label=Fedora-Workstation-ISO fs=ntfs
	assign letter=p

	CREATE PARTITION PRIMARY SIZE=1600
	format quick label=Fedora-Xfce-ISO fs=ntfs
	assign letter=q

	CREATE PARTITION PRIMARY SIZE=7300
	format quick label=CentOS-ISO fs=ntfs
	assign letter=r

	CREATE PARTITION PRIMARY SIZE=2100
	format quick label=Ubuntu-ISO fs=ntfs
	assign letter=s

	CREATE PARTITION PRIMARY SIZE=1700
	format quick label=Ubuntu-Xfce-ISO fs=ntfs
	assign letter=t

	CREATE PARTITION PRIMARY SIZE=2000
	format quick label=Linux1 fs=ntfs
	assign letter=u

	CREATE PARTITION PRIMARY SIZE=2000
	format quick label=Linux2 fs=ntfs
	assign letter=v

	CREATE PARTITION PRIMARY SIZE=5900
	format quick label=Windows-10-ISO fs=ntfs
	assign letter=w
	
	

<div class="md1"></div>

