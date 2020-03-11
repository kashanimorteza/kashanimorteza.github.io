<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Config</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Script](Linux-Script.md)

<div class="md1"></div>

## Create Partition

	#!/bin/bash

	hdd="sdd"

	fdisk /dev/$hdd << EOF
	g
	n


	+25G
	n


	+50M
	n


	+2300M
	n


	+2100M
	n


	+1600M
	n


	+7300M
	n


	+2100M
	n


	+1700M
	n


	+2000M
	n


	+2000M
	n


	+5900M
	w

	EOF
	exit 0


<div class="md1"></div>

## Format Partition

	#!/bin/bash

	hdd="sdd"

	mkfs.ext4 -F /dev/"$hdd"1
	mkfs.vfat -F 32 /dev/"$hdd"2
	mkfs.ext4 -F /dev/"$hdd"3
	mkfs.ext4 -F /dev/"$hdd"4
	mkfs.ext4 -F /dev/"$hdd"5
	mkfs.ext4 -F /dev/"$hdd"6
	mkfs.ext4 -F /dev/"$hdd"7
	mkfs.ext4 -F /dev/"$hdd"8
	mkfs.ext4 -F /dev/"$hdd"9
	mkfs.ext4 -F /dev/"$hdd"10
	mkfs.ext4 -F /dev/"$hdd"11


<div class="md1"></div>

## Mount Partition
	#!/bin/bash

	hdd="sdd"

	mkdir /media/"$hdd"1
	mkdir /media/"$hdd"2
	mkdir /media/"$hdd"3
	mkdir /media/"$hdd"4
	mkdir /media/"$hdd"5
	mkdir /media/"$hdd"6
	mkdir /media/"$hdd"7
	mkdir /media/"$hdd"8
	mkdir /media/"$hdd"9
	mkdir /media/"$hdd"10
	mkdir /media/"$hdd"11
	mkdir /media/iso

	mount -t ext4 /dev/"$hdd"1 /media/"$hdd"1/
	mount /dev/"$hdd"2 /media/"$hdd"2/
	mount -t ext4 /dev/"$hdd"3 /media/"$hdd"3/
	mount -t ext4 /dev/"$hdd"4 /media/"$hdd"4/
	mount -t ext4 /dev/"$hdd"5 /media/"$hdd"5/
	mount -t ext4 /dev/"$hdd"6 /media/"$hdd"6/
	mount -t ext4 /dev/"$hdd"7 /media/"$hdd"7/
	mount -t ext4 /dev/"$hdd"8 /media/"$hdd"8/
	mount -t ext4 /dev/"$hdd"9 /media/"$hdd"9/
	mount -t ext4 /dev/"$hdd"10 /media/"$hdd"10/
	mount -t ext4 /dev/"$hdd"11 /media/"$hdd"11/


<div class="md1"></div>

## Copy ISO

	#!/bin/bash

	hdd="sdd"

	cp -r /media/sda4/Users/Morteza/Desktop/Computer/. /media/"$hdd"1

	cp -r /media/"$hdd"1/NewGrub/EFI /media/"$hdd"2

	mount -t iso9660 /media/"$hdd"1/Linux-Fedora-Server-dvd-x86_64-31-1.9.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"3/
	rm -fr /media/"$hdd"3/EFI/

	mount -t iso9660 /media/"$hdd"1/Linux-Fedora-Workstation-Live-x86_64-31-1.9.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"4/
	rm -fr /media/"$hdd"4/EFI/

	mount -t iso9660 /media/"$hdd"1/Linux-Fedora-Xfce-Live-x86_64-31-1.9.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"5/
	rm -fr /media/"$hdd"5/EFI/

	mount -t iso9660 /media/"$hdd"1/Linux-CentOS-8-x86_64-1905-dvd1.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"6/
	rm -fr /media/"$hdd"6/EFI/

	mount -t iso9660 /media/"$hdd"1/Linux-Ubuntu-18.04.2-desktop-amd64.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"7/
	rm -fr /media/"$hdd"7/EFI/

	mount -t iso9660 /media/"$hdd"1/Linux-Ubuntu-Xfce-19.04-desktop-amd64.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"8/
	rm -fr /media/"$hdd"8/EFI/

	mount -t iso9660 /media/"$hdd"1/Windows-10-X64-19H2-10in1-OEM-ESD-en-US-DEC-2019.iso /media/iso -o loop
	cp -r /media/iso/. /media/"$hdd"11/
	rm -fr /media/"$hdd"11/EFI/





<div class="md1"></div>

## Grub Config
	set default="0"

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
	menuentry 'Fedora Server 31' --class fedora --class gnu-linux --class gnu --class os {
		load_video
		set gfx_payload=keep
		insmod gzio
		set root=(hd1,12)
		linux /boot/vmlinuz-5.3.7-301.fc31.x86_64 root=UUID=04660859-5493-4469-9c56-1846ad4f7097 ro\ rhgb quiet
		initrd /boot/initramfs-5.3.7-301.fc31.x86_64.img
	}
	menuentry 'Ubuntu' --class ubuntu --class gnu-linux --class gnu --class os $menuentry_id_option 'gnulinux-simple-bd950b68-33f3-45ac-922e-e2f9770abd46' {

		set root='hd1,gpt3'
		linux	/boot/vmlinuz-4.18.0-15-generic root=UUID=bd950b68-33f3-45ac-922e-e2f9770abd46 ro quiet splash
		initrd	/boot/initrd.img-4.18.0-15-generic
	}










	menuentry 'Install Fedora Server 31' --class fedora --class gnu-linux --class gnu --class os {

		set root=(hd1,3)
		linuxefi /images/pxeboot/vmlinuz inst.repo=hd:sdb3 quiet
		initrdefi /images/pxeboot/initrd.img
	}
	menuentry 'Install Fedora Workstation 31' --class fedora --class gnu-linux --class gnu --class os {

		set root=(hd1,4)
		linuxefi /images/pxeboot/vmlinuz inst.repo=hd:sdb4 quiet
		initrdefi /images/pxeboot/initrd.img
	}
	menuentry 'Install Fedora Xfce 31' --class fedora --class gnu-linux --class gnu --class os {

		set root=(hd1,5)	
		linuxefi /images/pxeboot/vmlinuz inst.repo=hd:sdb5 quiet
		initrdefi /images/pxeboot/initrd.img
	}
	menuentry 'Install CentOS 8.0.1905' --class fedora --class gnu-linux --class gnu --class os {
		
		set root=(hd1,6)
		linuxefi /images/pxeboot/vmlinuz inst.repo=hd:sdb6 quiet
		initrdefi /images/pxeboot/initrd.img
	}
	menuentry "Install Ubuntu-18.04.2" {
		
		set root=(hd1,7)
		set gfxpayload=keep
		linuxefi /casper/vmlinuz boot=casper boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi /casper/initrd
	}
	menuentry "Install Ubuntu Xfce 18.04.2" {
		
		set root=(hd1,8)
		set gfxpayload=keep	
		linuxefi /casper/vmlinuz boot=casper boot=casper iso-scan/filename=${isofile} quiet splash
		initrdefi /casper/initrd
	}

	menuentry 'Install Windows 10' --class fedora --class gnu-linux --class gnu --class os {

		set root=(hd1,11)	
		linuxefi /images/pxeboot/vmlinuz inst.repo=hd:sdb11 quiet
		initrdefi /images/pxeboot/initrd.img
	}





