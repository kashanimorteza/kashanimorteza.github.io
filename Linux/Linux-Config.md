# [<span style="color:black;">Linux Config</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md)

<br>

## Config file
| File | Config |
| ------ | ------ |
| /etc/ld.so.conf     | Libreary path |
| /etc/ld.so.cache     | Libreary name and phth of cash |
| /etc/apt/sources.list     | List Of Packages |


<br /><br />
## User
#### Enable root user
    sudo passwd root
    usermod -U root
    su root
#### Disable sudo pass
	vim /etc/sudoers
	ALL     ALL = (ALL) NOPASSWD: ALL



<br /><br />
## Device
#### Disable Touchpad
	echo 'xinput --disable 15' >> $HOME/.profile


<br /><br />
## Install tools
	sudo apt install -f
	sudo apt install net-tools



<br /><br />
## Install software
#### Chrome
	sudo apt install libxss1 libappindicator1 libindicator7
	wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
	sudo dpkg -i google-chrome*.deb
	if u want to Run google-chrome as root :
	Vim /usr/bin/google-chrome
	Add to end of the file : --user-data-dir
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
#### Notepad++
	sudo add-apt-repository ppa:notepadqq-team/notepadqq
	sudo apt-get update
	sudo apt-get install notepadqq
#### Telegram
	sudo add-apt-repository ppa:atareao/telegram 
	sudo apt-get update 
	sudo apt-get install telegram
#### unetbootin
	sudo add-apt-repository ppa:gezakovacs/ppa 
	sudo apt-get update 
	sudo apt-get install unetbootin
#### ntfs
	yum install epel-release
	yum install ntfs-3g
	mkdir /mnt/win
	mount -t ntfs-3g /dev/sdb1 /mnt/win
	umount /mnt/win
	nano /etc/fstab
	/dev/sdb1 /mnt/win ntfs-3g defaults 0 0


<br /><br />
## Reinstall BootLoader
sudo mkdir /mnt/ubuntu <br>
sudo mount /dev/sda1 /mnt/ubuntu <br>
sudo grub-install --boot-directory=/mnt/ubuntu/boot /dev/sda <br>


<br /><br />
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








