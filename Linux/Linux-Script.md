<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Config</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Install](Linux-Install.md) | [Script](Linux-Script.md)
<div class="md1"></div>




## Create Partition
	#!/bin/bash

	hdd="sdd"

	sudo fdisk /dev/$hdd << EOF
	g
	n


	+25G
	n


	+50M
	w
	EOF
	exit 0
	
	
	
	
<div class="md1"></div>





## Format Partition
	#!/bin/bash

	hdd="sdd"

	sudo mkfs.ext4 -F /dev/"$hdd"1
	sudo mkfs.vfat -F 32 /dev/"$hdd"2




<div class="md1"></div>





## Mount Partition
	#!/bin/bash

	hdd="sdd"

	sudo mkdir /media/"$hdd"1
	sudo mkdir /media/"$hdd"2

	sudo mount -t ext4 /dev/"$hdd"1 /media/"$hdd"1/
	sudo mount /dev/"$hdd"2 /media/"$hdd"2/
	
	
	
	
<div class="md1"></div>




## Copy ISO
	#!/bin/bash

	hdd="sdd"

	sudo cp -r /media/sda4/Users/Morteza/Desktop/Computer/. /media/"$hdd"1

	sudo cp -r /media/"$hdd"1/NewGrub/EFI /media/"$hdd"2

	
	
	
	
<div class="md1"></div>




## Grub Config
	set default="1"

	function load_video {
	  insmod efi_gop
	  insmod efi_uga
	  insmod video_bochs
	  insmod video_cirrus
	  insmod all_video
	}

	load_video
	set gfxpayload=keep
	insmod gzio
	insmod part_gpt
	insmod ext2

	set timeout=60

	search --no-floppy --set=root -l 'Fedora-S-dvd-x86_64-31'



	menuentry "Install --- Centos" {

		set isofile=/linux-centos.iso
		loopback loop3 (hd0,5)$isofile
		linuxefi (loop3)/images/pxeboot/vmlinuz inst.repo=hd:sda5 quiet
		initrdefi (loop3)/images/pxeboot/initrd.img
	}
	menuentry "Install --- Ubuntu" {
		
		set isofile=/linux-ubuntu.iso
		loopback loop4 (hd0,5)$isofile
		linuxefi (loop4)/casper/vmlinuz boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi (loop4)/casper/initrd
	}
	menuentry "Install --- Ubuntu Xfce" {
		
		set isofile=/linux-ubuntu-xfce.iso
		loopback loop5 (hd0,5)$isofile
		linuxefi (loop5)/casper/vmlinuz boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi (loop5)/casper/initrd
	}




<div class="md1"></div>




## openvpn

	#!/bin/bash
	
	sudo openvpn --config /home/morteza/Downloads/vpnbook/vpnbook-us2-udp25000.ovpn --auth-user-pass /home/morteza/Downloads/vpnbook/login.conf








<div class="md0"></div>

## Create Service

sudo vim /etc/systemd/system/forex-downloaddata.service

	[Unit]
	Description=forex download data
	[Service]
	User=morteza
	WorkingDirectory=/home/morteza/forex-download-data
	ExecStart=/home/morteza/forex-download-data/linux-service
	SuccessExitStatus=143
	TimeoutStopSec=10
	Restart=on-failure
	RestartSec=60
	[Install]
	WantedBy=multi-user.target

sudo vim /home/morteza/forex-download-data/linux-service

	#!/bin/sh

	python3.8 main.py

sudo chmod 755 /home/morteza/forex-download-data/linux-service

Start Service

	sudo systemctl daemon-reload
	
	sudo systemctl enable forex-downloaddata
	sudo systemctl disable forex-downloaddata
	
	sudo systemctl is-enabled forex-downloaddata
	sudo systemctl is-active forex-downloaddata

	sudo systemctl start forex-downloaddata
	sudo systemctl stop forex-downloaddata
	sudo systemctl restart forex-downloaddata
	sudo systemctl status forex-downloaddata

Check Service Log 

	sudo journalctl --unit=forex-downloaddata
	sudo journalctl -f -n 10 -u forex-downloaddata
	sudo journalctl -f -u forex-downloaddata