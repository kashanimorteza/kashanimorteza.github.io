# [<span style="color:black;">Linux Structure</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md)

<br>

## Boot
<table><tbody>
<tr><td rowspan="1"> Boot Steps </td><td rowspan="1"> IC PC Register - Bios - MBR,GPT - BootLoader - Kernel - Systemd </td></tr>
<tr><td rowspan="1"> Boot type </td><td rowspan="1"> Bios - UEFI </td></tr>
<tr><td rowspan="1"> Partition Table </td><td rowspan="1"> MBR - GPT </td></tr>
<tr><td rowspan="1"> Partition type </td><td rowspan="1"> Primary - Extended(Logical) - LVM - swap </td></tr>
</tbody>
</table>



<br><br>
## Boot Loader
<table><tbody>
<tr><td rowspan="1"> Boot Loader </td><td rowspan="1"> GRUB - LILO - BURGO </td></tr>
</tbody></table>



<br><br>
## Kernel
<table><tbody>
<tr>
<td rowspan="1">Layer 3</td>
<td rowspan="1">System Call Interfaces (SCI)</td>
<td>stat, splice, dup, ...</td>
</tr>
</tbody></table>
<table><tbody>
<tr>
<td rowspan="1">Layer 2</td>
<td rowspan="1">Process Scheduling</td>
<td rowspan="1">IPCSub</td>
<td rowspan="1">Memory Management</td>
<td rowspan="1">VirtualFiles</td>
<td rowspan="1">Network</td>
</tr>
</tbody></table>
<table><tbody>
<tr>
<td rowspan="2">Layer 1</td>
<td rowspan="1">Other Subsystems: </td>
<td rowspan="1">ALSA, DRI, evdev, LVM, Device mapper, Linux Network Scheduler, Netfilter</td>
</tr>
<tr>
<td rowspan="1">Security Modules</td>
<td rowspan="1"> SELinux, TOMOYO, AppArmor, Smack</td>
</tr>
</tbody></table>


<br><br>
## C Standard Library
<table><tbody>
<tr>
<td rowspan="1">glibc</td>
<td rowspan="1">uClibc</td>
<td rowspan="1">bionic</td>
<td rowspan="1">Other Implementations</td>
</tr>
</tbody></table>


<br><br>
## Low-level System Components
<table><tbody>
<tr>
<td rowspan="1">System daemons</td>
<td rowspan="1">systemd, runit,logind, networkd, soundd</td>
</tr>
<tr>
<td rowspan="1">Windowing system</td>
<td rowspan="1">X11, Wayland, Mir, SurfaceFlinger(Android)</td>
</tr>
<tr>
<td rowspan="1">Other Libraries</td>
<td rowspan="1">GTK+, Qt, EFL,SDL, SFML, FLTK, GNUstep</td>
</tr>
</tbody></table>


<br><br>
## High-level System Components
<table><tbody>
<tr><td rowspan="1">Shell system</td><td rowspan="1">Bash, </td></tr>
<tr><td rowspan="1">Package Manager System (PMS)</td><td rowspan="1">RPMT, dpkg, yum, knl</td></tr>
</tbody></table>


<br><br>
## runLevel


<br><br>
## File system

<br><br>
## Hard Disk

| Subject | Memeber |
| ------ | ------ |
| /etc/fstab   | kernel linux read this file at the first  |

<br><br>
## Account & Permission


<br><br>
## Other
System daemons - Windowing system - Other libraries - GUI(Gnome)
* [Init] - 
* [Hal] - 
* [debus] - 
* [udev] - 
* [UUID] - 
* [Folders] - 
* [Runlevel] - 
* [Variables] - 
<br><br>


<br><br>
## Process
| Process | E |
| ------ | ------ |
| Hal | مثلا کارت شبکه اول رو eth0 قرار میده، فارق از اینکه مدلش چیه و یا برای چه کارخانه ای اس |
| dbus | یک باس زیر نرم افزارهااست، مثلا وقتی موس به سیستم وصل شد به برنامه X بگو یه کارایی انجام بده  |
| udev | یه سری اتفاق رو هندل میکنه، مثلا وقتی فلش دیسک رو زدم بیا یه سری کار انجام بد |
| init | مادر تمام پروسه ها |
| LVM | چند تا هارد رو بوسیله LVM بصورت یک هارد به سیستم عامل نشان بده |
| UUID |  |


<br><br>
## Security


<br><br>
## Network


<br><br>
## Log  
/var/log/messages<br>
dmesg


<br><br>
## Script


<br><br>
## Bash


<br><br>
## Reqular expression


<br><br>
## Folder system
Search on internet
