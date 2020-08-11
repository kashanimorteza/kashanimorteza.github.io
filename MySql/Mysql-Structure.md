<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>

# [<span style="color:black;">Mysql Programming</span>](Mysql.md)
[Basic](Mysql-Basic.md) | [Structure](Mysql-Structure.md) | [Script](Mysql-Script.md)






<div class="md1"></div>

## Data Type







<div class="md0"></div>


## Database
	CREATE DATABASE Forex;



































* Numbers

* Strings

* Booleans




<div class="md0"></div>

## Data Type
	var name = 'Smith';
	
	
	String name = 'Smith';
	
	
	dynamic x;	
	x = "tom"; print(x);	
	x = 1; print(x);	
	x = true; print(x);




<div class="md0"></div>




## Data structures 
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
	
#### Generics 
	-------------- (Generic List)
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
	
	
	-------------- (Generic Set)
	Set set = <String>{};
		set.add('a'); 
		set.add('a'); 
		set.add('a'); 
	print(set);

	
	Set set = <String>{'a','a','a'};
	print(set);
	
	
	-------------- (Generic Map)
	Map<String,int> map = new Map();
	map['Usrname'] = 1; 
    map['Password'] = 2;
	print(map);
	
	
	Map<String,int> map = {'Usrname':1,'Password':2};
	print(map);	
	
	
	

<div class="md0"></div>




## Function 

	-------------- (The main() function)	
	void main()
	{
		print('Function 1');
	}
		
	main() => print('Function 2');
	
	
	-------------- (Get Parameter)	
	main() => MyFunction('Function 3');	
	void MyFunction(String name)
	{
		print(name);
	}	
	
	main() => MyFunction('Function 3');	
	MyFunction(String name) => print(name);		


	-------------- (Return Value)	
	main() => print(MyFunction('Morteza'));	
	String MyFunction(String name)
	{
		return 'Hello ' +name;
	}
		
	main() => print(MyFunction('Morteza'));	
	MyFunction(String name) => 'Hello ' +name;	
	
	
	-------------- (Positional parameters)		
	main() => MyFunction(name:'Morteza',family:'Kashani');	
	String MyFunction({String name,String family})
	{
		print(name + ' '+ family);
	}
	
	
	-------------- (Default parameter values)	
	main() => MyFunction(family:'Kashani');	
	String MyFunction({String name='ali',String family})
	{
		print(name + ' '+ family);
	}
	
	
	-------------- (Pass a function as a parameter to another function)		
	main() {	
		var list = [1, 2, 3];
		list.forEach(printElement);
	}	
		
	void printElement(int element) {
		print(element);
	}
	
	
	-------------- (Anonymous functions)	
	main() {	
		var list = ['apples', 'bananas', 'oranges'];
		list.forEach((item) {
			print('${list.indexOf(item)}: $item');
		});
	}	
	
	
	
	
	
	

<div class="md0"></div>






## Operators
#### Arithmetic 
#### Relational 
#### Type test 
#### Bitwise 
#### Assignment 
#### Logical 




<div class="md0"></div>




## Control Flow

#### Loop

#### Decision Making


<div class="md0"></div>





## OOP
#### Inheritance




<div class="md0"></div>


## Asynchronous



<div class="md0"></div>




## Library



	
<div class="md0"></div>




## Package



	
<div class="md0"></div>




## Debugging



	
<div class="md0"></div>