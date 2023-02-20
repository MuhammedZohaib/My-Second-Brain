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
SHOW DATABASES;
USE "databaseName";

CREATE table employees(
id int,
firstname varchar(255),
lastname varchar(255),
email varchar(255)
);

DROP TABLE "tablename";
```

# Database Design
*How Should we design databases?*
1. `Schemas` (How data should be logically organized)
2. `Normalization` (Minimal Dependency and Redundancy)
3. `Views` (Join Queries)
4. `Access Control` (Should All Users have same access Level?)
5. `DBMS` (SQL or Non-SQL)

## Approaches to Processing Data
*Helps design how data will flow, processed and stored*
1. `OLTP` (Online Transaction Processing)
2. `OLAP` (Online Analytical Processing)

OLTP focus on supporting day to day operations while OLAP tasks are vaguer and focus in business decision making.

 |         |OLTP | OLAP|
 |------|-------|-------|
 |Purpose |  support daily transactions |report and analyze data|
 |Design|application-oriented|subject-oriennted|
|Data|up-to-date, operational|consolidated,historical|
|Size| Snapshot, gigabytes| archive,terabytes|
|Queries| simple transactions & frequent updates| complex, aggregate queries & limited updates|
| Users| Thousands|Hundreds|


* Figure Out Business Requirements
* OLTP Design or OLAP Design or both

### Storing of Data
1. Structured Data (*Follow a Schema, Defined Types and RelationShips with concepts like foriegn keys*)
2. Unstructured Data (SchemeLess, Most of Data in world like photos, chat logs, mp3)
3. Semi-Structured Data (Don't Have a Large Schema, Show some Structure)

**Structured Data:** Easy to Analyze, More Flexibility and Scalability but not very flexible because it follows a schema

* Tradational Databases (OLTP)
* Data Warehouses (OLAP)
* Data Lakes (For analyzing big data)

## Data Warehouses
* Optimized For Read-Only analytics 
	 * Organized for reading/aggregating data
	 * Usually Read Only
* Contains Data from multiple Resources
* Massively Parallel Processing
* Dimensional Modeling and Denormalized Schema
 
 Amazon Redshift
 Azure SQL Data Warehouse
 Google Big Query

### Data Marts
* Subset of Data Warehouse
* Dedicated to a Specific Topic
  
## Data Lakes
* Stores all types of data at a lower cost
* Retain all data and can take up petabytes
* Schema on-read as opposed to Schema on-write
* Need to catalog data otherwise becomes a data swamp
*Data Lakes are used for analysis for machine learning and data discovery as the data is not very clean*

## Data Flows:
1. ETL (Extract Transform Load) -> Data Warehouses and Small scale analytics
2. ELT (Extract Load Transform) -> Big Data Projects, Data Lakes

## Database Design
* How Data is logically Stored?
* How Data is going to be read and updated?

There are two important concepts when it comes to design
1. `Models(High Level Specifications for Database Structures)`
   * Relational Model (*Most Popular*)
   * NoSQL Model
   * Object-Oriented Model
   * Network Model  
2. `Schemas (Blueprints of Databases)`
   * Define tables, fields, relationships,indexes and views
   * Schemas must be followed while data insertion

The first step of database design is defining a model, this is the abstract phase of database design. There are three levels to a data model.
1. Conceptual data model (describe entites and relationship)
2. Logical data model (define or map tables columns and relationships)
3. Physical data model (describes physical storage)

Beyond Realtional Modeling we also have Dimensional Modeling. It is an adaption to relational modeling for data design. It is more like optimized for OLAP queries: aggregate data, not updating data. Built using Star Schema. 

In Dimensional Modeling we have two types of tables 
	1. Facts Table (Business use case, Updated regularly, connects to dimension table via foriegn keys)
	2. Dimension Table (hold attributes, does not changed often)

## Example of schema:

| runs|           |
|------|-------|
|duration_mins| float|
|week|int|
|month|varchar(160)|
|park_name|varchar(160)|
|city_name|varchar(160)|
|distance_km|float|
|route_name|varchar(160)|

## Creating Table Example:
```sql
-- Create a route dimension table
CREATE TABLE route (
    route_id INTEGER PRIMARY KEY,
    park_name VARCHAR(160) NOT NULL,
    city_name VARCHAR(160) NOT NULL,
    distance_km FLOAT NOT NULL,
    route_name VARCHAR(160) NOT NULL
);
-- Create a week dimension table
CREATE TABLE week(
    week_id INTEGER PRIMARY KEY,
    week INTEGER NOT NULL,
    month VARCHAR(160) NOT NULL,
    year INTEGER NOT NULL
);
```

### SUM AVG COUNT

```sql
SELECT SUM(duration_mins) from run;
SELECT AVG(mins) from day_time;
SELECT count(people) from candidates;
```













 







