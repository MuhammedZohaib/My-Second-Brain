# Promises
The concept of promise is that it is an object which contains some value for an asynchorous function. Sometimes we don't know what will be the value of this object so this object has three states.
1. Pending
2. Fulfilled
3. Rejected

Rejected promise is like throwing an error like we sent a request to a site and the response never came back so we say that the promise is rejected.

```JS
const promise = new Promise((resolve, reject) => {
	resolve(3);
});
console.log(promise);
//else if the promise isn't resolved or rejected it'll show pending state.

const promise = new Promise((resolve, reject) => {
	setTimeout((() => resolve(3), 1000);
});
console.log(promise);
//In this case our promise will be resolved after one second which is asynchoronous but infact our promise is console logged even before resolving so it'll show pending state. which shows that synchoronous code is executed first. Incase if we make a console log after some time we'll se resolved promise. But it we make a request to a web or server we don't know how long it'll take to resolve so the set Timout method won't work in real scenarios. Insetead we use the below method.

promise.then(value => console.log(value));
//Thid .then methos will wait for promise to resolve and then it'll console log the value. This allow us to manipulate the value returned by the promise. This method can take two functions one for resolved promise and other for rejected promise.
promise.then(console.log, error => (console.log error));
//The second function is for rejected promise. But we have a nicer syntax for this which is
promise.then(console.log).catch(error => console.log(error));
//It is improtant to note that then function itself return a promise. .then deals with the resolved promises and .catch deals with the rejected promises. We can chain the .then methods as far as we want. Also there is a .finally mehtod which is executed no matter if the promise is resolved or rejected.

Promise.resolve();
Promise.reject();
//These are the methods which will return either resolved or rejected promise. There is no pending state. 
Promise.all();
//It takes a collection or array of promises and wait for all of them to be resolved. And all promises must resolves in case even if one of the promise is rejected then an error will be thrown.
Promise.race();
//This method also takes an array of promises and as the name suggest its function. It returns the promise which is resolved first. Returns first resolved promise. It is not affected by rejected promises.
Promise.any();
//This also takes an array of promises and look for any resolve promises and igonre rejected promises also it'll throw an error if all promises got rejected.


async function tester(){
return 3;
}
console.log(tester());


async function tester(){
await new Promise ((res, rej) => setTimeout(() => res(3), 1000));
return 3;
}
console.log(tester());

//The async keyword implicitly returns a promise while the await keyword waits for a promise to be resolved. We can only use await keyword when we are in a async function or at top level of a module. In these cases we also need to handle unresolved or rejected promises for that purpose we use try catch blocks.

async function tester(){
try{
await new Promise ((res, rej) => setTimeout(() => res(3), 1000));
return 3;
}
catch (error){
console.log(error);
}
}
```

# Working with the Server

The main implementation of promises is when we interact with the servers or APIs. also we don't know how long it'll take for a server to return response so we use promises in such cases.
### Basic Types of APIs:
1. BASE API -> *Simple GET API which returns some text*
2. JSON API -> *Just Like Base API just returns JSON response*
3. POST API -> *The API to which we can send data to and get a personalised response*
4. SLOW API -> *Base APIs which take alot of time to return some response*

To make a request to an API we use `fetch()` function which is provided by the browser. 

```JS
const BASE_API = "some api here";
const JSON_API = "some api here";
const POST_API = "some api here";
const SLOW_API = "some api here";

console.log(fetch(BASE_API)); //Promise{<pendind>}
//So for now we'll use .then statement as
fetch(BASE_API).then(console.log);
//This will console log the whole response once the promise is resolved. Instead of logging the whole object we can use the methods to get only our desired result.
fetch(BASE_API).then(res => res.text()).then(console.log);
//This will only console log the text response of the BASE_API. Also we would like to add a catch method in case of rejected promises.
fetch(BASE_API).then(res => res.text())
			   .then(console.log)
			   .catch(error => console.log(error));
//Another important thing to remember is that any code that is synchoronous will execute first as comapared to the asynchoronous functions or code.
//Sometimes these APIs can also take some parameters we can do this by using string concatenation or using URL object.
fetch(BASE_API + `?firstName=${name}&lastName=${lName}`).then(console.log);
//The same can be established using the url object as:

const url = new URL(BASE_API);
url.searchParams.set('firstName', name);
url.searchParams.set('lastName', lName);
fetch(url).then(console.log);
//Also we can use another approach in this case and that is XMLHTTP request as this was the standard method before fetch was added. The thing is that this method doesn't use promises.
const request = new XMLHTTpRequest();
request.addEventListner('load',function() {
  console.log(this.responseText)
});
request.open('GET',BASE_API);
request.send(); 
//Also we can use async and await instead of .then chains
async function main(){
	try{
	const response = await fetch(BASE_API);
	const text = await response.text();
	console.log(text);
	}
	catch(error){
		console.log(error);
	}
}
main();
//Some usefull method of response are:
response.status; //returns status code {anything in range of 200 is resolved} 
response.ok; //returns boolean
// Using JSON API is also similar to BASE API as:

async function main(){
	try{
	const obj = await fetch(JSON_API);
	const json = await response.json();
	console.log(json);
	}
	catch(error){
		console.log(error);
	}
}
main();
//Some imp mehtods
JSON.parse('string here'); //returns JSON from a string but string must be in JSON format
JSON.stringify('JSON here'); //returns Strinf from a JSON format
//sometimes we are not sure what type of response we'll get so in that case we can grab header and look for type of response as:
console.log(response.headers.get('content-type')); 

//Using POST_API we need to tell fetch() that we are making a POST request so either we can pass an anonymouse objet or we can make an object as options and pass it in the fetch.
async function main(){
	const data = {
		name: 'Zohaib'	
	}
	try{
	const obj = await fetch(POST_API,{
		method: 'POST',
		body: JSON.stringify(data),
		headers: {
			'Content-Type': 'application/json; charset-utf-8'
		}
	});
	const json = await response.json();
	console.log(json);
	}
	catch(error){
		console.log(error);
	}
}
main();
//OR
async function main(){
	const data = {
		name: 'Zohaib'	
	}
	const options = {
			method: 'POST',
		body: JSON.stringify(data),
		headers: {
			'Content-Type': 'application/json; charset-utf-8'
		}
	}
	try{
	const obj = await fetch(POST_API, options);
	const json = await response.json();
	console.log(json);
	}
	catch(error){
		console.log(error);
	}
}
main();
// we can also pass header object as:
async function main(){
	const headers = new Headers();
	headers.apped('Content-Type', 'application/json; charset-utf-8');
	
	const data = {
		name: 'Zohaib'	
	}
	
	const options = {
			method: 'POST',
		body: JSON.stringify(data),
		headers: headers	
		}
	
	try{
	const obj = await fetch(POST_API, options);
	const json = await response.json();
	console.log(json);
	}
	catch(error){
		console.log(error);
	}
}
main();

//Using SLOW_APIs

async function main(){
	const abortController = new AbortController();
	setTimout(()=> abortController.abort(), 2000);
try{
	const obj = await fetch(SLOW_API, {
		signal: abortController.signal
	});
	const json = await response.json();
	console.log(json);
	}
	catch(error){
		console.log(error);
	}
}
main();
```

# Timers and Intervals
1. Intervals -> *Run callback function repeatedly after after an interval of time*
2. Timeouts -> *Simply delay the execution of a function*
3. Animation frames -> *Allows us to run a call back function right before browser repaints* 

### Intervals
```JS
window.setInterval(() => {
	console.log('start');
} , 500)
// we alse don't need to specify the window object here.
//Also we need to stop the time for that puspose we need to specify an ID to the interval
let timerID;
timerID = setInterval(() => {
	console.log('start');
},500);

clearInterval(timerID);
```

### Timeouts
Timeouts delay the execution of a fucntion like if we want to run a function after a given time frame we'll use Timeouts as:

```JS
setTimeout(() => {
	console.log('Timeout')''
}, 2000);
//It'll delay the arrow function for 2s
//This also returns a timerID
```

### AnimationFrames
Animation frames work very similar to the `setIntervals` 
```JS
let animationFrameID = requestAnimationFrame("Pass function here recursively");
cancelAnimationFrame(animationFrameID);
//requestAnimationFrame runs approximately 60 times per second or can vary depending upon the system of the user.
```

```JS

performance.now(); //Returns the milliseconds from the origin time(Since page loaded)
Date.now(); //Returns number of milliseconds passed since January 1st 1970
//Creating Date Objects Manually

const date = new Date(Year, Month, Date, Hour, Minutes, Seconds, MilliSeconds);
date.getMonth();
date.getYear();
date.getDay();
date.getHours();
date.setMonth(8); //August

```

