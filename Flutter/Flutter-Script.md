<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Flutter Script</span>](Flutter.md)
[Basic](Flutter-Basic.md) | [Widget](Flutter-Widget.md) | [Package](Flutter-Package.md) | [Command](Flutter-Command.md) | [Script](Flutter-Script.md)
<div class="md1"></div>




## General
	import 'package:flutter/material.dart';

	void main() {
	  runApp(MyApp());
	}

	class MyApp extends StatelessWidget{

	  Widget build(BuildContext context) {
		return MaterialApp(home: Text('Hello', ));
	  }

	}

