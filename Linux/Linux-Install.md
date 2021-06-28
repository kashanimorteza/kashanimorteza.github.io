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

# [<span style="color:black;">Linux Install</span>](Linux.md)

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
<a href="#Basic">Basic</a> - 
<a href="#Tools">Tools</a> - 
<a href="#Programming">Programming</a> - 
<a href="#Software">Software</a>





<div class="md1"></div>

## <span class="red">Ubuntu</span>

#### <span class="blue">Basic</span>
	sudo apt update
	sudo apt upgrade

#### <span class="blue">Tools</span>

	sudo apt install software-properties-common
	sudo apt install apt-transport-https
	sudo apt install wget
	sudo apt install ca-certificates
	sudo apt-get install unixodbc-dev

#### <span class="blue">Network</span>

	sudo apt install net-tools
	sudo apt install iputils-ping

#### <span class="blue">Server</span>

SSH

	sudo apt install openssh-server

#### <span class="blue">Software</span>

Chrome

	cd ~/Downloads
	wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
	sudo apt install ./google-chrome-stable_current_amd64.deb





<div class="md0"></div>

## Centos

#### Basic

	dnf update
	dnf upgrade

	dnf clean all
	rm -fr /var/cache/dnf
	dnf -y upgrade
	dnf -y update

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

#### Software

Chrome

	curl -SLo chrome.rpm https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
	dnf localinstall chrome.rpm









<div class="md0"></div>

## Software

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





#### Atom	
	curl -SLo atom.rpm https://atom.io/download/rpm
	dnf localinstall atom.rpm
	
	
#### VS Code
	---[ubuntu]
	Way 1:
	wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
	sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
	sudo apt update
	sudo apt install code

	Way 2:
	cd ~/Downloads
	wget https://az764295.vo.msecnd.net/stable/a0479759d6e9ea56afa657e454193f72aef85bd0/code_1.48.2-1598353430_amd64.deb	
	sudo apt install ./code_1.48.2-1598353430_amd64.deb
	



