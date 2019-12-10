# [<span style="color:black;">Linux Command</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md)

<br>


<br><br>
## Hardware
| Command | Explain |
| ------ | ------ |
| lsusb   | Show Devices that connected to usb port |
| lspci  | Show Devices that connected to pci port  |
| lshal   | Show Device who be HAL |
| lshw  | Show all Hardware |
| lspcmcia   | Show all mcia card |
| blkid  | Show block id like HDD  |


<br><br>
## Kernel
| Command | Explain |
| ------ | ------ |
| lsmod   | All module that load with kernel |
| rmmod  |   |
| modprobe   |  |
| runlevel   | Show systrm runlevel at the moment |
| telinit   | Move to other runlevel |
| systemctl   | aaa |
| wc   | Count line and character rpm -qa | wc -l |
| grep   | Filter |
| systemctl get-default   | Filter |
| systemd-analyze   | - |




<br><br>
## Process
| Command | Explain |
| ------ | ------ |
| top   | Show all process |
| pstree   | Show all process as tree |
| ps aux   | Show all process |
| kill -9 33407   | kill process with PID 33407 |
| pkill -KILL fire* | kill all process that starts wirh fire |



<br><br>
## File
| Command | Explain |
| ------ | ------ |
| fdisk sda   | aaa |
| parted   | Ude for make partition |
| locate   | Find Directory or file |
| which   | Show path of program |


<br><br>
## Network
| Command | Explain |
| ------ | ------ |
| nmcli d   | Show all network card |
| nmtui   | Graphic GUI for config network |
| ip link   | Show network card with some information |
| ip addr   | Show network card with some information with ipaddress |
| ip -s link   | Shoe detail of informaion about network card |


<br><br>
## Libreary
| Command | Explain |
| ------ | ------ |
| -   | - |
| -  | -  |


<br><br>
## Hard Disk
| Command | Explain |
| ------ | ------ |
| ldd   | Show program library dependency |
| ldconfig  | Cash name and path of libreary  |
| df -h  | list of partition and mounted on  |
| lsblk -p  | list of partition and mounted on  |
| mount/umount  | add hard to file sytem  |
| fdisk  | partition bandi  |


## Log
| Command | Explain |
| ------ | ------ |
| dmesg   | Show all log  |

