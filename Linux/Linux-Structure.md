<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Linux Structure</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md) | [Install](Linux-Install.md) | [Script](Linux-Script.md)
<div class="md1"></div>




## Boot
<table><tbody>
<tr><td rowspan="1"> Boot Loader </td><td rowspan="1"> Grub </td></tr>
</tbody>
</table>



<div class="md1"></div>

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
<table><tbody>
<tr>
<td rowspan="1">/etc/fstab</td>
<td>kernel linux read this file at the first</td>
</tr>
</tbody></table>



<div class="md1"></div>

## C Standard Library
<table><tbody>
<tr>
<td rowspan="1">glibc</td>
<td rowspan="1">uClibc</td>
<td rowspan="1">bionic</td>
<td rowspan="1">Other Implementations</td>
</tr>
</tbody></table>
<div class="md2"></div>


<div class="md1"></div>

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



<div class="md1"></div>

## High-level System Components
<table><tbody>
<tr><td rowspan="1">Shell system</td><td rowspan="1">Bash, </td></tr>
<tr><td rowspan="1">Package Manager System (PMS)</td><td rowspan="1">RPMT, dpkg, yum, knl</td></tr>
</tbody></table>



<div class="md1"></div>

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



<div class="md1"></div>

## Process
| Process | E |
| ------ | ------ |
| Hal | مثلا کارت شبکه اول رو eth0 قرار میده، فارق از اینکه مدلش چیه و یا برای چه کارخانه ای اس |
| dbus | یک باس زیر نرم افزارهااست، مثلا وقتی موس به سیستم وصل شد به برنامه X بگو یه کارایی انجام بده  |
| udev | یه سری اتفاق رو هندل میکنه، مثلا وقتی فلش دیسک رو زدم بیا یه سری کار انجام بد |
| init | مادر تمام پروسه ها |
| LVM | چند تا هارد رو بوسیله LVM بصورت یک هارد به سیستم عامل نشان بده |
| UUID |  |





<div class="md1"></div>

## Script


<div class="md1"></div>

## Bash


<div class="md1"></div>

## Reqular expression


<div class="md1"></div>

## Folder system
Search on internet
