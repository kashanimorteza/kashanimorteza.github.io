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




<div class="md1"></div>




## Tools
#### Network
	sudo apt install -f
	sudo apt install net-tools	
#### ntfs
	yum install epel-release
	yum install ntfs-3g
	mkdir /mnt/win
	mount -t ntfs-3g /dev/sdb1 /mnt/win
	umount /mnt/win
	nano /etc/fstab
	/dev/sdb1 /mnt/win ntfs-3g defaults 0 0




<div class="md1"></div>




## Software
#### Chrome
	su
    
	[Method 1]
	dnf install fedora-workstation-repositories
	dnf config-manager --set-enabled google-chrome
	dnf install google-chrome-stable
	google-chrome
	
	[Method 2]
	sudo dnf install https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
	google-chrome
	
#### Notepad++
	dnf install notepadqq 
	
#### Xdman
	wget https://datapacket.dl.sourceforge.net/project/xdman/xdm-2018-x64.tar.xz
	tar -xvf xdm-2018-x64.tar.xz
	sudo ./install.sh
	
#### Openvpn
	sudo apt install network-manager-openvpn-gnome
	sudo openvpn --config /path/to/config.ovpn
	
#### Git
	sudo apt install git
	
#### Atom
	sudo add-apt-repository ppa:webupd8team/atom
	sudo apt update
	sudo apt install atom
	
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
	
#### Telegram
	sudo add-apt-repository ppa:atareao/telegram 
	sudo apt-get update 
	sudo apt-get install telegram
	
#### unetbootin
	sudo add-apt-repository ppa:gezakovacs/ppa 
	sudo apt-get update 
	sudo apt-get install unetbootin



