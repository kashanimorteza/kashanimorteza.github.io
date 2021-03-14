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
[Application](Flutter-Application.md) |
[My Library](Flutter-MyLibrary.md)




<div class="md3"></div>
<a href="#class">Class</a> - 
<a href="#widget">Widget</a> - 
<a href="#method">Method</a> - 
<a href="#package">Package</a>




<div class="md1"></div>

## Class

#### <span class="red">Base</span>

<table><tbody>
<tr >
<td align="center" bgcolor="D1ECCF">Widget </td>
<td align="center" bgcolor="D1ECCF">Explain</td>
</tr>
<tr>
<td rowspan="1">StatelessWidget</td>
<td rowspan="1">main Widget , Abstract class , All Widget must put in this Widget , Static </td>
</tr>
<tr>
<td align="center" rowspan="1">StatefulWidget</td>
<td rowspan="1">main Widget , Abstract class , All Widget must put in this Widget , Dynamic</td>
</tr>
<tr>
<td align="center" rowspan="1">State</td>
<td rowspan="1">The logic and internal state for a StatefulWidget.</td>
</tr>
</tbody></table>



<div class="md0"></div>

## Widget

#### <span class="red">App structure</span>

<table><tbody>
<tr >
<td align="center" bgcolor="D1ECCF">Widget </td>
<td align="center" bgcolor="D1ECCF">Explain</td>
</tr>
<tr>
<td align="center" rowspan="1">MaterialApp</td>
<td rowspan="1">Gives us all the propertied of material design</td>
</tr>
<tr>
<td align="center" rowspan="1">Scaffold</td>
<td rowspan="1">Implements the basic material design visual layout structure</td>
</tr>
<tr>
<td align="center" rowspan="1">Card</td>
<td rowspan="1"></td>
</tr>
</tbody></table>





#### <span class="red">Layout</span>

<table><tbody>
<tr >
<td align="center" bgcolor="D1ECCF">Widget </td>
<td align="center" bgcolor="D1ECCF">Explain</td>
</tr>
<tr>
<td align="center" rowspan="1">Column</td>
<td rowspan="1">A widget that displays its children in a vertical array</td>
</tr>
<tr>
<td align="center" rowspan="1">Row</td>
<td rowspan="1">A widget that displays its children in a horizontal array</td>
</tr>
<tr>
<td align="center" rowspan="1">Container</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">Stack</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">Flexible</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">SingleChildScrollView</td>
<td rowspan="1"></td>
</tr>
</tbody></table>




#### <span class="red">Object</span>

<table><tbody>

<tr >
<td align="center" bgcolor="D1ECCF">Widget </td>
<td align="center" bgcolor="D1ECCF">Explain</td>
</tr>
<tr>
<td align="center" rowspan="1">TextField</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">RaiseButton</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">ListView</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">ListTile</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">GridView</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">ListTile</td>
<td rowspan="1"></td>
</tr>
<tr>
<td align="center" rowspan="1">AppBar</td>
<td rowspan="1">A material design app bar.</td>
</tr>
</tbody></table>






<div class="md0"></div>

## Method

<table><tbody>
<tr >
<td align="center" bgcolor="D1ECCF">Method</td>
<td align="center" bgcolor="D1ECCF">Explain</td>
</tr>
<tr>
<td align="center">main()</td>
<td rowspan="1">Run Application with this method</td>
</tr>
<tr>
<td align="center">runApp()</td>
<td rowspan="1">Set main widget to run</td>
</tr>
<tr>
<td align="center">setState()</td>
<td rowspan="1">force flutter to reload U</td>
</tr>
<tr>
<td align="center">showModalBottomSheet</td>
<td rowspan="1">Shows a modal material design bottom sheet.</td>
</tr>

</tbody></table>








<div class="md0"></div>

## Package