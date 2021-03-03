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
<a href="#static">Static</a> - 
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

#### General
	void main() 
	{
		User morteza = new User();
		
		morteza.name = "morteza";
		print(morteza.name);
		morteza.say();
	}

#### The Cascade operator

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

## Static
	class User 
	{
		static String msg;

		void say() 
		{
			print('hello $msg');
		}
	}

	void main() 
	{
		User.msg = 'User class';
		print(User.msg);
	}






<div class="md0"></div>

## This
	class User 
	{
		String msg;

		User(msg) 
		{
			this.msg = msg + '-' + msg;
			print(msg);
			print(this.msg);
		}
	}

	void main() 
	{
		User u = new User('test');
	}





<div class="md0"></div>

## Constructor

#### Example 1

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

#### Example 2

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

##### Named Constructors

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

	class User 
	{
		String name;
		String family;
		int age;

		void set usr_age(int age)
		{
			this.age = age;
		}

		int get usr_age 
		{
			return age;
		}
	}

	void main() 
	{
		User morteza = new User();
		morteza.usr_age = 11;
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