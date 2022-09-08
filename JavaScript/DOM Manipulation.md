# DOM
DOM stands for document object model. It can be thought of as a tree model of your html created by the browser and Javascript can be used to read, write and manipulate the DOM.
It is object oriented which means that each node has its own methods and properties.
The browser gives us a main window object which is the browser itself then we have document object in it which further root element and so on.
Technically it's an API(Application programming InterFace);

	console.dir(document);

This command will show all the properties and methods which are part of document object.

## Important properties of DOM:

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

## DOM Selectors:
	document.getElementById('id_name_hre');









## DOM Properties and Methods:
* **.textContent = 'assign_new_value_here'**     It focus on the text value despite of the style applied
* **.innerText = 'assign_new_valur_here'**          It focus on text as well as style applied on the element.
* .**innerHTML = 'block_of_code_here'**            You can use it for inserting block of code with Javascript
* 