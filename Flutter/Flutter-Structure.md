<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C;font-size: 16px;}
.blue{color:#3498DB}
.green{color:##28B463}
</style>


# [<span style="color:black;">Flutter Structure</span>](Flutter.md)
[Diagram](Flutter-Diagram.md) |
[Basic](Flutter-Basic.md) |
[Structure](Flutter-Structure.md) |
[Script](Flutter-Script.md) |
[My Library](Flutter-MyLibrary.md) |
[My Program](Flutter_MyProgram.md)



<div class="md3"></div>
<a href="#widget">Widget</a> - 
<a href="#class">Class</a> - 
<a href="#method">Method</a> - 
<a href="#package">Package</a>





<div class="md1"></div>

## Widget

#### <span class="red">Invisible Or Layout Or Control</span>

<table><tbody>
<tr>
<td rowspan="1">StatelessWidget</td>
<td rowspan="1">main Widget , Abstract class , All Widget must put in this Widget , Static </td>
</tr>
<tr>
<tr>
<td rowspan="1">StatefulWidget</td>
<td rowspan="1">main Widget , Abstract class , All Widget must put in this Widget , Dynamic</td>
</tr>
<td rowspan="1">MaterialApp</td>
<td rowspan="1">Gives us all the propertied of material design</td>
</tr>
<tr>
<tr>
<td rowspan="1">Scaffold</td>
<td rowspan="1">Implements the basic material design visual layout structure</td>
</tr>
<tr>
<td rowspan="1">Column</td>
<td rowspan="1">A widget that displays its children in a vertical array</td>
</tr>
<tr>
<td rowspan="1">Row</td>
<td rowspan="1">A widget that displays its children in a horizontal array</td>
</tr>
<tr>
<td rowspan="1">Container</td>
<td rowspan="1"></td>
</tr>
</tbody></table>

<div class="md3"></div>

#### <span class="red">Visible</span>

<table><tbody>
<tr>
<td rowspan="1">AppBar</td>
<td rowspan="1">A material design app bar.</td>
</tr>
</tbody></table>







<div class="md0"></div>

## Class

<table><tbody>
<tr>
<td rowspan="1">State</td>
<td rowspan="1">The logic and internal state for a StatefulWidget.</td>
</tr>
</tbody></table>








<div class="md0"></div>

## Method

<table><tbody>
<tr>
<td rowspan="1">setState()</td>
<td rowspan="1">force flutter to reload UI</td>
</tr>
</tbody></table>








<div class="md0"></div>

## Package