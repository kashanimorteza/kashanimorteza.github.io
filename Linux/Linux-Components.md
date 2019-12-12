<style>
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
</style>



# [<span style="color:black;">Linux Components</span>](Linux.md)
[Basic](Linux-Basic.md) | [Structure](Linux-Structure.md) | [Components](Linux-Components.md) | [Requirement](Linux-Requirement.md) | [Command](Linux-Command.md) | [Config](Linux-Config.md)



<div class="md1"></div>

## System and Service Manage : Systemd
<table><tbody>
<tr><td colspan="2" align="center" bgcolor="D1ECCF">Info</td></tr>
<tr><td rowspan="1">Developer</td><td>Redhat</td></tr>
<tr><td rowspan="1">Wetsite</td><td><a href="https://www.freedesktop.org/wiki/" target="_blank">www.freedesktop.org</a></td></tr>
<tr><td rowspan="1">Github</td><td><a href="https://github.com/systemd" target="_blank">www.github.com/systemd</a></td></tr>
<tr><td rowspan="1">Wiki</td><td><a href="https://www.freedesktop.org/wiki/Software/systemd/" target="_blank">www.freedesktop.org/wiki/Software/systemd/</a></td></tr>
</tbody></table>
<div class="md3"></div>
<table><tbody>
<tr><td colspan="2" align="center" bgcolor="D1ECCF">Structure</td></tr>
<tr><td rowspan="1">Libraries</td><td>dbus-1 - libpam - libcam - libcryptsetup - tcpwrapper - libaudit - libnotify</td></tr>
<tr><td rowspan="1">Components</td><td>journald - logind - networkd - tmpfiles - timedated - udevd - Systemd-boot</td></tr>
<tr><td rowspan="1">Units</td><td>service - socket - device - mount - automount - swap - target - path - timer - snapshot - slice - scope</td></tr>
<tr><td rowspan="1">Targets</td><td>bootmode - basic - shutdown - reboot - multiuser - graphical - user session</td></tr>
<tr><td rowspan="1">Utilites</td><td>systemctl - journalctl - notify - analyze - cgls - cgtop - loginctl - nspawn</td></tr>
<tr><td rowspan="1">GUI Interface</td><td>systemd-ui, systemd-kcm</td></tr>
<tr><td rowspan="1">Command</td><td>systemctl , systemd-analyze</td></tr>
</tbody></table>
<div class="md3"></div>
<table><tbody>
<tr><td colspan="2" align="center" bgcolor="D1ECCF">Hierarchy of configuration files</td></tr>
<tr><td rowspan="1">Local configuration</td><td>/etc/systemd/system</td></tr>
<tr><td rowspan="1">Runtime units</td><td>/run/systemd/system</td></tr>
<tr><td rowspan="1">Units of installed packages</td><td>/usr/lib/systemd/system</td></tr>
</tbody></table>



<div class="md1"></div>

## Event logging : journald
| a | b |
| ------ | ------ |
| b | a |




<div class="md1"></div>

## User Manager : logind
| a | b |
| ------ | ------ |
| b | a |



<div class="md1"></div>

## Network Manager : networkd
| a | b |
| ------ | ------ |
| b | a |



<div class="md1"></div>

## Temp Manager : tmpfiles
| a | b |
| ------ | ------ |
| b | a |



<div class="md1"></div>

## Time Manager : timedated
| a | b |
| ------ | ------ |
| b | a |



<div class="md1"></div>

## Device Manager : udevd
| a | b |
| ------ | ------ |
| libudev | Standard libreary for using of udev |



<div class="md1"></div>

## Boot Manager : Systemd-boot
| a | b |
| ------ | ------ |
| libudev | Standard libreary for using of udev |



<div class="md1"></div>

## Security



<div class="md1"></div>

## Network



<div class="md1"></div>

## Log  
/var/log/messages<br>
dmesg
