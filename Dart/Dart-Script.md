<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Dart Script</span>](Dart.md)
[Diagram](Dart-Diagram.md) | 
[Basic](Dart-Basic.md) | 
[Language](Dart-Language.md) | 
[Development](Dart-Development.md) | 
[Script](Dart-Script.md)
<div class="md1"></div>




## General

#### null safety

	String x;

	x = null;
	print(x?.toUpperCase());

	x = "asd";
	print(x?.toUpperCase());