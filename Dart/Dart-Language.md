<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Dart Language</span>](Dart.md)
[Diagram](Dart-Diagram.md) | 
[Basic](Dart-Basic.md) | 
[Language](Dart-Language.md) | 
[Development](Dart-Development.md) | 
[Script](Dart-Script.md)


<div class="md3"></div>
<a href="#data-type">Data Type</a> - 
<a href="#variable">Variable</a> - 
<a href="#define-variable">Define Variable</a> - 
<a href="#generics">Generics </a> - 
<a href="#conditions">Conditions</a> - 
<a href="#loop">Loop</a> - 
<a href="#operators">Operators</a> - 
<a href="#function">Function</a>
<div class="md4"></div>
<a href="#oop">OOP</a> -
<a href="#libraries">Libraries</a> -
<a href="#packages">Packages</a> -
<a href="#asynchronous">Asynchronous</a> -
<a href="#generators">Generators</a> -
<a href="#debugging">Debugging</a> -
<a href="#exceptions">Exceptions</a> -
<a href="#comments">Comments</a>



<div class="md1"></div>

## Data type

numbers

strings

booleans

lists (also known as arrays)

sets

maps

runes (for expressing Unicode characters in a string)

symbols




<div class="md0"></div>

## Variable

General

Dynamic

Final

Const




<div class="md0"></div>

## Define Variable

#### General

	var name = 'Smith';	
	String name = 'Smith';
	
#### Dynamic

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

#### Final

	final name = 'Bob';

#### Const

	const bar = 1000000;

#### List

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


#### Set

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
	
	
#### Map
	Map map = new Map();
	map['Usrname'] = 'u'; 
    map['Password'] = 1; 
	print(map);
	
	
	Map map = {'Usrname':'u','Password':1};
	print(map);	
	

#### Runes
	.
	
#### Symbol 
	.
	




<div class="md0"></div>

## Generics 
#### List
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
	
	
#### Set
	Set set = <String>{};
		set.add('a'); 
		set.add('a'); 
		set.add('a'); 
	print(set);

	
	Set set = <String>{'a','a','a'};
	print(set);
	
	
#### Map
	Map<String,int> map = new Map();
	map['Usrname'] = 1; 
    map['Password'] = 2;
	print(map);
	
	
	Map<String,int> map = {'Usrname':1,'Password':2};
	print(map);	
	
	
	



<div class="md0"></div>

## Conditions

#### If / else

#### Switch






<div class="md0"></div>

## Loop

#### for

#### while

#### do ... while




<div class="md0"></div>

## Operators

#### Arithmetic 

#### Relational 

#### Type test 

#### Bitwise 

#### Assignment 

#### Logical 





<div class="md0"></div>

## Function 

#### <span style="color:red;">The main() function</span>

<span style="color:blue;">Way 1</span>

	void main()
	{
		print('Function 1');
	}

<span style="color:blue;">Way 2</span>

	main() => print('Function 2');
	
	
#### Get Parameter
	main() => MyFunction('Function 3');	
	void MyFunction(String name)
	{
		print(name);
	}	
	
	main() => MyFunction('Function 3');	
	MyFunction(String name) => print(name);		


#### Return Value	
	main() => print(MyFunction('Morteza'));	
	String MyFunction(String name)
	{
		return 'Hello ' +name;
	}
		
	main() => print(MyFunction('Morteza'));	
	MyFunction(String name) => 'Hello ' +name;	
	
	
#### Positional parameters	
	main() => MyFunction(name:'Morteza',family:'Kashani');	
	String MyFunction({String name,String family})
	{
		print(name + ' '+ family);
	}
	
	
#### Default parameter values
	main() => MyFunction(family:'Kashani');	
	String MyFunction({String name='ali',String family})
	{
		print(name + ' '+ family);
	}
	
	
#### Pass a function as a parameter to another function		
	main() {	
		var list = [1, 2, 3];
		list.forEach(printElement);
	}	
		
	void printElement(int element) {
		print(element);
	}
	
	
#### Anonymous functions
	main() {	
		var list = ['apples', 'bananas', 'oranges'];
		list.forEach((item) {
			print('${list.indexOf(item)}: $item');
		});
	}	
	
	
	

<div class="md0"></div>

## OOP

#### Inheritance




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