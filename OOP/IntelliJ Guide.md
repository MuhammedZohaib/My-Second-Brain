# The iml File:
The iml file contains the basic module information and a module in  intelliJ is a discrete chunk of code that you can run debug independently. There are more than one module in a project.
An iml file is actually an XML file.

# .idea Folder:
The .idea folder is basically a bunch of collection of files which are applicable to the whole project. In other words we can say that these are the some of IDE generated files.
**Example:**
`workspace.xml` contains information about the workspace you're working. It also contains your personal preferences about the project you're working on.

`modules.xml` contains different modules that you have inside your project.

`.gitignore` contains the file names which you want to ignore while pushing to a GitHub repository or any other version control application.

It is advised not to edit `xml` files in .idea folder of your project you're working in. 

# src Folder:
The src folder is the folder where you'll do most of Your work. src is short for source. where you're writing your source code.

# out Folder:
In intelliJ while working on a project you'll not actually see any out folder at start it'll appear as soon as you run you're program for the first time.
The out folder contains the executable java files of your program. In other words we can say this folder contains `.class` files which contains `bytecode` for our java files.
**External Libraries** folder contain libraries on which our project depends