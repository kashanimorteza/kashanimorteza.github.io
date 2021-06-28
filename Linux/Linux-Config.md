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
.green{color:#28B463}
table{border: 0px solid black;}
</style>

# [<span style="color:black;">Linux Config</span>](Linux.md)

<div class="md3"></div>

[Basic](Linux-Basic.md) | 
[Structure](Linux-Structure.md) | 
[Components](Linux-Components.md) | 
[Requirement](Linux-Requirement.md) | 
[Command](Linux-Command.md) | 
[Config](Linux-Config.md) | 
[Install](Linux-Install.md) | 
[Script](Linux-Script.md)

<div class="md3"></div>
<a href="#ssh">SSH</a> - 
<a href="#network">Network</a> - 


<div class="md3"></div>




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










## <span class="red">SSH</span>

<div class="md1">

#### <span class="blue">Service</span>

	sudo systemctl status ssh

	[ps show ssh]
	--------------
	vi /usr/bin/pp
	chmod 755 /usr/bin/pp
	#!/bin/bash
	ps -wax | grep ssh

#### <span class="blue">Connection</span>

	ssh root@192.168.1.1

#### <span class="blue">Tunnel</span>

	vi /usr/bin/mytunnel
	---------------------
	#!/bin/bash
	ssh -D 8080 -f -C -q -N root@185.177.23.137

	chmod 755 /usr/bin/mytunnel

	mytunnel



#### <span class="blue">Putty Key-Based</span>

	1 - Download puttygen and run it
	2 - Click on 'Generate' Button and move mouse to generate faster
	3 - Afte complete generation, Click on 'Save private key' Button and save as linux.ppk
	4 - Connect to linux server :
	5 - Create folder : mkdir /root/.ssh
	6 - Create file : vim /root/.ssh/authorized_keys
	7 - Permition file : chmod -R 700 /root/.ssh/authorized_keys
	8 - Copy public_key from linux.ppk
	9 - Paste public_key into server file : /root/.ssh/authorized_keys
	10 - Add 'ssh-rsa' at the first of the public_key with space
	11 - Set linux.ppk On putty > connection > SSH > Auth
	12 - Set  username(for example root) at putty > connection > data > Auto-login username

#### <span class="blue">Ssh Key-Based</span>

	ssh-keygen -t rsa
	ssh root@185.177.23.137 mkdir -p .ssh
	cat .ssh/id_rsa.pub | ssh root@185.177.23.137 'cat >> .ssh/authorized_keys'

</div>



## <span class="red">Network</span>

<div class="md1">

#### <span class="blue">Set Static</span>

	sudo vim /etc/netplan/1-network-manager-all.yaml
	-------------------------------------------------
	network:
	version: 2
	renderer: NetworkManager
	ethernets:
	enp2s0:
		dhcp4: no
		addresses:
			- 192.168.1.110/24
		gateway4: 192.168.1.1
		nameservers:
			addresses: [8.8.8.8, 4.2.2.4]
	
	run this command
	-------------------
	sudo netplan apply
	ip addr show dev enp2s0

</div>




