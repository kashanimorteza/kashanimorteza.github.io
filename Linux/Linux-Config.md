<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Config</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Install](Linux-Install.md) | [Script](Linux-Script.md)
<div class="md1"></div>




## Config file
<table><tbody>
<tr><td colspan="2" align="center" bgcolor="D1ECCF">Config Files</td></tr>
<tr><td rowspan="1">Libreary path</td><td>/etc/ld.so.conf</td></tr>
<tr><td rowspan="1">Libreary name and phth of cash</td><td>/etc/ld.so.cache</td></tr>
<tr><td rowspan="1">List Of Packages</td><td>/etc/apt/sources.list</td></tr>
</tbody></table>




<div class="md1"></div>




## Boot
#### Add Menu to grub
	Add these lines to filr /etc/grub.d/40_custom :
	---------------------------------------------------
	menuentry "Install Linux Ubuntu-18.04.2" {
	set isofile="/Linux-Ubuntu-18.04.2-desktop-amd64.iso"
	loopback loop (hd1,2)$isofile
	linuxefi (loop)/casper/vmlinuz boot=casper iso-scan/filename=${isofile} quiet splash
	initrdefi (loop)/casper/initrd
	}
	
	Run this command : update-grub
	
#### Reinstall BootLoader
	sudo mkdir /mnt/ubuntu <br>
	sudo mount /dev/sda1 /mnt/ubuntu <br>
	sudo grub-install --boot-directory=/mnt/ubuntu/boot /dev/sda <br>




<div class="md1"></div>
	
	
	
	
## User
#### Enable root user
    sudo passwd root
    usermod -U root
    su root
#### Disable sudo pass
	vim /etc/sudoers
	ALL     ALL = (ALL) NOPASSWD: ALL
	
	
	
	
<div class="md1"></div>




## Device
#### Disable Touchpad
	echo 'xinput --disable 15' >> $HOME/.profile




<div class="md1"></div>




## SSH key base
#### Putty Key-Based
	Download puttygen.exe
	Generate public/private key with puttygen.exe
	After that Add Key comment : rsa-key-ServerLocal
	Save Public_key as ServerLocal-PUBLIC_KEY 
	Save Private_key as ServerLocal-PRIVATE_KEY 
	Copy code and save as ServerLocal-authorized_keys
	Create drirectory on remote : mkdir /root/.ssh
	Create file on remote: vim /root/.ssh/authorized_keys
	Permission on remote : chmod -R 700 /root/.ssh
	Copy code of ServerLocal-authorized_keys into remote at /root/.ssh/authorized_keys
	Add path of ServerLocal-PRIVATE_KEY into putty : putty > connection > ssh > auth
#### ssh Key-Based
	ssh-keygen -t rsa
	ssh root@185.177.23.137 mkdir -p .ssh
	cat .ssh/id_rsa.pub | ssh root@185.177.23.137 'cat >> .ssh/authorized_keys'
#### ssh tunnel
	vi /usr/bin/p
	chmod 755 /usr/bin/p
	#!/bin/bash
	ssh -D 8080 -f -C -q -N root@185.177.23.137
#### ps show ssh
	vi /usr/bin/pp
	chmod 755 /usr/bin/pp
	#!/bin/bash
	ps -wax | grep ssh








