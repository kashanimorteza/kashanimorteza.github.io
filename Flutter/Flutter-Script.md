<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Flutter Script</span>](Flutter.md)
[Basic](Flutter-Basic.md) | [Script](Flutter-Script.md)
<div class="md1"></div>




## General

	import 'package:flutter/material.dart';
	
	void main() 
	{
	  runApp(Text("Welcome",textDirection: TextDirection.ltr,));
	}
	
	-------------------------------------------------------------
	
	import 'package:flutter/material.dart';

	void main() 
	{

	  void click() 
	  {    
		print('interaction is here');         
	  }

	  var my_appbar_text = Text("My First Application1");
	  var my_appbar = AppBar(title: my_appbar_text);
	  var my_scaffold = Scaffold(
		appBar: my_appbar,
			body: Column(
			  children: [
				Text(''),
				RaisedButton(
				  child: Text('Click me'),
				  onPressed: click,
				),
			  ]
		),
	  );
		
	  var my_material_app = MaterialApp(
		home: my_scaffold,
	  );
	  
	  runApp(my_material_app);
	}
	
	-------------------------------------------------------------
	
	import 'package:flutter/material.dart';

	void main() {
	  runApp(MyApp());
	}

	class MyApp extends StatelessWidget{

	  Widget build(BuildContext context) {
		return MaterialApp(home: Text('Hello', ));
	  }

	}
		
	-------------------------------------------------------------
	
	void main () 
	{
	  runApp(MyApp());    
	}

	class MyApp extends StatelessWidget 
	{
	  @override
	  Widget build(BuildContext context) 
	  {
		return 
		MaterialApp(
		  home: 
			Text(
			  'hello',
			  textAlign: TextAlign.center,
			  style: TextStyle(color: Colors.red,),
			),
		);
	  }  
	}
	
	-------------------------------------------------------------
	
	void main() {
	  //--- Way 1
	  var my_appbar_text = Text("My First Application1");
	  var my_appbar = AppBar(title: my_appbar_text);
	  var my_scaffold = Scaffold(
		appBar: my_appbar,
	  );
	  var my_material_app = MaterialApp(
		home: my_scaffold,
	  );
	  //var my_stateless_widget=StatelessWidget()
	  //runApp(my_material_app);

	  //--- Way 2
	  runApp(MyApp());
	}

	class MyApp extends StatelessWidget {
	  Widget build(BuildContext context) {
		return MaterialApp(
		  home: Scaffold(
			appBar: AppBar(
			  title: Text("My fist Application2"),
			),
		  ),
		);
	  }
	}
	
	-------------------------------------------------------------
	
	void main() => runApp(MyApp());

	class MyApp extends StatefulWidget {
	  @override
	  State<StatefulWidget> createState() {
		return _MyAppState();
	  }
	}

	class _MyAppState extends State<MyApp> {
	  var questions = [
		'RaisedButton',
		'RaisedButton 1',
		'RaisedButton 2',
		'RaisedButton 3',
	  ];

	  var qi = 0;

	  void answerQuestion() {
		setState(() {
		  print('RaisedButton 1');
		  qi = 1;
		});
	  }

	  @override
	  Widget build(BuildContext context) {
		return MaterialApp(
		  home: Scaffold(
			appBar: AppBar(
			  title: Text('My First application'),
			),
			body: Column(
			  children: [
				Text(questions[qi]),
				RaisedButton(
				  child: Text('RaisedButton 1'),
				  onPressed: answerQuestion,
				),
				RaisedButton(
				  child: Text('RaisedButton 2'),
				  onPressed: () => qi = 2,
				),
				RaisedButton(
				  child: Text('RaisedButton 3'),
				  onPressed: () {
					// ...
					qi = 3;
					print('qi=' + qi.toString());
				  },
				),
			  ],
			),
		  ),
		);
	  }
	}
	
	-------------------------------------------------------------
	
	import 'package:flutter/material.dart';

	class Question extends StatelessWidget {
	  final String questionText;

	  Question(this.questionText);

	  @override
	  Widget build(BuildContext context) {
		return Container(
		  width: double.infinity,
		  margin: EdgeInsets.all(10),
		  child: Text(
			questionText,
			style: TextStyle(fontSize: 28),
			textAlign: TextAlign.center,
		  ),
		);
	  }
	}
	
	
	
	
<div class="md0"></div>
	
	
	
	
## Passing Callback Functions Around	
#### main.dart
	import 'package:flutter/material.dart';

	import './question.dart';
	import './answer.dart';

	// void main() {
	//   runApp(MyApp());
	// }

	void main() => runApp(MyApp());

	class MyApp extends StatefulWidget {
	  @override
	  State<StatefulWidget> createState() {
		// TODO: implement createState
		return _MyAppState();
	  }
	}

	class _MyAppState extends State<MyApp> {
	  var _questionIndex = 0;

	  void _answerQuestion() {
		setState(() {
		  _questionIndex = _questionIndex + 1;
		});
		print(_questionIndex);
	  }

	  @override
	  Widget build(BuildContext context) {
		var questions = [
		  {
			'questionText': 'What\'s your favorite color?',
			'answers': ['Black', 'Red', 'Green', 'White'],
		  },
		  {
			'questionText': 'What\'s your favorite animal?',
			'answers': ['Rabbit', 'Snake', 'Elephant', 'Lion'],
		  },
		  {
			'questionText': 'Who\'s your favorite instructor?',
			'answers': ['Max', 'Max', 'Max', 'Max'],
		  },
		];
		return MaterialApp(
		  home: Scaffold(
			appBar: AppBar(
			  title: Text('My First App'),
			),
			body: Column(
			  children: [
				Question(
				  questions[_questionIndex]['questionText'],
				),
				...(questions[_questionIndex]['answers'] as List<String>)
					.map((answer) {
				  return Answer(_answerQuestion, answer);
				}).toList()
			  ],
			),
		  ),
		);
	  }
	}

#### question.dart
	import 'package:flutter/material.dart';

	class Question extends StatelessWidget {
	  final String questionText;

	  Question(this.questionText);

	  @override
	  Widget build(BuildContext context) {
		return Container(
		  width: double.infinity,
		  margin: EdgeInsets.all(10),
		  child: Text(
			questionText,
			style: TextStyle(fontSize: 28),
			textAlign: TextAlign.center,
		  ),
		);
	  }
	}

#### answer.dart

	import 'package:flutter/material.dart';

	class Answer extends StatelessWidget {
	  final Function selectHandler;
	  final String answerText;

	  Answer(this.selectHandler, this.answerText);

	  @override
	  Widget build(BuildContext context) {
		return Container(
		  width: double.infinity,
		  child: RaisedButton(
			color: Colors.blue,
			textColor: Colors.white,
			child: Text(answerText),
			onPressed: selectHandler,
		  ),
		);
	  }
	}