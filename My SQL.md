Organized collections of tables is is known as relational databases.

`SQL` stands for *Structured Query Language*.

Tables are the main building blocks.
Tables divided rows and columns.

* rows -> *records*
* columns -> *fields*

# Table Naming Convention:
* Should be lowercase
* No spaces are allowed(Use underscore instead)
* Refer to a collective group or be plural

Record refer to the complete information about a person. It shares a piece of information from every field.
Field refer to a collection of a single piece of information about all records.

## Fields Naming Convention:
* Should be lowercase
* No spaces
* should be written singular
* two fields cannot have same name
* field name should be different from the table name

**Unique identifiers are used to identify records in a table**
Unique identifier is often a number.

Use multiple tables to make database to organize data in a manageable way.


When a table is created a data type must be indicated for each field.
Schema are often referred as blueprints of databases.
Database we use stores the data on a hard disk of computer which is often known as `Database Server`.
Servers are centralized computers that perform services via requests made over a network.


# Data Types:
* `SHORTSTRING`
* `VARCHAR`
* `INT`
* `FlOAT`
* `NUMERIC`

If You want to perform mathematical operations use `NUMERIC` or `INT` datatypes.


# Keywords:
* `SELECT` *Refers to select a field*
* `FROM` *Refers to select from a table*
* `AS` *Can be used for aliasing fields*
* `DISTINCT` *To avoid any repetitive data in a field*
* `CREATE VIEW` *To save the result of a query for future use*
* `LIMIT` *To Limit the result set*



we can select multiple fields with `SELECT` keyword by separating the field names with comma.
It's a best practice to end a query with a semi-colon.
To select all the fields in a table we use `SELECT *` .
We can use aliasing to rename columns. It only changes the field name while printing result set but doesn't actually rename our field.

A view is a virtual table that is the result of a saved SQL `SELECT` statement.
When accessed, views automatically update in response to updates in underlying data

# `SQL` Flavors:
`SQL` have different flavors some are free and some are paid. 
* `PostgreSQL`
	* Free and open-source relational database.
	* Created at University of California Berkeley. 
	* Sponsored by `DARPA` 

* `SQL Server`
	* Has Free and Paid Versions.
	* Created by Microsoft


```mysql
#Create New Database
CREATE DATABASE "databaseName";
#Backup existing Database .bak file extension name 
BACKUP DATABASE "databaseName"
TO DISK = 'filepath';
#Delete Database
DROP DATABASE "databaseName";

```