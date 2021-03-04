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


# [<span style="color:black;">Dart Language</span>](Dart.md)
[Diagram](Dart-Diagram.md) | 
[Basic](Dart-Basic.md) | 
[Language](Dart-Language.md) | 
[OOP](Dart-Language-OOP.md) | 
[Development](Dart-Development.md) | 
[Script](Dart-Script.md)


<div class="md3"></div>
<a href="#data-type">Data Type</a> - 
<a href="#variable">Variable</a> - 
<a href="#collection">Collection</a> - 
<a href="#enum">Enum</a> - 
<a href="#generic">Generic</a> - 
<a href="#operator">Operator</a> - 
<a href="#control-flow">Control flow</a> - 
<a href="#function">Function</a> -
<a href="#libraries">Libraries</a> -
<a href="#packages">Packages</a>
<div class="md4"></div>
<a href="#asynchronous">Asynchronous</a> -
<a href="#generators">Generators</a> -
<a href="#debugging">Debugging</a> -
<a href="#exceptions">Exceptions</a> -
<a href="#comments">Comments</a>






<div class="md1"></div>

## Data type

String

Number

Boolean






<div class="md0"></div>

## Variable

#### <span class="red">General</span>

	var name = 'morteza'

	String name = 'morteza';  

	String name, familt, job;  
	
#### <span class="red">Dynamic</span>

	dynamic x;

	x = "tom";
	print(x);
	print(x.runtimeType);

	print("----------------");

	x = 1;
	print(x);
	print(x.runtimeType);

	print("----------------");

	x = true;
	print(x);
	print(x.runtimeType);

	print("----------------");

#### <span class="red">Constant</span>

<span class="blue">Final</span>

	void main() 
	{
		final String name = 'morteza';
		print(name);
	}

<span class="blue">Const</span>

	void main() 
	{
		const String name = 'morteza';
		print(name);
	}


<span class="blue">???</span>

	final questions = const 
	[
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







<div class="md0"></div>

## Collection

#### <span class="red">List</span>

	List list = new List(3); 
		list[0] = 'a'; 
		list[1] = 1; 
		list[2] = false;	
	print(list);


	List list = new List(); 
		list.add('a'); 
		list.add(1); 	
		list.add(false); 
	print(list);		
	
	
	List list = ['a',1,false]; 
	
	
	List list = const ['a', 1, false];
		
	List list1 = [1, 2, 3];
	List list2 = [0, ...list1];
	List list3 = [...list2 ,0];
		
		
	var promoActive=true;
	List list = ['Home',if (promoActive) 'Outlet'];
	
	
	List list1 = [1, 2, 3];
	List list2 = ['#0',for (var i in list1) '#$i'];


#### <span class="red">Set</span>

	Set set = {};
		set.add('a'); 
		set.add('a'); 
		set.add(1);     
		set.add(1); 
		set.add(false);     
		set.add(false);
	print(set);
	
	
	Set set = {'a','a',1,1,false,false};
	print(set);

	
	Set set = const {'fluorine','chlorine','bromine','iodine','astatine',};	
	print(set);
	
	
#### <span class="red">Map</span>

	void main() 
	{
		Map map1 = new Map();
		map1['Usrname'] = 'ali';
		map1['Password'] = '123456';
		print(map1);
		print(map1['Usrname']);


		Map map2 = {'Usrname': 'ali', 'Password': '123456'};
		print(map2);

		
		var map3 = 
		[
			{'Usrname': 'ali', 'Password': '123456'},
			{'Usrname': 'msa', 'Password': '123456'},
			{'Usrname': 'upp', 'Password': '123456'}
		];
		print(map3[2]);
		

		var map4  = {'name': 'ali', 'family': ['kashani','moradi','farhadi']};
		print(map4);


		var map5 = 
		[
			{'object': 'car', 'model':  ['benz','bmw','ferari']},
			{'object': 'color', 'model':  ['red','blue','pink']},
			{'object': 'company', 'model':  ['google','ibm','microsoft']}
		];
		print(map5);

	

#### <span class="red">Runes</span>
	.
	
#### <span class="red">Symbol</span> 
	.





<div class="md0"></div>

## Enum





<div class="md0"></div>

## Generic

#### <span class="red">List</span>

	List<String> list = new List<String>(3);
		list[0] = 'a'; 
		list[1] = 'b'; 
		list[2] = 'c';
	print(list);
	
	
	List<String> list = new List<String>();
		list.add('a'); 
		list.add('b'); 	
		list.add('c'); 
	print(list);	
	
#### <span class="red">Set</span>

	Set set = <String>{};
		set.add('a'); 
		set.add('a'); 
		set.add('a'); 
	print(set);

	
	Set set = <String>{'a','a','a'};
	print(set);	
	
#### <span class="red">Map</span>

	Map<String,int> map = new Map();
	map['Usrname'] = 1; 
    map['Password'] = 2;
	print(map);
	
	
	Map<String,int> map = {'Usrname':1,'Password':2};
	print(map);	
	
	
	



<div class="md0"></div>

## Operator

#### Arithmetic 

#### Assignment 

#### Relational 

#### Type test 

#### Logical 

#### Bitwise 

#### Conditional 

#### Casecade notation(..) Operators










<div class="md0"></div>

## Control Flow

#### <span class="red">Conditions</span>

<span class="blue">If</span>

	void main() 
	{
		var x = 10;

		if (x > 1) 
		{
			print('value is > 1');
		}

		x > 10 ? print('value is > 10') : print('value is < 10');
	}

<span class="blue">If-else</span>

	void main() 
	{
		var x = 10;

		if (x > 1) 
		{
			print('value is > 1');
		}
		else
		{
			print('value is < 1');
		}
	}



<span class="blue">If else if</span>

	void main() 
	{
		var x = 10;

		if (x > 10) 
		{
			print('value is > 10');
		}
		else if (x == 10) 
		{
			print('value is == 10');
		}
		else
		{
			print('value is < 1');
		}
	}


<span class="blue">Switch</span>

	void main() 
	{
		var x = 3;

		switch (x) 
		{
			case 1:
			print("Value is 1");
			break;
			case 2:
			print("Value is 2");
			break;
			case 3:
			print("Value is 3");
			break;
		}
	}


#### <span class="red">Loop</span>

<span class="blue">for</span>

<span class="blue">while</span>

<span class="blue">do ... while</span>










<div class="md0"></div>

## Function 

#### <span class="red">The main() function</span>

<span class="blue">Way 1</span>

	void main()
	{
		print('Function 1');
	}

<span class="blue">Way 2</span>

	main() => print('Function 2');	

#### <span class="red">Get Parameter</span>

<span class="blue">General</span>

	void main() 
	{
		MyFunction('morteza', 'kashani');
	}

	void MyFunction(String name, String family) 
	{
		print(name + " " + family);
	}		

<span class="blue">Positional parameters</span>

	void main() 
	{
		MyFunction(name: 'morteza', family: 'kashani');
	}

	void MyFunction({String name, String family}) 
	{
		print(name + " " + family);
	}

<span class="blue">Default parameter values</span>

	void main() 
	{
		MyFunction(name: 'morteza');
	}

	void MyFunction({String name, String family = 'kashani'}) 
	{
		print(name + ' ' + family);
	}

#### <span class="red">Return Value</span>
	main() => print(MyFunction('Morteza'));	
	String MyFunction(String name)
	{
		return 'Hello ' +name;
	}
		
	main() => print(MyFunction('Morteza'));	
	MyFunction(String name) => 'Hello ' +name;	
	
#### <span class="red">Pass a function as a parameter to another function</span>	
	main() {	
		var list = [1, 2, 3];
		list.forEach(printElement);
	}	
		
	void printElement(int element) {
		print(element);
	}
		
##### <span class="red">Anonymous functions</span>
	main() {	
		var list = ['apples', 'bananas', 'oranges'];
		list.forEach((item) {
			print('${list.indexOf(item)}: $item');
		});
	}	













<div class="md0"></div>

## Libraries





<div class="md0"></div>

## Packages







<div class="md0"></div>

## Asynchronous



<div class="md0"></div>

## Generators



	
<div class="md0"></div>

## Debugging

#### assert  

<div align="right" dir="rtl">
 فرض کن میخوای بدونی که اگه به متغییر a  مقدار اولیه ندیم، مقدار اولیه  متغیر a چه خواهد شد ؟
<div class="md4"></div>
 اگر شرط assert درست باشد، برنامه error نمی دهد و اگر شرط assert درست نباشد برنامه error  می دهد
</div>
<div class="md4"></div>

	int a;
	assert(a == null);

 <div align="right" dir="rtl">
 در این مثال، برنامه با error مواجه نمی شود چون شرط assert درست است  یعنی مقدار اولیه متغییر null ،a است	
</div>







<div class="md0"></div>

## Exceptions

#### Throw

#### Catch

#### Finally  






<div class="md0"></div>

## Comments

#### Single-line 

#### Multi-line 

#### Documentation  