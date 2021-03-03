<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C;font-size: 20px;}
.blue{color:#3498DB}
.green{color:##28B463}
</style>


# [<span style="color:black;">Flutter Script</span>](Flutter.md)
[Diagram](Flutter-Diagram.md) |
[Basic](Flutter-Basic.md) |
[Structure](Flutter-Structure.md) |
[Script](Flutter-Script.md) |
[My Library](Flutter-MyLibrary.md) |
[My Program](Flutter_MyProgram.md)



<div class="md3"></div>
<a href="#1">1</a> - 
<a href="#2">2</a> - 
<a href="#3">3</a> - 
<a href="#4">4</a> - 
<a href="#5">5</a> - 
<a href="#6">6</a> - 
<a href="#7">7</a> - 
<a href="#8">8</a> - 
<a href="#9">9</a> - 
<a href="#10">10</a> - 
<a href="#general">General</a>





<div class="md1"></div>

#### <span class="red">1</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(Text("Welcome", textDirection: TextDirection.ltr,));
	}



<div class="md1"></div>

#### <span class="red">2</span>
	
	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatelessWidget 
	{
		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(home: Text('hello'),);
		}
	}


<div class="md1"></div>

#### <span class="red">3</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatelessWidget 
	{
		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
				appBar: AppBar(title: Text("My First Application 1")),
				body: Text('welcome to the flutter'),
				)
			);
		}
	}


<div class="md1"></div>

#### <span class="red">4</span>

<span class="blue">Adding Layout Widgets</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatelessWidget 
	{
		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
					appBar: AppBar(title: Text("My First Application 1")),
					body: Column(
						children: [
						Text('This is a seccond text'),
						RaisedButton(child: Text('btn 1'), onPressed: null),
						Text('This is a first text'),
						RaisedButton(child: Text('btn 2'), onPressed: null),
						],
					),
				)
			);
		}
	}


<div class="md1"></div>

#### <span class="red">5</span>

<span class="blue">Connecting Functions & Buttons</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatelessWidget 
	{
		void answer() 
		{
			print('button 1 is clicked');
		}

		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
					appBar: AppBar(title: Text("My First Application 1")),
					body: Column(
						children: [
						Text('This is text 1'),
						RaisedButton(child: Text('btn 1'), onPressed: answer),
						Text('This is text 2'),
						RaisedButton(child: Text('btn 2'),onPressed: () => print('button 2 is clicked')),
						Text('This is text 3'),
						RaisedButton(child: Text('btn 3'),onPressed: () {print('button 3 is clicked');}),
						],
					),
				)
			);
		}
	}


<div class="md1"></div>

#### <span class="red">6</span>

<span class="blue">Updating Correctly with Stateful Widgets</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatefulWidget 
	{
		@override
		_MyAppState createState() => _MyAppState();
	}

	class _MyAppState extends State<MyApp> 
	{
		var item = 0;

		void answer() 
		{
			setState(() {item = item + 1;});

			print(item.toString());
		}

		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
			appBar: AppBar(title: Text("My First Application 1")),
			body: Column(
				children: [
				Text(item.toString()),
				RaisedButton(child: Text('add item'), onPressed: answer),
				],
			),
			));
		}
	}



<div class="md1"></div>

#### <span class="red">7</span>

<span class="blue">Creating a New, Custom Widget</span>

item.dart

	import 'package:flutter/material.dart';

	class MyItem extends StatelessWidget 
	{
		int item;

		MyItem(this.item);

		@override
		Widget build(BuildContext context) 
		{
			return Text(item.toString());
		}
	}

main.dart

	import 'package:flutter/material.dart';
	import './item.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatefulWidget 
	{
		@override
		_MyAppState createState() => _MyAppState();
		}

		class _MyAppState extends State<MyApp> 
		{
		var item = 0;

		void answer() 
		{
			setState(() {item = item + 1;});

			print(item.toString());
		}

		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
			appBar: AppBar(title: Text("My First Application 1")),
			body: Column(children: 
			[
				MyItem(item),ElevatedButton(child: Text('add item'), onPressed: answer),
			],
			),
			));
		}
	}



<div class="md1"></div>

#### <span class="red">8</span>

<span class="blue">First Styling & Layouting Steps</span>

	import 'package:flutter/material.dart';

	void main() 
	{
		runApp(MyApp());
	}

	class MyApp extends StatelessWidget 
	{
		@override
		Widget build(BuildContext context) 
		{
			return MaterialApp(
				home: Scaffold(
			appBar: AppBar(title: Text("My First Application 1")),
			body: Container(
				margin: EdgeInsets.all(100.0),
				width: double.infinity,
				child: Text('Hello Flutter',
					style: TextStyle(fontSize: 33), 
					textAlign: TextAlign.center),
			),
			));
		}
	}









<div class="md0"></div>

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
	
	-------------------------------------------------------------
	
	import 'package:flutter/material.dart';

	void main() => runApp(MyApp());

	class MyApp extends StatelessWidget {
	  @override
	  Widget build(BuildContext context) {
		return MaterialApp(
		  title: 'Flutter App',
		  home: MyHomePage(),
		);
	  }
	}

	class MyHomePage extends StatelessWidget {
	  @override
	  Widget build(BuildContext context) {
		return Scaffold(
		  appBar: AppBar(
			title: Text('Flutter App'),
		  ),
		  body: Column(
			children: <Widget>[
			  Container(
				width: double.infinity,
				child: Card(
				  color: Colors.blue,
				  child: Text('CHART!'),
				  elevation: 5,
				),
			  ),
			  Card(
				child: Text('LIST OF TX'),
			  ),
			],
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
	



	
<div class="md0"></div>





	
## Example 1
#### main.dart
	import 'package:flutter/material.dart';
	import './transaction.dart';
	import './myclass.dart';

	void main() => runApp(MyApp());

	class MyApp extends StatelessWidget {
	  @override
	  Widget build(BuildContext context) {
		return MaterialApp(
		  title: 'Flutter App',
		  home: MyHomePage(),
		);
	  }
	}

	class MyHomePage extends StatelessWidget {
	  
	  MyClass m = new MyClass();

	  final List<Transaction> transactions = [
		Transaction(
		  id: 't1',
		  title: 'New Shoes',
		  amount: 69.99,
		  date: DateTime.now(),
		),
		Transaction(
		  id: 't2',
		  title: 'Weekly Groceries',
		  amount: 16.53,
		  date: DateTime.now(),
		),
	  ];

	  @override
	  Widget build(BuildContext context) {
		return Scaffold(
		  appBar: AppBar(
			title: Text('Flutter App'),
		  ),
		  body: Column(
			mainAxisAlignment: MainAxisAlignment.spaceAround,
			crossAxisAlignment: CrossAxisAlignment.stretch,
			children: <Widget>[
			  Column(
				children: transactions.map((lits_item) {
				  return Card(
					color: Color.fromARGB(0xFF, 0x42, 0xA5, 0xF5),
					child: Row(
					  children: <Widget>[
						Container(
						  margin: EdgeInsets.symmetric(
							vertical: 10,
							horizontal: 15,
						  ),
						  decoration: BoxDecoration(
							border: Border.all(
							  color: Colors.purple,
							  width: 2,
							),
						  ),
						  padding: EdgeInsets.all(10),
						  child: m.myText(
							  id: 1, text: lits_item.amount.toString(), style: 3),
						),
						Column(
						  crossAxisAlignment: CrossAxisAlignment.start,
						  children: <Widget>[
							m.myText(id: 1, text: lits_item.title, style: 2),
							m.myText(
								id: 1, text: lits_item.date.toString(), style: 1),
						  ],
						),
					  ],
					),
				  );
				}).toList(),
			  ),
			],
		  ),
		);
	  }
	}


#### transaction.dart
	import 'package:flutter/foundation.dart';

	class Transaction {
	  final String id;
	  final String title;
	  final double amount;
	  final DateTime date;

	  Transaction({
		@required this.id,
		@required this.title,
		@required this.amount,
		@required this.date,
	  });
	}


#### myclass.dart
	import 'package:flutter/cupertino.dart';
	import 'package:flutter/material.dart';

	class MyClass {
	  
	  Text myText({int id, String text, int style}) {
		switch (id) {
		  case 1:
			return Text(
			  text,
			  style: myTextStyle(style),
			);
		}
	  }

	  TextStyle myTextStyle(int id) {
		switch (id) {
		  case 1:
			return TextStyle(
			  color: Colors.red,
			);
		  case 2:
			return TextStyle(
			  fontSize: 16,
			  fontWeight: FontWeight.bold,
			);
		  case 3:
			return TextStyle(
			  fontWeight: FontWeight.bold,
			  fontSize: 20,
			  color: Colors.purple,
			);
		}
	  }
	}
