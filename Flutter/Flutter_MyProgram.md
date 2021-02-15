<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Flutter My Program</span>](Flutter.md)
[Diagram](Flutter-Diagram.md) |
[Basic](Flutter-Basic.md) |
[Structure](Flutter-Structure.md) |
[Script](Flutter-Script.md) |
[My Library](Flutter-MyLibrary.md) |
[My Program](Flutter_MyProgram.md)


<div class="md1"></div>

## My Application 1
#### main.dart
	import 'package:flutter/material.dart';
	import './widgets/transaction.dart';

	void main() => runApp(MyApp());

	class MyApp extends StatelessWidget {
	  @override
	  Widget build(BuildContext context) {
		return MaterialApp(
		  home: Scaffold(
			appBar: AppBar(
			  title: Text('My Application 1'),
			),
			body: Column(
			  crossAxisAlignment: CrossAxisAlignment.stretch,
			  children: <Widget>[Transaction()],
			),
		  ),
		);
	  }
	}
	
#### transaction.dart
	import 'package:flutter/material.dart';
	import '../models/transaction.dart';
	import './transaction_add.dart';
	import './transaction_list.dart';

	class Transaction extends StatefulWidget {
	  @override
	  _TransactionState createState() => _TransactionState();
	}

	class _TransactionState extends State<Transaction> {
	  final List<TransactionModel> _userTransactions = [];

	  void _addNewTransaction(String txTitle, double txAmount) {
		print('translation : _TransactionState : _addNewTransaction');
		
		final newTx = TransactionModel(
		  id: DateTime.now().toString(),
		  title: txTitle,
		  amount: txAmount,
		  date: DateTime.now(),
		);

		setState(() {
		  print('translation : _TransactionState : setState');
		  _userTransactions.add(newTx);
		  
		});
	  }

	  @override
	  Widget build(BuildContext context) {
		print('translation : _TransactionState : build');
		return Column(
		  children: <Widget>[
			TransactionAdd(_addNewTransaction),
			TransactionList(_userTransactions),
		  ],
		);
	  }
	}
	
#### transaction_list.dart
	import 'package:flutter/material.dart';
	import 'package:intl/intl.dart';
	import '../models/transaction.dart';
	import '../myclass.dart';

	class TransactionList extends StatelessWidget {
	  final List<TransactionModel> _userTransactions;
	  final MyClass myClass = new MyClass();

	  TransactionList(this._userTransactions);

	  @override
	  Widget build(BuildContext context) {
		print('translation_list : TransactionList : build');
		return Column(
		  children: _userTransactions.map((val) {
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
					child: myClass.myText(id: 1, text: '\$${val.amount}', style: 3),
				  ),
				  Column(
					crossAxisAlignment: CrossAxisAlignment.start,
					children: <Widget>[
					  myClass.myText(id: 1, text: val.title, style: 2),
					  myClass.myText(
						  id: 1,
						  text: DateFormat('yyyy-MM-dd HH:mm:ss').format(val.date),
						  style: 1),
					],
				  ),
				],
			  ),
			);
		  }).toList(),
		);
	  }
	}


#### transaction_add.dart
	import 'package:flutter/material.dart';

	class TransactionAdd extends StatelessWidget {
	  final Function addTx;
	  final titleController = TextEditingController();
	  final amountController = TextEditingController();

	  TransactionAdd(this.addTx);

	  @override
	  Widget build(BuildContext context) {
		print('translation_list : TransactionAdd : build');
		return Card(
		  elevation: 5,
		  child: Container(
			padding: EdgeInsets.all(10),
			child: Column(
			  crossAxisAlignment: CrossAxisAlignment.end,
			  children: <Widget>[
				TextField(
				  decoration: InputDecoration(labelText: 'Title'),
				  controller: titleController,              
				),
				TextField(
				  decoration: InputDecoration(labelText: 'Amount'),
				  controller: amountController,              
				),
				FlatButton(
				  child: Text('Add Transaction'),
				  textColor: Colors.purple,
				  onPressed: () {
					addTx(
					  titleController.text,
					  double.parse(amountController.text),
					);
				  },
				),
			  ],
			),
		  ),
		);
	  }
	}							


#### transaction_model.dart
	import 'package:flutter/foundation.dart';

	class TransactionModel {
	  final String id;
	  final String title;
	  final double amount;
	  final DateTime date;

	  TransactionModel({
		@required this.id,
		@required this.title,
		@required this.amount,
		@required this.date,
	  });
	}

#### myclass.dart
	import 'package:flutter/material.dart';

	class MyClass {
	  Text myText({int id, String text, int style}) {
		Text t;
		switch (id) {
		  case 1:
			t = Text(
			  text,
			  style: myTextStyle(style),
			);
		}

		return t;
	  }

	  TextStyle myTextStyle(int id) {
		TextStyle ts;

		switch (id) {
		  case 1:
			ts = TextStyle(
			  color: Colors.red,
			);
			break;
		  case 2:
			ts = TextStyle(
			  fontSize: 16,
			  fontWeight: FontWeight.bold,
			);
			break;

		  case 3:
			ts = TextStyle(
			  fontWeight: FontWeight.bold,
			  fontSize: 20,
			  color: Colors.purple,
			);
			break;
		}

		return ts;
	  }
	}



