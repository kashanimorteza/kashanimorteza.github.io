<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C;font-size: 16px;}
.blue{color:#3498DB;font-size: 14px;}
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
<a href="#class">Class</a> - 
<a href="#object">Object</a> - 
<a href="#field ">Field</a> - 
<a href="#this">This</a> - 
<a href="#constructor">Constructor</a> - 
<a href="#setter--getter">Setter/Getter</a> - 
<a href="#inheritance">Inheritance</a> - 
<a href="#interface">Interface</a> - 
<a href="#abstract">Abstract</a> - 
<a href="#polymorphism">Polymorphism</a> - 



<div class="md1"></div>

## Class

	class User 
	{
		String name;

		void say() 
		{
			print('hello User');
		}
	}



<div class="md0"></div>

## Object

#### <span class="red">General</span>

	void main() 
	{
		User morteza = new User();
		
		morteza.name = "morteza";
		print(morteza.name);
		morteza.say();
	}

#### <span class="red">The Cascade operator</span>

	class Student 
	{
		void method1() 
		{
			print("method 1");
		}

		void method2() 
		{
			print("method 2");
		}
	}

	void main() 
	{
		new Student()
			..method1()
			..method2();
	}


<div class="md0"></div>

## Field

#### <span class="red">General</span>

#### <span class="blue">lib.dart</span>

	class User 
	{
		String name;
	}

#### <span class="blue">main.dart</span>

	import './lib.dart';

	void main() 
	{
		User u =new User();
		u.name='morteza';
		print(u.name);
	}

#### <span class="red">Private</span>

#### <span class="blue">lib.dart</span>

	class User 
	{
		String _name;
	}

#### <span class="blue">main.dart</span>

	import './lib.dart';

	void main() 
	{
		User u =new User();
		u.
	}

#### <span class="red">Static</span>

#### <span class="blue">lib.dart</span>

	class User 
	{
		static String name;
	}

#### <span class="blue">main.dart</span>

	import './lib.dart';

	void main() 
	{
		User.name='morteza';
		print(User.name);
	}
	




<div class="md0"></div>

## This

#### <span class="blue">lib.dart</span>

	class User 
	{
		String msg;

		void Say(msg) 
		{
			this.msg = msg + '-' + msg;
			print(msg);
			print(this.msg);
		}
	}


#### <span class="blue">main.dart</span>

	import './lib.dart';

	void main() 
	{
		User morteza = new User();
		morteza.Say('morteza');
	}





<div class="md0"></div>

## Constructor

#### <span class="red">Example 1</span>

	class User 
	{
		String name;
		String family;
		int age;

		User(String name, String family, int age) 
		{
			this.name = name;
			this.family = family;
			this.age = age;
		}
	}

	void main()
	{
		User morteza = new User('morteza', 'kashani', 35);
		print(morteza.name);
	}

#### <span class="red">Example 2</span>

	class User 
	{
		String name;
		String family;
		int age;

		User(String this.name, String this.family, int this.age);
	}

	void main() 
	{
		User morteza = new User('morteza', 'kashani', 35);
		print(morteza.name);
	}

#### <span class="red">Named Constructors</span>

	class User 
	{
		String name;
		String family;
		int age;

		User(String this.name, String this.family, int this.age);
		User.initName(String this.name);
	}

	void main() 
	{
		User morteza = new User.initName('morteza');
		print(morteza.name);
	}









<div class="md0"></div>

## Setter / Getter

#### <span class="blue">lib.dart</span>

	class User 
	{
		int _age;

		void set usr_age(int age)
		{
			this._age = age+1;
		}

		int get usr_age 
		{
			return _age;
		}
	}

#### <span class="blue">main.dart</span>

	import './lib.dart';

	void main() 
	{
		User morteza = new User();
		morteza.usr_age = 10;
		print(morteza.usr_age);
	}








<div class="md0"></div>

## Inheritance

#### General

	class Car 
	{
		Car() 
		{
			print("You are inside Car constructor!!");
		}

		void Drive() 
		{
			print('Car is driving ...');
		}
	}

	class Benz extends Car 
	{
		Benz() 
		{
			print("You are inside Benz constructor!!");
		}
	}

	void main() 
	{
		Benz b = new Benz();
		b.Drive();
	}

#### Super
	class Car 
	{
		void Drive() 
		{
			print('Car is driving ...');
		}
	}

	class Benz extends Car 
	{
		@override
		void Drive() 
		{
			super.Drive();
		}
	}

	void main() 
	{
		Benz b = new Benz();
		b.Drive();
	}



<div class="md0"></div>

## Interface

 <div align="right" dir="rtl">
  در واقع شِمای کلاس هایی هست که باهاش پیاده سازی می شوند و بهشون میگه که چه چیز هایی رو باید پیاده سازی کنند.
  <br>
    کلاسی که با یک اینترفیس پیاده سازی می شود، باید تمامی متد ها و متغییر ها را دوباره پیاده سازی کند.
   <br>
   کلاس Interface خودش هیچ Method یی را پیاده سازی نمی کند
</div>

	class Human 
	{
		void speak() {}
	}

	class Boy implements Human 
	{
		@override
		void speak() 
		{
			print('boy is speaking ...');
		}
	}

	void main() 
	{
		Boy morteza = new Boy();
		morteza.speak();
	}







<div class="md0"></div>

## Abstract

 <div align="right" dir="rtl">
مثل همون Interface ها هستند با این تفاوت که اگر بدنه method یی در این کلاس پیاده سازی شده باشد دیگه اجباری نیست آن method در کلاس های ارث برده شده پیاده سازی شود
</div>

	abstract class Human 
	{		
		void speak();

		void run()
		{
			print('running...');
		}
	}

	class Boy extends Human 
	{
		@override
		void speak() 
		{
			print('speak bi adab...');
		}
	}

	void main() 
	{
		Boy morteza = new Boy();
		morteza.speak();
		morteza.run();
	}





<div class="md0"></div>

## Polymorphism

#### Method Overriding

	class Car 
	{
		void Drive() 
		{
			print('Car is driving ...');
		}
	}

	class Benz extends Car 
	{
		@override
		void Drive() 
		{	
			print('Benz is driving fast ...');
		}
	}

	void main() 
	{
		Benz b = new Benz();
		b.Drive();
	}



<div class="md0"></div>

## Mixin