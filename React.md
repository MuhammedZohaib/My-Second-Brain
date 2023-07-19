React is a JavaScript library for building user interfaces. It is mostly used to make single page applications. It allows us to create reusable UI components. The one good thing about the react is that it uses virtual DOM so as the edit is done it loads the edits into the virtual DOM and look for changes and only makes small changes in DOM rather than reloading the whole app.

We need to have installed Node JS in order to make react applications. The official way of creating a react app is using node package known as `create-react-app`. But it is important to note that we must install this package locally to make sure every time we uses the latest version of this package.
To install this package:

```JS
npm install create-react-app
```

If installed globally just simply uninstall it using:

```JS
npm uninstall -g create-react-app
```

We can create a simple React app by using node package known as `create-react-app`.

```JS
npx create-react-app "app name in lowecase without double quotes here"
```

After creating a simple react app go to the directory of the app and run:

```JS
npm start
```

This'll start the default react app and you can see live editing in the browser. To edit the project we need to find the `Project/src/App.js`. Open this file and you'll find a div with `className='App'`. This div is where we'll put our html code.

The default file structure of a React app created with `create-react-app` consists of several important directories and files. Here's a brief overview of each one:

1.  `node_modules`: This folder contains all of the dependencies installed for your React app, including the React library itself and any other packages you may have added.
2.  `public`: This folder contains assets that should be available to the public, such as the `index.html` file and any images or other resources that your app uses.
3.  `src`: This is the most important folder in your React app, and it contains the source code for your components, styles, and other assets.
4.  `src/components`: This folder is where you should keep all of your React components. Components are modular, reusable pieces of UI that you can use to build the user interface of your app.
5.  `src/styles`: This folder is where you can keep any styles that you want to apply to your components. You can create CSS or Sass files, or you can use any other CSS preprocessor that you prefer.
6.  `src/images`: This folder is where you can keep any images or other media files that you want to use in your app.
7.  `src/utils`: This folder is where you can keep any utility functions or other code that doesn't belong in a specific component.
8.  `src/App.js`: This file is the main entry point for your React app. It usually contains the root component that is rendered on the page, and it sets up the routing for your app.
9.  `src/index.js`: This file is responsible for rendering your React app to the page. It uses the `ReactDOM` library to render the root component of your app inside the `index.html` file.

This is the basic structure of a React app created with `create-react-app`. Of course, your own React app may have a slightly different structure, depending on your specific needs and the packages that you have installed.

```JS
const App = () =>{
return React.createElement(
"div",
{}
React.createElement("h1",{},"Hello World")
);
};

const Container = document.querySelector("#div");
const root = ReactDOM.createRoot (container);
root.render(React.createElement(App));
```

The above is the Basic rendering process of react but from now on we'll use JSX instead of React.createElement but in the background still the rendering is done as shown above.

## Key Points:
* Always Capitalize your components
* A component must return a markup which is result of `React.createElement()`.
* One way data flow data can be passed from parent to child but not from child to parent this allows debugging alot easier in react
* `package.json` is where we keep most of our dependecies.
* Also add a .gitionre and add files and directories which you don't want to push in the repo.
* Earlier we have been using parcel and web-pack as our build tool but from now on we'll be using vite as our build tool. It is a tool provided by Vue Team.
* react and react-dom are always released in locked versions means they'll always have the same version 
* `UseEffect` is the most buggy and hard part of react. Minimize use of it in your apps.
* While making an react function component always use Pascal Casing. Also use Pascal naming convention for naming react components.
* A component cannot return more than one element so we use a div to wrap all the elements and the div acts as the parent element but for solving this issue we are adding an extra component to the app to solve this we use Fragment from react. we can also use empty angle brackets instead of an Fragment.

### My Tech Stack:

- Bundler : `Vite`
- Components: `FunctionalComponents`
- State Management: `Redux`
- Routing: `React Router`
- Styling: `MUI and CSS Modules`
- API Calls: `React-Query`
- Testing: `Jest, Playwright`
- Framework: `Next.js`
- Forms: `React Hook Form`
- JS: `Typescript`


```JS
npm install --save-dev prettier
//make a .prettierrc file with empty obj {} in project directory
//Turn on format on save from the vs code settings 
//Install the prettier extension
//Also turn on prettier require Config, This will make sure the project which have config file only those project's will be formatted.
"format": "prettier --write \"src/**/*.{js,jsx}\"" //add in package.json scripts
```

```JS
npm install --save-dev eslint eslint-config-prettier
//Install eslint extension in vscode
//create a eslintrc.json file in project directory add below JSON in it
"test": "eslint \"src/**/*.{js,jsx}\" --quiet"
```

eslintrc.json
```json
{
  "extends": ["eslint:recommended", "prettier"],
  "rules": {},
  "plugins":[],
  "parserOptions": {
    "ecmaVersion": 2022,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  }
}
```

```JS
npm i -D vite @vitejs/plugin-react//Adding vite to our dev-dependencies
//as we install vite for our build tool we dont need to add react and react-dom script tags but we need to add <script type="module" src="src/App.jsx"></script> in our code make sure the source file has an extension of jsx else the build tool wont work.
//Then rename the file App.js to App.jsx
//Add a vite.config.js file to root project folder
npm init vite
```

### vite.config.js

```JS
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

export default defineConfig({
    plugins: [react()],
    root: "src"
});
```


```JS
npm init vite@latest my-react-app --template-react
```

Earlier we have been using CRA for building react projects but from now on we'll use vite as our build tool for react projects.


## Configuring eslint for React

```JS
//eslint plugins to work with react
npm install -D eslint-plugin-import@latest eslint-plugin-jsx-a11y@latest eslint-plugin-react@latest

npm install -D eslint-plugin-react-hooks@latest
```

## .eslintrc.json for React

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "plugin:react-hooks/recommended",
    "prettier"
  ],
  "rules": {
    "react/prop-types": 0,
    "react/react-in-jsx-scope": 0
  },
  "plugins": ["react", "import", "jsx-a11y"],
  "parserOptions": {
    "ecmaVersion": 2022,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  },
  "settings": {
    "react": {
      "version": "detect"
    },
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx"]
      }
    }
  }
}
```

## React-Icons:
```js
npm install react-icons --save
```

# Hooks:
Anytime we see the keyword `use` in JXS it indicates that we are using hooks. 
All custom hooks are other hooks bundled together. We can only use hooks in a function component but not in class components. Custom hooks are basically calling other hooks but as a whole. Every time the component runs the hook must run in same order. We cannot use hooks conditionally or in asynchoronous manner. By convention all hooks start with letter use.

```jsx
const [currState, setState] = useState(""); //React Hook, DeStructuring is used
//useState returns an array
//setState is a function which is used to update the currState.
```


## Making Network Request:
For making network request in React we use Hook known as `UseEffect`
Effects are used to do chores which are outside the lifecycle of a react component. Most of the time it's an API request. 
UseEffect runs everySingle time we re-render our application. 

```js
useEffect(()=>{
	requestData();
},[]); //we can pass an array of dependcies in the useEffect hook so that it runs every time that dependency changes.

async function requestData(){
	const data = await fetch(`api here`);
	const json = await data.json();
}
```

People are less likely to use `UseEffect` Hook in their JSX file they make their custom hook and use it separately along with other hooks. Like suppose if you're making more than one network request you would like to use custom hook.

# React Router
For Multipage we need react router

```js
npm i react-router-dom@latest
```

- `BrowserRouter`
- `Routes`
- `Route`
- `Link`


# React Query:
React query is used to handle API requests. As we have `UseEffect` also but it's a better way and less buggy. so we prioritize its use instead of `UseEffect`

```js
npm i @tanstack/react-query@latest
```

first we need to instantiate the query provider in our `app.jsx`

```js
import {QueryClient, QueryClientProvider} from @tanstack/react-query;

const queryClient = new QueryClient({
defaultOptions:{
	queries:{
		staleTime: Infinity, //How long to store response in cache time is in millis
		cacheTime: Infinity,
	},
},
})
```

now move whole app body into `QueryClientProvider` but inside of `BrowserRouter`
always use a if condition that throws an error in case API request was not successful while using react query.


## React State Management

- React updates state asynchronously.

```jsx
const [person, setPerson] = useState({
name:'',
age: '',
designation:''
})

const onClick(()=>{
	setPerson(...person, person.name: 'myName')
})

```


## React Forms:

We can handle form in react by three ways or more:

- Using `useRef` Hook
- Using `useState` Hook
- Using `useForm` Hook

```js
npm i react-hook-form@latest

import {useForm} from "react-hook-form";
```

```jsx
import { useState } from "react";
import CSS from "./Form.module.css";

const style = {
  color: "#ff9f64",
};

const Form = () => {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    subject: "",
    message: "",
  });

  return (
    <form
      className={CSS.formContainer}
      onSubmit={(event) => {
        event.preventDefault();
        console.log(formData);
      }}
    >
      <h2 style={style}>Get in touch</h2>
      <p>Fill in the form below to contact us</p>
      <div className={CSS.borderDiv}>
        <label htmlFor="Name">Name</label>
        <input
          onChange={(event) => {
            setFormData({ ...formData, name: event.target.value });
          }}
          value={formData.name}
          type="text"
          name="Name"
          id="Name"
        />
        <label htmlFor="Email">Email</label>
        <input
          onChange={(event) => {
            setFormData({ ...formData, email: event.target.value });
          }}
          value={formData.email}
          type="text"
          name="Email"
          id="Email"
        />
        <label htmlFor="Subject">Subject</label>
        <input
          onChange={(event) => {
            setFormData({ ...formData, subject: event.target.value });
          }}
          value={formData.subject}
          type="text"
          name="Subject"
          id="Subject"
        />
        <label htmlFor="Meassage">Message</label>
        <textarea
          onChange={(event) => {
            setFormData({ ...formData, message: event.target.value });
          }}
          value={formData.message}
          name="Message"
          id="Message"
          cols="30"
          rows="10"
        ></textarea>
      </div>
      <button type="submit" className={CSS.button}>
        Submit
      </button>
    </form>
  );
};

export default Form;

```

```jsx
import CSS from "./Form.module.css";
import { useForm } from "react-hook-form";

const style = {
  color: "#ff9f64",
};

const Form = () => {
  const { register, handleSubmit } = useForm();

  return (
    <form
      className={CSS.formContainer}
      onSubmit={handleSubmit((data) => {
        console.log(data);
      })}
    >
      <h2 style={style}>Get in touch</h2>
      <p>Fill in the form below to contact us</p>
      <div className={CSS.borderDiv}>
        <label htmlFor="Name">Name</label>
        <input {...register("Name")} type="text" name="Name" id="Name" />
        <label htmlFor="Email">Email</label>
        <input {...register("Email")} type="text" name="Email" id="Email" />
        <label htmlFor="Subject">Subject</label>
        <input
          {...register("Subject")}
          type="text"
          name="Subject"
          id="Subject"
        />
        <label htmlFor="Meassage">Message</label>
        <textarea
          {...register("Message")}
          name="Message"
          id="Message"
          cols="30"
          rows="10"
        ></textarea>
      </div>
      <button type="submit" className={CSS.button}>
        Submit
      </button>
    </form>
  );
};

export default Form;

```

## Chakra UI

```js
npm i @chakra-ui/react @emotion/react @emotion/styled framer-motion
```

```tsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.tsx";
import "./index.css";
import { ChakraProvider } from "@chakra-ui/react";

ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
  <React.StrictMode>
    <ChakraProvider>
      <App />
    </ChakraProvider>
  </React.StrictMode>
);

```


```js
//add in package.json script
"server": "json-server --watch db.json --port 5000"
```


```js
import {Admin, Resource} from 'react-admin'
```


## Libraries for Backend Setup:

```js
npm install express mongoose jsonwebtoken bcryptjs clodudinary nodemon dotenv

//express -- server
//mongoose -- routing
//jsonwebtoken -- jwt
//bycryptjs -- password hasing
//cloudinary -- storing images
//nodemon -- automatically restart server on change (install globally) (run as binary)
//dotenv -- storing enviornment variables

```

## Setting up MongoDB

- Create mongo atlas account
- Create Database
- Grab connection URL
- make a `.env` file
- use mongoose for connection
- make sure to import `dotenv` for using environment variables
- also install Mongo DB compass application
- create a models directory
- use mongoose to define the schemas or model classes
- create a routes folder


### Writing APIs

- Create a Routes folder
- Create file names as `UserRoutes.ts` or `EmployeeRoutes.ts` 
- Import User model and `Router` in the Routes file

We need to send a token from the backend to frontend upon successful login. This token will be used to execute the queries from frontend to backend as an authorized connection.

# React & Typescript

```tsx
const component = ({name}:{name: string}) =>{
return();
}
```

```ts
const addTwo = (n: number): number =>{
return n + 2;
} 
```

```tsx
const component = () : JSX.Element =>{
return (<section></section>);
}
```

```ts
//prefer to use type instead of an interface as types can be combined using or operator

//creating a type which can be a type of props
type componentProps = {
name: string,
onChange: React.ChangeEventHandler<HTMLInputElement>, //hover over the attribute and steal the type :)
greetings?: string, //question mark indicates that it can be undefined
}

//an interface is more like a class which can be extended, can be used instead of a type
interface compoentProps{
name: string;
onChange: React.ChangeEventHandler<HTMLInputElement>;
}

//extending a type
type AdminControls = componentProps & {isAdmin : true};

//extending an interface
interface AdminControls extends componentProps{
isAdmin: true;
}

```

Make a `global.d.ts` for model which are often used.
For passing another react component as a child in props we can use `React.ReactNode` type.

```ts
type childProps={
box: React.ReactNode, //passing another react component as props
}


type childProps = PropsWithChildren<{

}>;
```


## Types

```ts
type myTypes ={
style?: React.CSSProperties,
}
```