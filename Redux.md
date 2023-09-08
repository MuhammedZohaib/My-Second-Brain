"Redux is a predictable state container for JS apps". Redux is used for state management in any JS apps. Suppose in a react app if some component needs to access the state of another component then we'll need to lift the state up to their parent. so that it can be accessed by it's child similarly in case of children we need to pass the state as props. This is where redux comes in handy.

We can also manage the state using the React hooks which are `useReducer` and `useContext` instead of redux but redux was introduced back in 2015 when these hooks were not available. We'll likely to use Redux for our react project which will have some routes and several components sharing states. Also we'll use React-Redux library which actually binds the both react and redux together.

## Getting Started
Make sure we have `node` and `npm` installed in our system.

```node
npm install redux
```

## Three Core Concepts in Redux

- Store: `Holds the state of the application`
- Action: `Describes what happend`
- Reducer: `Binds the store and action together`

## Three Principles of Redux
These three redux principles basically define redux patterns:

- All the states in the application are stored in a single object which is managed by the redux store.
- The only way to change the state is to emit an action, an object describing what happend. we are not allowed to directly update the state object the only way is through an action.
- To transform the state based on the action we write pure reducers.

## Actions:

- The only way we can interact with our redux store.
- Carry some information from our application to redux store.
- Takes in a plain JS object.
- Has a type property which indicates the type of action being performed.
- Type property is typically defined as string constants.


```js

const BUY_CAKE = `BUY_CAKE` //Action Type

function buyCake(){ //Action Creator, defined in the reducer function
	return{
	type: BUY_CAKE
	}
}

```

## Reducers:

Reducers specify how the state of the application changes when an action is dispatched. It accepts state and action as argument and returns the next state of the application.

	(previousState, action) => newState

## Redux Store:
- Holds application state
- Allows to access state via `getState()`
- Allow state to be updated via `dispatch(action)`
- Registers listeners via `subscribe(listener)`
- Handles unregistering of listeners via the function returned by the `subscribe(listner)`


## Redux API

It has total five main methods and also the `createStore` object has 4 methods which makes a total of 9 methods.

- `createStore`
- `bindActionCreator`
- `combineReducers`
- `compose`
- `applymiddleware`


```js
//The compose function in the redux api provides the functionality of the pipes suppose we have three functions and we need to process our data through all the three function is either we can pass our value one by one to all the functions or simply we can use the compose method present in the redux api

const makeLouder = string => string.toUpperCase();
const repThreeTimes = string => string.repeat(3);
const bold = string => string.bold();

const allFunctionRun = string => bold(repThreeTimes(makelouder(string)));

allFunctionRun('lmao');


//with compose method

const allFunctionRun = compose(makeLouder,repThreeTimes,bold);
allFunctionRun('lmao');
```


```js
//Reducer function is a function that takes two parameters action that happend and the state and returns the new modified state.
```


```js
//The store has an object that is known as replaceReducer and it takes a function as argument and relaces the current reducer wit the new function. we use this method for code splitting.
```

Try to use only one store using multiple stores is an anti-pattern.

```js
//Make a constant of the actions types
const INCREMENT = "INCREMENT";
const ADD = "ADD";

//An object containing the initial state of our app
const initialState = {
    value: 0,
}

//our actions
const increment = () => ({type: INCREMENT});
const add = (amount) => ({type: ADD, payload:amount});

//our reducer function
const reducer = (state = initialState, action) =>{
    switch(action.type){
        case INCREMENT:
            return {value: state.value +1};
        case ADD: 
            return {value: state.value + action.payload};
    }
    return state;
}

//creating new store
const store = createStore(reducer);

//subscriber function
const subscriber = () => console.log("SUBSCRIBER", store.getState());

//subscribing a function which runs every time our state changes
store.subscribe(subscriber);

//a function which binds all our actions together
const actions = bindActionCreators({increment, add}, store.dispatch);

actions.increment();
actions.increment();
actions.increment();

```

```js
const initialState = {
    users:[
        {id:1, name:"Steve"},
        {id:2, name:"Eric"}
    ],
    tasks:[
        {title: "idk do something"},
        {title: "idk do something more"},
    ]
}

const ADDUSER = "ADDUSER";
const ADDTASK = "ADDTASK";

const addTask = (title) => ({type: ADDTASK, payload:{title}});
const addUser = (id,user) => ({type: ADDUSER, payload:{id,user}});

const reducer = (state = initialState, action) => {
     
    switch(action.type){
        case ADDUSER:
            return {...state, users:[...state.users, action.payload]}
        case ADDTASK:
            return {...state, tasks:[...state.tasks, action.payload]}

    }
}

const store = createStore(reducer);

const subscriber = () => console.log('subscriber', store.getState());

store.subscribe(subscriber);

const actions = bindActionCreators({addTask,addUser}, store.dispatch);
```

```js
const initialState = {
    users:[
        {id:1, name:"Steve"},
        {id:2, name:"Eric"}
    ],
    tasks:[
        {title: "idk do something"},
        {title: "idk do something more"},
    ]
}

const ADDUSER = "ADDUSER";
const ADDTASK = "ADDTASK";



const addTask = (title) => ({type: ADDTASK, payload:{title}});
const addUser = (id,user) => ({type: ADDUSER, payload:{id,user}});

const userReducer = (users = initialState.users, action) => {
    if(action.type === ADDUSER){
        return [...users, action.payload]
    }
    return users;
}
const taskReducer = (tasks = initialState.tasks, action) => {
    if(action.type === ADDTASK){
        return [...tasks, action.payload]
    }
    return tasks;
}

const reducer = combineReducers({users: userReducer, tasks: taskReducer});

const store = createStore(reducer);

const subscriber = () => console.log('subscriber', store.getState());

store.subscribe(subscriber);

const actions = bindActionCreators({addTask,addUser}, store.dispatch);
```

```ts
import { bindActionCreators, combineReducers, createStore } from "redux";

type user ={
    id: number;
    name: string;
}
type tasks = {
    title: string;
}

type initialType = {
    user: user[];
    tasks: tasks[];
} 

type actionType = {type: string, payload:{id: number, name: string}} | {type:string, payload:{title: string} }

const intialState :initialType = {
    user: [
        {id: 1, name: "zohaib"}
    ],
    tasks:[
        {title: "lmao do something"}
    ]
}

enum dispatchedActions {
    ADDUSER = "ADDUSER",
    ADDTASK = "ADDTASK"
} 

const addUser = ({id, name}: user): actionType => {return {type: dispatchedActions.ADDUSER, payload:{id,name}}};
const addTask = (title:string) : actionType => {return {type: dispatchedActions.ADDTASK, payload:{title: title}}};

const userReducer = (user = intialState.user, action:actionType) =>{
    if(action.type === dispatchedActions.ADDUSER){
        return [...user, action.payload]
    }
    return user;
}
const taskReducer = (task = intialState.tasks, action:actionType) =>{
    if(action.type === dispatchedActions.ADDTASK){
        return [...task, action.payload]
    }
    return task;
}

const reducer = combineReducers({user:userReducer,task:taskReducer});
const store = createStore(reducer);

const subscriber = (): void => {console.log('State', store.getState())};

store.subscribe(subscriber);

const actions = bindActionCreators({addUser,addTask},store.dispatch);

actions.addTask("Lmao this");

```
