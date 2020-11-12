<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">MarketPlace Subject</span>](MarketPlace.md)
[Target](MarketPlace-Target.md) |
[Subject](MarketPlace-Subject.md) | 
[Politics](MarketPlace-Politics.md) |
[Resources](MarketPlace-Resources.md) | 
[Requirement](MarketPlace-Requirement.md) | 
[Structure](MarketPlace-Structure.md)


<div class="md3"></div>
<a href="#data-type" >Data Type</a> - 
<a href="#Variable" >Variable</a> - 
<a href="#data-structures" >Data structures</a> - 
<a href="#Operators">Operators</a> - 
<a href="#Conditions">Conditions</a> - 
<a href="#loop">Loop</a> - 
<a href="#function" >Function</a> -
<a href="#module">Module</a> -
<a href="#API">API</a> -
<a href="#Database">Database</a> -
<a href="#Error">Error</a>
<div class="md4"></div>
<a href="#oop" >OOP</a> -
<a href="#Iterator">Iterator</a> - 
<a href="#Generator">Generator</a> - 
<a href="#decorator">Decorator</a> -
<a href="#Multi-threading">Multi Threading</a> - 
<a href="#Multi-Processing">Multi Processing</a> -
<a href="#Example">Example</a>







<div class="md1"></div>

## Data Type

#### String

	item1 = "Mohammad"
	print(type(item1))

#### Numeric : Integer

	item2 = 10
	print(type(item2))

#### Numeric : Float

	item3 = 10.02
	print(type(item3))

#### Boolean

	item4 = True
	print(type(item4))

#### Complex

	item5 = 5j
	print(type(item5))

#### Convert Data Type

	print(str(item2))
	print(int(item3))
	print(float(item2))	













<div class="md0"></div>

## Variable

#### Variable Assignment

	a = 1
	b = 2
	c = "Hey"
	a, b, c = 1, 2, "Hey"
	a = b = c = "Hey"

#### Name mangling

	name = 'aaa'    # normal case definition	
	Name = 'bbbb'   # case sensitive definition			
	my_age = 20     # snak case definition	
	myAge = 20      # camel case definition		
	MyAge = 20      # upper camel case definition
	_name = 'cccc'  # no displey 	
	__name = 'cccc' # private
	




	





<div class="md0"></div>
	
## Data structures

#### List	

	#---------------------------------------------[Normal List]
	person_info = ['sara','majd',11,True]

	#-----Example 1
	person_info.append('yahoo')

	#-----Example 2
	print(person_info)

	#-----Example 3
	print(person_info[0])
	print(len(person_info))
	print("majd" in person_info )

	#-----Example 4
	for item in person_info:
		print(item)
<span><span>

	#---------------------------------------------[Comprehension List]
	#-----Example 1
	myNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
	print(myNumbers)
	doubled_numbers = [num * 2 for num in myNumbers]
	print(doubled_numbers)
	
	#-----Example 2
	myName = "Mohammad"
	namesCharacters = [char.upper() for char in myName]
	print(namesCharacters)

	#-----Example 3
	myNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
	even = [num for num in myNumbers if num % 2 == 0]
	print(even)
	odd = [num for num in myNumbers if num % 2 != 0]
	print(odd)

	#-----Example 4
	myNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]	
	newList = [num * 2 if num % 2 == 0 else num * 3 for num in myNumbers]
	print(newList)
<span><span>

	#---------------------------------------------[Nested List]
	myList = [[1, 2, 3], [4, 5, 6]]

	#-----Example 1
	print(myList[1][1])

	#-----Example 2
	for li in myList:
		for num in li:
			print(num)

	#-----Example 3
	copyList = [li for li in myList]
	print(copyList)	
	
	#-----Example 4	
	copyList = [[print(l) for l in li] for li in myList]		

	#-----Example 5
	myList = [num for num in range(1, 4)]
	print(myList)
	myNestedList = [['X' if newNum % 2 == 0 else 'O' for newNum in range(1, 4)] for num in range(1, 4)]
	print(myNestedList)
	
#### Dictionary

	myDictionary = {"name": 'sara', "family": 'majd', "age": 11, "active": True}
	
	#-----Example 1
	print(myDictionary)
	print(myDictionary["name"])
	print(myDictionary.get("name"))
	print(len(myDictionary))
	print("sara" in myDictionary["family"])

	#-----Example 2
	for item in myDictionary.values():
		print(item)

	#-----Example 3
	myDictionary  = dict.fromkeys(["name","family"], "unknown")
	print(myDictionary )
	
	#-----Example 4	
	MyDic = {num: num*2 for num in [1, 2, 3, 4, 5]}
	print(MyDic)

	#-----Example 5
	myDictionary1 = dict(first=1, second=2, third=3)
	myDictionary2 = {key: value ** 2 for key, value in myDictionary1.items()}
	print(myDictionary2)
	
	#-----Example 6
	myDictionary = {num: ("even" if num % 2 == 0 else "odd") for num in [1, 2, 3, 4, 5]}
	print(myDictionary)
	
#### Tuple	

	myTuple1 = tuple([1, 2, 3, 4, 5])
	myTuple2 = (1, 2, 3, 4, 5, 2, (4, 5, 3), 3, 3)
	
	#-----Example 1
	print(myTuple1)
	print(myTuple2)

	#-----Example 2
	locations = {
    (35.67, 45.78): "Tehran",
    (40.30, 69.92): "Shiraz"
	}
	print(locations[(35.67, 45.78)])

	#-----Example 3	
	myTuple = (1, 2, 3, 4, 5, 2, (4, 5, 3), 3, 3)
	for num in myTuple2:
		print(num)

#### Set

	mySet = {1, 2, 3, 4, 4, 4, 4, 4, 2, 2, 5}

	#-----Example 1
	print(mySet)
	print(1 in mySet)

	#-----Example 2	
	for item in mySet:
		print(item)

#### Range

	myRange = range(0, 15, 2)
	myList = list(range(0, 15, 2))
	print(myList)	

#### frozenset	
	.
	









<div class="md0"></div>
	
## Operators 










<div class="md0"></div>

## Conditions

#### IF Statement

	userRank = 1

	if userRank == 1:
		print("you got GOLD medal")
	elif userRank == 2:
		print("you got SILVER medal")
	elif userRank == 3:
		print("you got BRONZE medal")
	else:
		print("you got no medal")

#### Expression

	userRank = 1
	print("you got GOLD medal") if userRank == 1 else print("no medal")

#### Truthiness Falsiness	

	number = 3

	if type(number) is int:
		print('this is true')
	else:
		print('this is false')
<span><span>

	list_1 = ['a', 'b', 'c']
	list_2 = list_1
	list_3 = list(list_1)
	
	print(list_1)
	print(list_2)
	print(list_3)

	print('----------------')
	print(list_1 == list_2)
	print(list_1 == list_3)
	print('----------------')
	print(list_1 is list_2)
	print(list_1 is list_3)
<span ><span>

	if 1:
		print('this is true')
	else:
		print('this is false')

	print('----------------')

	if 0:
		print('this is true')
	else:
		print('this is false')

	print('----------------')

	if "":
		print('this is true')
	else:
		print('this is false')

	print('----------------')

	if "a":
		print('this is true')
	else:
		print('this is false')

	print('----------------')

	print('enter your favorite car')
	car = input()
	if car:
		print(f"your favorite car is {car}")








<div class="md0"></div>

## Loop 






	
	
<div class="md0"></div>

## Function 

#### normal function

	def Callme():    
		print('callme')

	Callme()

#### function With Return Value	
	def Callme(name):    
		return name

	print(Callme('morteza'))

#### function With parameters	

	def Callme(name):    
		print(name)

	Callme('morteza')

#### function With Default parameter values	

	def Callme(name,family='kashani'):    
		print(name + ' '+ family)

	Callme('morteza')
	Callme('morteza','tavakolian')

#### function With Definition parameters	

	def Callme(name,family):    
		print(name + ' '+ family)

	Callme(family="kashani",name="morteza")

#### function With dynamic parameters

	def sum_all_numbers(*args):
		print(type(args))
		print(args)
		
		total = 0
		for num in args:
			total += num
		return total

	print(sum_all_numbers(1, 2, 3, 4, 5, 6))
	
	#----uppack list to parameter
	numbers = [1, 2, 3, 4, 5, 6]
	print(sum_all_numbers(*numbers))
	
	---------------------------------------------	
	
	def showUserInfo(**kwargs):
		print(type(kwargs))
		print(kwargs)

		for key, value in kwargs.items():
			print(f"{key} : {value}")

	showUserInfo(name="mohammad", family="orodookhani", age=23, email="moh96ordo@gmail.com")

	#----uppack dictionary to parameter
	info = {"name": "mohammad", "family": "orodookhani", "age": 23, "email": "moh96ordo@gmail.com"}
	print(showUserInfo(**info))
	
	---------------------------------------------
	
	def display_info(a, b, *args, defPara="defalut", **kwargs):
    return [a, b, args, defPara, kwargs]

	print(display_info(1, 2, 6, first_name="mohammad", last_name="ordookhani"))		

#### Anonymous functions

	myFuction1 = lambda name: print(name)
	myFuction1('morteza')

	myFuction2 = lambda a,b: a+b
	print(myFuction2(1,4))

#### Built-in function(Map, filter, all, any, sort, reversed, max-min , Len , Abs , Sum و Round , zip)	

	---------------------------------------------[map]
	names = ["mohammad", "sara", "iman", "ali"]
	upperNames = map(lambda name: name.upper(), names)
	print(list(upperNames))	

	people = [
		{'name': 'mohammad', 'family': 'ordookhani', 'age': 23},
		{'name': 'sara', 'family': 'moradi', 'age': 25},
	]
	print(list(map(lambda person: person['family'], people)))
<span><span>

	---------------------------------------------[filter]

	numbers = [1, 2, 3, 4, 5, 6]
	evens = filter(lambda num: num % 2 == 0, numbers)
	print(list(evens))


	users = [
		{'name': 'mohammad', 'shopCart': []},
		{'name': 'sara', 'shopCart': ['kotlin', 'vue']},
		{'name': 'iman', 'shopCart': []}
	]
	result = filter(lambda user: not user['shopCart'], users)
	print(list(result))
<span><span>

	---------------------------------------------[all]

	numbers = [2, 4, 6, 7]
	print(all([num % 2 == 0 for num in numbers]))
<span><span>

	---------------------------------------------[any]

	numbers = [2, 4, 6, 8]
	results = [False, False, False, True]
	print(any([num % 2 != 0 for num in numbers]))
<span><span>

	---------------------------------------------[sorted]

	#----example 1
	numbers = [1, 5, 3, 11, 2]
	print(sorted(numbers))

	#----example 2	
	numbers = [1, 5, 3, 11, 2]
	print(sorted(numbers, reverse=True))

	#----example 3
	users = [
		{'name': 'mohammad', 'family': 'ordookhani', 'age': 23},
		{'name': 'taha', 'family': 'ordookhani', 'age': 40},
		{'name': 'ali', 'family': 'ordookhani', 'age': 30},
		{'name': 'sara', 'family': 'ordookhani', 'age': 80}
	]

	print(sorted(users, key=lambda user: user['age'], reverse=True))
<span><span>

	---------------------------------------------[min max]
	
	#----example 1
	numbers = [3, 6, 8, 13, 4, 90]
	chars = ['a', 't', 'z']
	myName = "mostafa"

	print(max(numbers))
	print(max(chars))
	print(max(myName))

	print(min(numbers))
	print(min(chars))
	print(min(myName))

	#----example 2	
	names = ['mohammad', 'milad', 'akbar', 'sara', 'iman','ali']
	print(max(names, key=lambda n: len(n)))
	print(min(names, key=lambda n: len(n)))
<span><span>

	---------------------------------------------[reverse]
	
	#----example 1
	numbers = [1, 2, 3, 4, 5, 6]
	numbers.reverse()
	print(numbers)

	#----example 2
	numbers = [1, 2, 3, 4, 5, 6]
	print(list(reversed(numbers)))

	#----example 3
	print(list(reversed("hello")))
	print("hell0"[::-1])
<span><span>

	---------------------------------------------[len]
	
	#----example 1
	data1 = "mohammad"
	data2 = [1, 2, 3, 4, 5]
	data3 = (3, 4, 5, 6, 7, 8, 9)

	print(len(data1))
	print(len(data2))
	print(len(data3))

	print(data1.__len__())
	print(data2.__len__())
	print(data3.__len__())

	#----example 2
	class MyList:
		def __init__(self, data):
			self.__data = data

		def __len__(self):
			return 50

	test = MyList([23, 4, 5, 6, 7, 4, 3])
	print(len(test))
<span><span>

	---------------------------------------------[abs]
	number = -5

	print(abs(number))
<span><span>

	---------------------------------------------[sum]
	numbers = [1, 2, 3]

	numbers = (1, 2)

	print(sum(numbers, 10))
<span><span>

	---------------------------------------------[round]
	number = 4.56330480

	print(round(number,2))
<span><span>

	---------------------------------------------[zip]
	#----example 1
	numbers_1 = [1, 2, 3, 4, 5]
	numbers_2 = [5, 6, 7, 8, 9, 10]

	result = zip(numbers_1, numbers_2)

	#print(list(result))
	print(dict(result))

	#----example 2
	myList = [(1, 5), (3, 7), (6, 4), (7, 9)]
	print(list(zip(*myList)))
	
	#----example 3
	students = ["mohammad", "iman", "sara"]
	midterm = [78, 80, 94]
	final = [90, 88, 92]

	finalGrades = {t[0]: max(t[1], t[2]) for t in zip(students, midterm, final)}
	print(finalGrades)

	#----example 4
	students = ["mohammad", "iman", "sara"]
	midterm = [78, 80, 94]
	final = [90, 88, 92]

	average = zip(
		students,
		map(
			lambda pair: (pair[0] + pair[1]) / 2,
			zip(midterm, final)
		)
	)

	print(dict(average))




<div class="md0"></div>

## OOP  
#### Class, Object 
	class User:

		def showFullName(self, userName, userFamily):
			return f"{userName} {userFamily}"

	morteza = User()
	print(morteza.showFullName('morteza','kashani'))	
#### Constructor
	class User:

		classText = "hello"

		def __init__(self, userName, userFamily):
			self.name = userName
			self.family = userFamily

		def showFullName(self):
			return f"{User.classText} {self.name} {self.family}"

	morteza = User('morteza', 'kashani')
	print(morteza.showFullName())

	ali = User('ali', 'arshadi')
	print(ali.showFullName())
#### Class Methods 
	class User:

		def say(self):
			print(self)

		@classmethod
		def run(cls):
			print(cls)

	morteza = User()
	print(morteza.say())

	print(User.run())
<span><span>

	class User:

		def __init__(self, name, family):
			self.name = name
			self.family = family

		def say(self):
			print(self)

		@classmethod
		def run(cls, data):
			name, family = data.split(',')
			return cls(name, family)

	ins = User.run("morteza,kashani")
	print(ins.name, ins.family)
<span><span>

	class User:

		def __init__(self, name, family, age):
			self.name = name
			self.family = family
			self.age = age

		def __repr__(self):
			return f"{self.name} {self.family} is {self.age}"

	me = User('mohammad', 'ordookhani', 24)
	print(me)	
#### Property  
	class Person:

		def __init__(self, name, family, age):
			self.name = name
			self.family = family
			if age >= 0:
				self._age = age
			else:
				self._age = 0

		@property
		def age(self):
			return self._age

		@age.setter
		def age(self, value):
			if value >= 0:
				self._age = value
			else:
				raise ValueError('age can not be negative')

		@property
		def fullName(self):
			return f"{self.name} {self.family}"

		def showFullName(self):
			return f"{self.name} {self.family}"

	me = Person('ali', 'miladi', 23)
	print(me.showFullName())

	me.age = 20
	print(me.fullName)
#### Inheritance 
	class Person:
		classAttribute = "test value"
		def __init__(self, name, family, age):
			self.name = name
			self.family = family
			self.age = age

		def showFullName(self):
			return f"{self.name} {self.family}"

	class User(Person):
		pass

	mohammad = Person('mohammad', 'ordookhani', 24)

	sara = User('sara', 'moradi', 24)
	print(sara.name)
	print(sara.classAttribute)
<span><span>

	---------------------------------------------[super]
	class Person:
		def __init__(self, name, family):
			self.name = name
			self.family = family

		@property
		def fullName(self):
			return f"{self.name} {self.family}"


	class User(Person):
		def __init__(self, name, family, email):
			super().__init__(name, family)
			self.email = email

	sara = User('sara', 'moradi', 'test@test.com')

	print(sara.fullName)
<span><span>

	---------------------------------------------[Multi Inheritance]
	class Person:
		def __init__(self, name):
			print("Person Init")
			self.__name = name

		def sayHello(self):
			return f"hello {self._Person__name} in Person Class"

		def sayBye(self):
			return f"goodbye {self._Person__name}"

	class User:
		def __init__(self, name):
			print("User Init")
			self.__name = name

		def sayHello(self):
			return f"hello {self._User__name} in User Class"


	class Admin(Person, User):
		def __init__(self, name):
			print("admin Init")
			User.__init__(self, 'user name')
			Person.__init__(self, 'person name')

	person_1 = Admin('mohammad')
	print(person_1.sayHello())
	print(person_1.sayBye())

	print(isinstance(person_1, Person))
	print(isinstance(person_1, User))
	print(isinstance(person_1, Admin))
<span><span>

	---------------------------------------------[Method resolution order]
	class A:
		def say_hello(self):
			print("hello MarketPlace in A")

	class B(A):
		pass
		#def say_hello(self):
			#print("hello MarketPlace in B")

	class C(A):
		def say_hello(self):
			print("hello MarketPlace in C")

	class D(B, C):
		pass
		#def say_hello(self):
		# print("hello MarketPlace in D")

	item = D()
	item.say_hello()
#### Polymorphisms
	class Animal:

		def makeSound(self):
			raise NotImplementedError

	class Dog(Animal):
		def makeSound(self):
			return "dog is making sound"

	class Cat(Animal):
		def makeSound(self):
			return "cat is making sound"

	class Worm(Animal):
		def makeSound(self):
			return "worm does not make any sound"


	dog = Dog()
	cat = Cat()
	worm = Worm()

	print(cat.makeSound())
	print(dog.makeSound())
	print(worm.makeSound())
<span><span>

	class IUserService:
		def getAllUsers(self): raise NotImplementedError
		def getUserById(self): raise NotImplementedError
		def createNewUser(self): raise NotImplementedError

	class UserServiceBySql(IUserService):
		def getAllUsers(self):
			print("get all users from sql server")
		def getUserById(self):
			print("get user by id from sql server")
		def createNewUser(self):
			print("create new user from sql server")

	class UserServiceByOracle(IUserService):
		def getAllUsers(self):
			pass
		def getUserById(self):
			pass
		def createNewUser(self):
			pass


	userService = UserServiceBySql()
	userService.getAllUsers()

	userService_by_oracle = UserServiceByOracle()
	userService.getAllUsers() # Error 
<span><span>

	class Person:
		def __init__(self, name, family, age, money):
			self.name = name
			self.family = family
			self.age = age
			self.money = money

		def __repr__(self):
			return f"{self.name} {self.family}"

		def __len__(self):
			return self.age

		def __add__(self, other):
			return self.money + other.money

		def __mul__(self, other):
			return self.money * other.money

		def __truediv__(self, other):
			return self.money / other.money


	person_1 = Person('mohammad', 'ordookhani', 24, 1000)
	person_2 = Person('sara', 'moradi', 18, 2000)

	print(person_1)
	print(len(person_1))
	print(person_1 + person_2)
	print(person_1 * person_2)
	print(person_1 / person_2)















<div class="md0"></div>

## Iterator
#### Example 1
	name1 = 'morteza'
	name2 = iter(name1)

	print(next(name2))
	print(next(name2))
	print(next(name2))
	print(next(name2))
	print(next(name2))
	print(next(name2))
	print(next(name2))
#### Example 2
	numbers1 = [1, 2, 3, 4, 5]
	numbers2 = iter(numbers1)

	print(next(numbers2))
	print(next(numbers2))
	print(next(numbers2))
	print(next(numbers2))
	print(next(numbers2))
##### Example 3
	def my_for(iterable, func):
		iterator = iter(iterable)

		while True:
			try:
				thing = next(iterator)
			except StopIteration:
				break
			else:
				func(thing)


	numbers = [1, 2, 3, 4, 5]

	def square(num):
		print(num ** 2)

	my_for(numbers, square)
##### Example 4
	class Counter:
		def __init__(self, start, end, step=1):
			self.current = start
			self.end = end
			self.step = step

		def __iter__(self):
			return self

		def __next__(self):
			if self.current < self.end:
				num = self.current
				self.current += self.step
				return num
			raise StopIteration
#### Example 5
	class User:
		ActiveUsers = []

		def __init__(self, name, age):
			self.name = name
			self.age = age
			userDict = {'name': name, 'age': age}
			User.ActiveUsers.append(userDict)
			self.index = 0

		def __iter__(self):
			return self

		def __next__(self):
			if self.index < len(User.ActiveUsers):
				person = User.ActiveUsers[self.index]
				self.index += 1
				return person
			raise StopIteration

	person_1 = User('mohammad', 24)
	person_2 = User('sara', 20)
	person_3 = User('ali', 60)

	for person in person_1:
		print(person)

	myCounter = Counter(0, 20, 4)

	for num in myCounter:
		print(num)










<div class="md0"></div>

## Generator  

#### Example 1

	def count_up_to(max):
		count = 1
		while count <= max:
			yield count
			count += 1

	counter = count_up_to(5)

	print(next(counter))  # -> 1
	print(next(counter))  # -> 2
	print(next(counter))  # -> 3
	print(next(counter))  # -> 4
	print(next(counter))  # -> 5

#### As a expression

	myGenerator = (num for num in range(5))
	print(myGenerator)

	print(next(myGenerator))
	print(next(myGenerator))
	print(next(myGenerator))
	print(next(myGenerator))
	print(next(myGenerator))

	print(sum(num for num in range(100000000)))

#### fibonacci with list

	def fib_list(max):  # 10
		nums = []  # [1,1]
		a, b = 0, 1
		while len(nums) < max:
			nums.append(b)
			a, b = b, a + b
		return nums

	fib_list(1000000)

#### fibonacci with generator

	def fib_generator(max):
		x = 0
		y = 1
		count = 0
		while count < max:
			x, y = y, x + y
			yield y
			count += 1

	for num in fib_generator(1000000):
		print(num)














<div class="md0"></div>

## Decorator 

#### Function

	def func1(value):
		return value

#### Send function as a arguman

	def func1(value):
		return value

	def func2(function, num):
		return function(num)

	print(func2(func1,5))

#### Nesting functions

	def myFunction():
		
		def func1():
			return "func1"

		def func2():
			return "func2"

		print(func1()) 
		print(func2()) 

	myFunction()

#### Return functions

	def my_decorator(func):
		def say():
			print('say')
			func()
		return say

	def my_function():
		print('hello')

	test = my_decorator(my_function)
	test()

#### Decorators 1

	def my_decorator(func):
		def say():
			print('say')
			func()
		return say

	@my_decorator
	def my_function():
		print('hello')

	my_function()

#### Decorators 2

	def my_decorator(func):
		def say(name):
			print('say')
			func(name)
		return say

	@my_decorator
	def my_function(name):
		print('hello ' + name)

	my_function('Morteza')

#### Decorators 3

	def my_decorator(func):
		def say(*args, **kwargs):
			print('say')
			func(*args, **kwargs)

		return say

	@my_decorator
	def my_function1(name):
		print('hello ' + name)

	@my_decorator
	def my_function2(name, family):
		print('hello ' + name + ' ' + family)

	@my_decorator
	def my_function3(name, family, age):
		print('hello ' + name + ' ' + family + ' ' + age)

	my_function1('Morteza')
	my_function2('Morteza', 'kashani')
	my_function3('Morteza', 'kashani', "11")

#### Decorators 4

	from functools import wraps

	def my_decorator(func):
		@wraps(func)
		def say():
			print('say')
			func()
		return say

	@my_decorator
	def my_function():
		print('hello')

	print(my_function.__name__)	

#### Decorators 5

	def show_decorator(name):
		def inner_decorator(func):
			def say():
				print(name)
				func()
			return say
		return inner_decorator

	@show_decorator('My Text')
	def my_function():
		print('this is my_function')

	my_function()
	
#### Decorators 6

	from time import time

	def speed_test_decorator(func):
		def wrapper(*args, **kwargs):
			start_time = time()
			result = func(*args, **kwargs)
			end_time = time()
			print(f"Time Elapsed : {end_time - start_time}")
			return result

		return wrapper

	@speed_test_decorator
	def sum_nums_list():
		return sum([x for x in range(40000000)])

	@speed_test_decorator
	def sum_nums_gen():
		return sum(x for x in range(40000000))

	sum_nums_list()
	sum_nums_gen()









<div class="md0"></div>

## Multi Threading

class myThread (threading.Thread):
   def __init__(self, name, instrument, timeFrame, dateFrom, dateTo):
      threading.Thread.__init__(self)
      self.name = name
      self.instrument = instrument
      self.timeFrame = timeFrame
      self.dateFrom = dateFrom
      self.dateTo = dateTo
   def run(self):      
      threadLock.acquire()
      fx.Update(self.instrument, self.timeFrame, self.dateFrom, self.dateTo)
      threadLock.release()









<div class="md0"></div>

## Multi Processing













<div class="md0"></div>

## Module 

	import random	
	import random as r
	
	from random import randint, choice
	from random import randint as ri, choice as rch
















<div class="md0"></div>

## API

	import requests

	response = requests.get("https://barnamenevisan.info/api/courses/getactivecourses")
	jsonData = response.json()

	for course in jsonData:
		print(f"{course['title']} مدرس : {course['teacher']}")

	res = requests.post("https://jsonplaceholder.typicode.com/posts")
	print(res.json())

	res = requests.get("https://jsonplaceholder.typicode.com/comments", params={'postId': 2})
	print(res.json())

	for data in res.json():
		print(data)









<div class="md0"></div>

## Database		








<div class="md0"></div>

## Error 

#### Return raise

	raise IndexError('throw index error')
	raise ValueError('invalid value')
<span></span>

	def colorize(text, color):

		colors = ('red', 'green', 'blue')

		if type(text) is not str:
			raise TypeError("text must be a string")
		elif color not in colors:
			raise ValueError(f"{color} is not in colors")
		else:
			print(f"printed {text} in {color}")

	colorize('mohammad', 'yellow')

#### try except

	def get(d, key):
		try:
			return d[key]
		except KeyError:
			return "no key found"
		except IndexError:
			return "index error"

	person = {'name': 'mohammad','family': 'ordookhani'}

	print(get(person, 'age'))
<span></span>

	try:
		num = int(input("plese enter a number: "))
	except ValueError:
		print('thats not a number! please enter another one :')
	else:
		print('you have entered a number')
	finally:
		print('this is finally section')
<span></span>
 		
	def divide(first, second):
		try:
			return first / second
		except ZeroDivisionError:
			return "Dont Divide By Zero Please !!!"
		except TypeError as error:
			print(error)
			return "first and second must be numbers !!!"

	print(divide(1, 'skjdf'))



	





<div class="md0"></div>

## Example

#### Convert DataType

	print(f"i am {20} years old")	
	myAge=20
	print("i am "+str(myAge)+" years old")
		
#### Get dara from user

	name = input('Insert Your name:')
	age = input('Insert Your Age:')
	message=f"You are {name} and you are {age} years old"
	print(message)
	
#### Convert kilometers to miles

	print("how many kms do you want to convert?")
	# kms / 1.60934  # "50" / 1.60934
	kms = input('insert kilometers:')
	miles = float(kms) / 1.60934
	miles = round(miles, 3)
	print(f"{kms} km is { miles } miles")
	
#### Convert Datetime	

	def generalToStamp(date, datetime_fmt="%Y/%m/%d %H:%M:%S"): 
	return int(time.mktime(parse(date).timetuple()))

	def stampToGeneral(data, datetime_fmt="%Y/%m/%d %H:%M:%S:%f"):
	return dt.fromtimestamp(data).strftime(datetime_fmt)  	

	start_time = time.time()
	print(f"-------------- Time(Connection):{time.time() - start_time}")



#### Write To File
	f = open("log", "w")
	f.write("Now the file has more content!")
	f.close()
