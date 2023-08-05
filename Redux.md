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
- 