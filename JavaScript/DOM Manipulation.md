# DOM:

DOM stands for document object model. It can be thought of as a tree model of your html created by the browser and Javascript can be used to read, write and manipulate the DOM. An interface for changing the content of a web page.
It's arranged in a hierarchical tree. DOM is the representation of an html document.
It is object oriented which means that each node has its own methods and properties.
The browser gives us a main window object which is the browser itself then we have document object in it which further root element and so on.
Technically it's an API(Application programming InterFace);

```DOM
console.dir(document);
```
This command will show all the properties and methods which are part of document object.

## Important properties of DOM:

```Document Object Model
	console.log(document.domain);
	console.log(document.URL);
	console.log(document.title);
	console.log(document.doctype);
	console.log(document.head);
	console.log(document.body);
	console.log(document.all);
	console.log(document.forms);
	console.log(document.links);
	console.log(document.images);
```


## DOM Selectors:
```DOM
	document.getElementById('id_name_hre');
	document.getElementByName('name_attribute of input tag');
	document.getElementByTagName('li');
	document.getElementByClassName('className');
	document.querySelector('className,Id,or attribute');
	document.getElementByAttribute('li');
	document.body.firstElementChild;
	document.body.lastElementChild;
	document.body.parentElement;
	document.body.nextElementSibling;
	document.body.previousElementSibling;
	document.body.children[];
	let children = Array.form(element.children);
	children.forEach(child => child.sttyle.background = "lightgreen");
```

# Traversing the DOM:
* .parentNode
* .childNodes

## Add Change Html Elements:
* **.textContent = 'assign_new_value_here'**     It focus on the text value despite of the style applied
* **.innerText = 'assign_new_valur_here'**          It focus on text as well as style applied on the element. It is vulnerable to XSS attacks.
* .**innerHTML = 'block_of_code_here'**            You can use it for inserting block of code with Javascript
* .createElement('element_name');

```
	const nameTag = document.creatElement("h1");
	nameTag.textContent = window.prompt("Enter Your Name");
	document.body.append(nameTag);
```

* .prepend()   append()
  prepend to add at start
  append to add at last

```
	const myList = document.querySelector("#fruits");
	const listItem = document.createElement("li");
	listItem.textContent = "mango";
	myList.append(listItem);
```

# CSS Styling with DOM

* .style.backgroundColor = "" ;
* .style.color = "" ;
*  .style.fontFamily = "" ;
* .style.textAlign = "" ;
* .style.border = "" ;
*  .style.display = "" ;

# Events
* .onclick
* .onload
* .onchange
* .onmouseover
* .onmouseout 
* .onmousedown
* .onmouseup 
* .mouseenter
* .mouseleave
* .click
* .dblclick
* .mouseover
* .mouseout
* .mousemove


# EventListners

.addeventListner(event, function, useCapture)
You can add any event handlers to one element
Even the same event that invokes different functions.
If two elements are overlapping and listening to same type of event then we can use `true`  or `false` for giving preference to event as third option in the event listner.

# Key Listners
```DOM
	window.addEventListner("keydown", function());
```
# Canvas API:
A means for drawing graphics, Used for animations, games, data visualization.

```DOM
	//first make a canvas tag in html
	
	let canvas = document.getElementById("myCanvas");
	let context = canvas.getContext("2d");
	
	context.stroke.style = "color_name";
	context.lineWidth = 10;
	context.beginPath();
	context.moveTo(0,0);
	context.lineTo(250,250);
	context.linetTo(250,250);
	context.moveTo(500,0);
	context.linetTo(250,250);
	context.stroke;
	
	context.strokRect(0,0,0,0);
	context.arc(100,100,100,0 2* Math.PI);
	context.fillText = ()"text here, x , y");
	context.fillText;
```

## making a triangle:
```DOM
	context.beginPath();
	context.moveTo(250, 0);
	context.linetTo(0,250);
	context.linetTo(500,250);
	context.linetTo(250,0);
	 context.fill();

```

# Window Object:
Interface used to talk with the web browser.
The DOM is the property of window.

```DOM
	console.dir(window);

	window.innerWidth;
	Window.innerHeight;

	window.outerWidth;
	Window.outerHeight;

	window.scrollX;
	window.scrollY;

	window.loacation.href;
	window.loaction.hostname;
	window.loaction.pathname;

	window.open(); //can pass here any link
	window.close();
	window.print();

	window.alert();
	window.confirm();
	window.prompt(); 
```



# Cookies:
A small text file stored on your computer used to remember information about the user saved in `name=value` pairs.

	navigator.cookieEnabled;
	

## Making New Cookie:
```DOM
	document.cookie = "firstName = Zohaib; epires= Sun 1 Jan 2030 12:00:00 UTC; path=/;
	document.cookie = "lastname=Ali; epires= Sun 1 Jan 2030 12:00:00 UTC; path=/";

	setCookie("email, Spongebob@gmail.com", 365);
	function setCookie(name, value,daysToLive){
	cosnt date = newDate();
	date.setTime(date.getTime() + daysToLive * 24 * 36000);
	let expires = "expires=" + date.toUTCString();
	document.cookie = `${name}=${value}; ${expires}; path=/`;
	}
```
