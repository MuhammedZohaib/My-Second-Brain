## npm init
This command is used to initialize a new npm package in the current directory. It creates a `package.json` file, which contains information about the package, such as its name, version, and dependencies.

```JS
npm init
```


## npm install
This command is used to install packages and their dependencies. You can install packages either globally or locally.

```JS
//To install a package locally (in the current directory) 
npm install <package_name>  
//To install a package globally 
npm install -g <package_name>
```

## npm update
This command is used to update packages to their latest version.

```JS
//To update a local package 
npm update <package_name>  
//To update all local packages 
npm update
```

## npm uninstall
This command is used to remove packages.

```JS
//To remove a local package 
npm uninstall <package_name>  
//To remove a global package 
npm uninstall -g <package_name>
```

## npm list
This command is used to display a list of installed packages.

```JS
//To display a list of local packages 
npm list  
//To display a list of globally installed packages 
npm list -g --depth=0
```

To update `npm` itself, you can use the following command:

```JS
npm install -g npm
```

## Updating Node JS
Unfortunately, there is no direct command to update Node.js. The recommended way to update Node.js is to use a version manager like `nvm` (Node Version Manager).

Install `nvm`: To install `nvm`, you can use the following command:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

* Restart your terminal to activate `nvm`.
* List available Node.js versions: You can use the following command to list all available Node.js versions:  

```JS
nvm ls-remote
```


* Install a new Node.js version: To install a new version of Node.js, you can use the following command:

```JS
nvm install <version>
//Replace `<version>` with the desired version number. For example:
nvm install 14.16.1
```

* Set the new version as the default: To set the new version as the default, you can use the following command:

```JS
nvm use <version>
//Replace `<version>` with the desired version number. For example:
nvm use 14.16.1
```

You can verify the installed version of Node.js by running:
```JS
node -v
```
