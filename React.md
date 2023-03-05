React is a javascript library for building user interfaces. It is mostly used to make single page applications. It allows us to create reusable UI components. The one good thing about the react is that it uses virtual DOM so as the edit is done it loads the edits into the virtual DOM and look for changes and only makes small changes in DOM rather than reloading the whole app.

We need to have installed Node JS in order to make react applications. The official way of creating a react app is using node package known as `create-react-app`. But it is important to note that we must install this package locally to make sure everytime we uses the latest version of this package.
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
```

## .eslintrc.json for React

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
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

