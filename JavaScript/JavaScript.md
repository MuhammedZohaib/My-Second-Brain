
![[Screenshot from 2023-01-17 20-28-56.png]]


# -----Arrow Functions-----

 These are compact alternative to a tradational function.
 Represented by " => ".
 If you have no arguments you don't need any brackets before arrow function however if you have more then one arguments then we can enclose them in parenthesis.
# ----Nested Functions----
Functions Inside other functions.
Outer Functions have access to inner functions.
Inner Functions are "hidden" from outside Outer functions.
Used in closures. 
They add data security.
# ----Map----
An object that holds key-value pairs of any data type
# ----Object----
A group of properties and methods.

Properties = What an object has in it.
Methods = What an object can do.

we usually use . notation to access properties/methods.

## Example:

```JS
	const car1 = {
	
		model : "Mustang",
		color : "red",
		year : 2023,
		
		drive : function(){
		console.log("You drive the car");
		},
		brake : function(){
		console.log("You step on the brake");
		}
	};
	
	const car2 = {
	
		model : "Corvette",
		color : "blue",
		year : 2014,
		
		drive : function(){
		console.log("You drive the car");
		},
		brake : function(){
		console.log("You step on the brake");
		}
	};
	
	console.log(car.model);
	console.log(car.year);
	console.log(car.year);
	
	car.drive();
	car.brake();
```

# ----This Keyword----

Gives reference to a particular object.
The object depends on the immediate context.

## Example:
```JS
	const car1 = {
	
		model : "Mustang",
		color : "red",
		year : 2023,
		
		drive : function(){
		console.log(`You drive the car ${this.model}`);
		},
	};
	
	const car2 = {
	
		model : "Corvette",
		color : "blue",
		year : 2014,
		
		drive : function(){
		console.log(`You drive the car ${this.model}`);
		},
	};
```

# ----Class----
A class is  blueprint for creating objects.
Defines what properties and methods they have use a constructor for unique properties.

## Example:


```JS
	class Player{
	score = 0;
	pause(){
		console.log(`You have paused the game`);
	}
	exit(){
		console.log(`You have exited the game`);
	} 
	}
	
	const player1 = new Player();
	const player2 = new Player();
	const player3 = new Player();
	const player4 = new Player();
	
	player1.score += 1;
	console.log(player1.score);
	console.log(player2.score);
	
	player1.pause();
	player2.exit();

```

## ----Constructors----
a special method of a class
accepts arguments and assigns properties

## Example:
```JS
class Students{
	constructor(name, age, gpa){
		this.name = name;
		this.age = age;
		this.gpa = gpa;
	}
	study(){
			cosole.log(`${this.name} is studying`);
	}
	}
	
	const student1 = new Student("Zohaib", 30, 3.3);
	const student2 = new Student("Fawaz", 20, 3.6);
	const student3 = new Student("Aashir", 25, 3.9);
	
	cosole.log(student1.name);
	cosole.log(student1.age);
	cosole.log(student1.gpa);
	student1.study();
	
	cosole.log(student2.name);
	cosole.log(student2.age);
	cosole.log(student2.gpa);
	student2.study();
	
	cosole.log(student3.name);
	cosole.log(student3.age);
	cosole.log(student3.gpa);
	student3.study();

```

# ----Static Keyword----
A member that is static belongs to a class and not to the objects.
properties : useful for caches, fixed-configurations.
methods : useful for utility functions.

## Example:

```JS
	class Car{
	
		static numberOfCars = 0;
		constructor(model){
				this.model = model;
				Car.numberOfCar += 1;
		}
		
		static startRace(){
		console.log("3...2...1...G0!");
		}
	}
	const car1 = new Car("Mustang");
	const car2 = new Car("Corvette");
	const car3 = new Car("BMW");
	const car4 = new Car("Mazda Rx7");
	
	console.log(Car.numberOfCars);
	
	Car.startRace();
```

# ----Inheritance Property----

A child class can inherit all the methods and properties from another class known as a parent class.

## Example:


```JS
	class Animal{
		alive = true;
		eat(){
			console.log{`This ${this.name} is eating`};
		}
		sleep(){
			console.log{`This ${this.name} is sleeping`};
		}
	}
	
	class Rabbit extends Animal{
		
		name  = rabbit; 
		run(){
			console.log{`This ${this.name} is running`};
		}
	}
	
	class Fish extends Animal{
		name  = fish; 
		swim(){
			console.log{`This ${this.name} is swimming`};
		}
	}
	
	class Hawk extends Animal{
		name  = hawk; 
		fly(){
			console.log{`This ${this.name} is flying`};
		}
	}
	
	const rabbit = new Rabbit();
	const fish = new Fish();
	const hawk = new Hawk();
	
	console.log(rabbit.alive); /*shows true despite there is no any alive 
                                  property in rabbit*/
```


# ----Super Keyword----
Refers to the parent class.commonly used to invoke the constructor of a parent class.

## Example:
```JS
	 class Animal{
		 constructor(name, age){
		 this.name = name;
		 this.age = age;
		 }
	 }
	 class Rabbit etends Animal{
		 constructor(name, age, runSpeed){
			super(name,age);
			 this.runSpeed = runSpeed;
		 }
	 }
	 class Fish etends Animal{
		 constructor(name, age, swimSpeed){
			super(name,age);
			 this.swimSpeed = swimSpeed;
		 }
	 }
	 class Hawk etends Animal{
	 	 constructor(name, age, flySpeed){
			 super(name,age);
			 this.flySpeed = flySpeed;
		 }
	 }
	
	const rabbit = new Rabbit("rabbit", 1, 40);
	const fish = new Fish("fish", 2, 80);
	const hawk = new Hawk("hawk", 3, 200);
	
	console.log(rabbit.name);
	console.log(rabbit.age);
	console.log(rabbit.runSpeed);
```


# ----Get Keyword----
get binds an object property to a function when that property is accessed.

## Example:

```JS
	class Car{
		constructor(power){
			this._power = power;
		}
		get power(){
			return `${this._power}hp`;
		}
	}
	
	let car = new Car(400);
	
	console.log(car.power);
```


# ----Anonymous Objects----
These are the objects without any name.
Not directly refrenced.
Less syntax. No need for Unique names. We make a class and a constructor then we make an arrays in which we have our objects by using array methods we can access these objects.
These can't be accessed directly.

# ----Error----
These are the objects with description of something went wrong.

* Can't Open a file
* Lost Connection
* User types incorrect input
* TyperError


```JS
		try{
		let x = window.prompt("Enter a New Number");
		x = Number(x);
		if (isNan(x) throw "That wasn't a number");
		if(x == "") throw "That was empty";
		console.log(`${x} is a number`);
		}
		catch(error){
			console.log(error);
		}
		finally{
		console.log("This always executes");
		}

```
# ----Set Timeout()----
Invokes a Function  after a number of miliseconds.

```JS
	let time1 = setTimeout(firstMessage, 3000); /*when we use timeout it 
                                                gives us an id*/
	let time2 = setTimeout(secondMessage, 6000);
	let time3 = setTimeout(thirdMessage, 9000);
	
	function firstMessage(){
		alert('Hi');
	}
	function secondMessage(){
		alert('Welcome To Our site');
	}
	function thirdMessage(){
		alert('Thanks');
	}
	
	clearTimeout(time1); //it'll clear the set time for first message.
```


# ----setInterval()----
Invokes a function repeatedly after an interval of time.
It's a asynchronous function means it doesn't pause the execution of your function.

```JS
	let count = 0;
	let max = window.propmpt(`Count upto what number?`);
	max = Number(max);
	
	const myTimer = setInterval(countUp, 1000);
	
	function countUp{
		count+=1;
		console.log(count);
		if(count >= max){
			clearInterval(myTimer);
		}
	
	} 
```

# ----Date Object----
The date object is used to work with date and times

```JS
	let date = new Date();
	let year = Date.getFullYear();
	let dayOfMonth = Date.getDate();
	let dayOfWeek = Date.getDay();
	let month = Date.month();
	let hour = Date.getHour();
	let minutes = Date.getMinutes;
	let seconds = Date.getSeconds();
	let ms = Date.getMilliSeconds();
	
	//we can also set any of these properties
	Date.setFullYear(2024);
	
	date = date.toLocaleString();
	console.log(date);

```
## Making A Clock In JS:
```JS
	const myLabel = document.getElementById('clock');
	update();
	setInterval(update,1000);
	
	function update(){
	let date = new Date();
	myLabel.innerHTML = format(date);
	
	function format(date){
		let hours = date.getHours();
		let minutes = date.getMinutes();
		let seconds = date.getSeconds();
		let amOrPm = hours >= 12 ? "pm" : "am";
		hours = (hours % 12) || 12 ;
		
		hours = formatZeros(hours);
		minutes = formatZeros(minutes);
		seconds = formatZeros(seconds);
		
		return `${hours}:${minutes}:${seconds} ${amOrPm}`;
	}
	function formatZeros(time){
		time = time.toString();
		return time.lenght < 2 ? "0" : time;
	}
	}
```


# ----Synchronus & Asynchronus----
**Synchronus Code** = In ordered sequence, Step by step linear Instructions (start now, finish now)
**Asynchronus Code** = Out of Sequence (start now, finish sometime later)

**Synchronus Code Example:**

```JS
	console.log("step 1");
	console.log("step 2");
	console.log("step 3");
```

**Asynchronus Code Example:**

```JS
	console.log("step1");
	setTimout(()=> console.log(`Step 2`), 5000);
	console.log("step 2");

```

# ----console.time()----
Starts a timer which you can use to track how long an operation takes for a synchronus function.

```JS
	console.time(`Response Time`);
	window.alert(`Hello`);
	console.endTime(`Response Time`);
```


# ----Promises----
Object that encapsulates the result of an asynchronus operation .
Let asynchronous method return values like a synchronus methos.
"I promise to return something in the future"

the STATE is 'pending' then: 'fulfilled' or rejected
the RESULT is what can be returned
It has 2 parts producing and consuming.

```JS
	const promise = new Promise((resolve, reject)=> {
	let fileloaded == true;
	if(fileloaded = true){
	resolve("File loaded successfully");
	}
	else{
	reject("File not found");
	}
	})
	promise.then(value => console.log(value))
	.catch(error => console.log(error));


	const wait = time => new Promise(resolve => {
		setTimeout(resolve, 3000);
	})
	
		wait(3000).then(()=> console.log("Thanks for waiting"));
```


# ----async----
It makes a function return a Promise.
```JS
	async function loadFile(){
		let fileloaded == true;
	if(fileloaded = true){
		return "File loaded successfully";
	}
	else{
		throw "File not found";
	
	}
	})
	loadFile.then(value => console.log(value))
	.catch(error => console.log(error));

```
# ----await----
Make an async function wait for a Promise.
We can only use await keyword in async function

```JS
	async function loadFile(){
		let fileloaded == true;
	if(fileloaded = true){
		return "File loaded successfully";
	}
	else{
		throw "File not found";
	
	}
	})
	async function startProcess(){
	try{
				let message = await loadFile();
		console.log(message);
		}
	catch(error){
		console.log(error);
		}
	}
	startProcess();

```

# ----ES6 Modules----
The idea behind a module is that it's reusable 
we can import sections of pre-written code to use whenever we want. These are great for any general utility values and functions.
Helps to make your code reusable and maintainable.
Think of modules as separate chapters of a book.
To begin working with module add Type ="module" in script tag of html.

```JS
	<script type="module" src="index.js"></script>

	import {function_name} from "./second JS file path"; 
```

Also use export keyword before importing a function into another file.
```JS
	import * as descriptive name from "./second JS file path";
	console.log(descriptivename.getfunctionName());
```
