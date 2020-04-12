<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Install</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Install](Linux-Install.md) | [Script](Linux-Script.md)
<div class="md1"></div>




## Basic
	dnf update
	dnf upgrade

	dnf clean all
	rm -fr /var/cache/dnf
	dnf -y upgrade
	dnf -y update




<div class="md1"></div>




## Tools
#### EPEL
	dnf -y install epel-release
	yum config-manager --set-enabled PowerTools

	dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

#### Network	
	dnf install net-tools
	
#### ntfs
	dnf -y install ntfs-3g	
	
	wget https://tuxera.com/opensource/ntfs-3g_ntfsprogs-2017.3.23.tgz
	tar -zxvf ntfs-3g_ntfsprogs-2017.3.23.tgz
	cd ntfs-3g_ntfsprogs-2017.3.23
	./configure --prefix=/usr/local --disable-static
	make
	make install

	mkdir /media/sda1
	mount -t ntfs-3g /dev/sd11 /media/sda1
	umount /media/sda1

	vim /etc/fstab
	/dev/sda1 /media/sda1 ntfs-3g defaults 0 0




<div class="md1"></div>




## Software
#### Chrome		
	curl -SLo chrome.rpm https://dl.google.com/linux/direct/google-chrome-		stable_current_x86_64.rpm
	dnf localinstall chrome.rpm

#### Telegram
	Download from telegram.com

	dnf config-manager --add-repo ppa:atareao/telegram
	dnf update 
	dnf install telegram

#### Xdman
	curl -SLo xdm.xz https://github.com/subhra74/xdm/releases/download/7.2.10/xdm-setup-7.2.10.tar.xz
	tar -xvf xdm.xz
	./install.sh
	
#### Openvpn
	dnf install openvpn

	git clone https://github.com/Nyr/openvpn-install.git
	cd ./openvpn-install
	chmod +x ./openvpn-install.sh
	./openvpn-install.sh

	sudo openvpn --config /home/morteza/Downloads/vpnbook/vpnbook-us2-udp25000.ovpn --auth-user-pass login.conf
	
#### Atom	
	curl -SLo atom.rpm https://atom.io/download/rpm
	dnf localinstall atom.rpm
	
#### f.lux
	sudo add-apt-repository ppa:nathan-renniewaldock/flux
	sudo apt-get update
	sudo apt-get install fluxgui
	sudo apt-get install fluxgui
	51.48N, 0.29W
	
#### Redshift
	sudo apt-get install libxcb1-dev libxcb-randr0-dev libx11-dev
	sudo apt-get install redshift redshift-gtk
	
#### putty
	sudo apt-get install putty

#### Grub Customizer
	sudo add-apt-repository ppa:danielrichter2007/grub-customizer
	sudo apt-get update
	sudo apt-get install grub-customizer
	

	
#### unetbootin
	sudo add-apt-repository ppa:gezakovacs/ppa 
	sudo apt-get update 
	sudo apt-get install unetbootin


#### Git
	dnf --enablerepo="epel" install git



