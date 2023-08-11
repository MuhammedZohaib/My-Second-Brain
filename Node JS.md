## **npm Commands:**

### **npm init**
This command initializes a new npm package in the current directory, creating a `package.json` file with package information.

```bash
npm init
```

### **npm install**
This command is used to install packages and their dependencies either locally or globally.

Local installation:
```bash
npm install <package_name>
```

Global installation:
```bash
npm install -g <package_name>
```

### **npm update**
Updates packages to their latest versions.

Update a local package:
```bash
npm update <package_name>
```

Update all local packages:
```bash
npm update
```

### **npm uninstall**
Removes packages, either locally or globally.

Remove a local package:
```bash
npm uninstall <package_name>
```

Remove a global package:
```bash
npm uninstall -g <package_name>
```

### **npm list**
Displays a list of installed packages.

List local packages:
```bash
npm list
```

List globally installed packages:
```bash
npm list -g --depth=0
```

### **Updating npm**
To update npm itself:
```bash
npm install -g npm
```

## **Updating Node.js:**

Updating Node.js involves using a version manager like `nvm` (Node Version Manager).

1. Install `nvm`:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

2. Restart your terminal to activate `nvm`.

3. List available Node.js versions:
```bash
nvm ls-remote
```
   (Or for Windows: `nvm list available`)

4. Install a new Node.js version:
```bash
nvm install <version>
```
   (For example: `nvm install 14.16.1`)

5. Set the new version as default:
```bash
nvm use <version>
```
   (For example: `nvm use 14.16.1`)

6. Verify the installed Node.js version:
```bash
node -v
```
