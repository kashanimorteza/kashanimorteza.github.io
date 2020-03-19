<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Python Structure</span>](Python.md)
[Basic](Python-Basic.md) | [Structure](Python-Structure.md) | [Components](Python-Components.md) | [Requirement](Python-Requirement.md) | [Command](Python-Command.md) | [Config](Python-Config.md) | [Install](Python-Install.md) | [Script](Python-Script.md)
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
<td rowspan="1">ALSA, DRI, evdev, LVM, Device mapper, Python Network Scheduler, Netfilter</td>
</tr>
<tr>
<td rowspan="1">Security Modules</td>
<td rowspan="1"> SEPython, TOMOYO, AppArmor, Smack</td>
</tr>
</tbody></table>
<table><tbody>
<tr>
<td rowspan="1">/etc/fstab</td>
<td>kernel Python read this file at the first</td>
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
<tr><td rowspan="1">Package Manager System (PMS)</td><td rowspan="1">Dnf, RPM, dpkg, yum, knl</td></tr>
</tbody></table>




<div class="md1"></div>

## Folder system
Search on internet
