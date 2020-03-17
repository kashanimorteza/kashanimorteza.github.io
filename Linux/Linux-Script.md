<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Config</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Install](Linux-Install.md) | [Script](Linux-Script.md)
<div class="md1"></div>




## Create Partition
	#!/bin/bash

	hdd="sdd"

	fdisk /dev/$hdd << EOF
	g
	n


	+50M
	n


	+30G
	w

	EOF
	exit 0
	
	
	
	
<div class="md1"></div>





## Format Partition
	#!/bin/bash

	hdd="sdd"
	
	mkfs.vfat -F 32 /dev/"$hdd"1
	mkfs.ext4 -F /dev/"$hdd"2




<div class="md1"></div>





## Mount Partition
	#!/bin/bash

	hdd="sdd"

	mkdir /media/"$hdd"1
	mkdir /media/"$hdd"2

	mount /dev/"$hdd"2 /media/"$hdd"2/
	mount -t ext4 /dev/"$hdd"1 /media/"$hdd"1/
	
	
	
	
<div class="md1"></div>




## Copy ISO
	#!/bin/bash

	hdd="sdd"

	cp -r /media/sda4/Users/Morteza/Desktop/Computer/. /media/"$hdd"1

	cp -r /media/"$hdd"1/NewGrub/EFI /media/"$hdd"2

	mount -t iso9660 /media/"$hdd"1/Linux-Fedora-Server.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"3/
	rm -fr /media/"$hdd"3/EFI/
	
	
	
	
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


	menuentry 'Windows' --class windows --class os $menuentry_id_option 'osprober-efi-38A7-4966' {
		
		set root='hd0,gpt2'
		insmod part_gpt	
		insmod fat
		chainloader /EFI/Microsoft/Boot/bootmgfw.efi
	}
	menuentry 'Centos' --class fedora --class gnu-linux --class gnu --class os {
		load_video
		set gfx_payload=keep
		insmod gzio
		set root=(hd1,3)
		linux /boot/vmlinuz-5.3.7-301.fc31.x86_64 root=UUID=04660859-5493-4469-9c56-1846ad4f7097 ro\ rhgb quiet
		initrd /boot/initramfs-5.3.7-301.fc31.x86_64.img
	}
	menuentry 'Ubuntu' --class ubuntu --class gnu-linux --class gnu --class os $menuentry_id_option 'gnulinux-simple-bd950b68-33f3-45ac-922e-e2f9770abd46' {

		set root='hd1,4'
		linux	/boot/vmlinuz-4.18.0-15-generic root=UUID=bd950b68-33f3-45ac-922e-e2f9770abd46 ro quiet splash
		initrd	/boot/initrd.img-4.18.0-15-generic
	}
	menuentry 'Ubuntu Xfce' --class ubuntu --class gnu-linux --class gnu --class os $menuentry_id_option 'gnulinux-simple-bd950b68-33f3-45ac-922e-e2f9770abd46' {

		set root='hd1,5'
		linux	/boot/vmlinuz-4.18.0-15-generic root=UUID=bd950b68-33f3-45ac-922e-e2f9770abd46 ro quiet splash
		initrd	/boot/initrd.img-4.18.0-15-generic
	}


	menuentry "Install --- Centos" {

		set isofile=/linux-centos.iso
		loopback loop3 (hd1,1)$isofile
		linuxefi (loop3)/images/pxeboot/vmlinuz inst.repo=hd:sdb1 quiet
		initrdefi (loop3)/images/pxeboot/initrd.img
	}
	menuentry "Install --- Ubuntu" {
		
		set isofile=/linux-ubuntu.iso
		loopback loop4 (hd1,1)$isofile
		linuxefi (loop4)/casper/vmlinuz boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi (loop4)/casper/initrd
	}
	menuentry "Install --- Ubuntu Xfce" {
		
		set isofile=/linux-ubuntu-xfce.iso
		loopback loop5 (hd1,1)$isofile
		linuxefi (loop5)/casper/vmlinuz boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi (loop5)/casper/initrd
	}