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