Our main goal is database modeling and and development

**Books:**
* Modern Database Management (11th Edition) 11th Edition by Jeffrey A. Hoffer, Ramesh Venkataraman , Heikki Topi
* Database Systems: A Practical Approach to Design, Implementation and Management (4th Edition) by Thomas M. Connolly, Carolyn E. Begg

# Database:
"A shared collection of logically related data and a description of this data, designed to meet the information needs of the organizations"
Logically related data comprises of entities, attributes and relationships of an organization's information.

## DBMS:
A Software system that enables users to define, create, mantain and controll access to database.

## Components of DBMS:
* Data Defination Language (*DDL*) :  Permits specification of data types, structure and any data constraints. 
* Data Manipulation Language (*DML*) : General Enquiry Facility of Data.
* Controlled Access

# File Systems vs DBMS
File Basd Systems: "A collection of application programs that perform services for the end-users such as production of reports. Each program defines and manages its own data."
**One File One Application**

## Limitations of File Based Systems:
* Separation and Isolation of Data (One Program one File)
* Data Redundancy
* Loss of Data Integrity
* Data Dependence - Data depend on the program
* Incompatibility of file formats
* Fixed queries and Little Flexibility
* Data Abstraction - Separation between data defination and Application program

## Organizing Data:
1. Entity - Distinct Objects e.g person, place or thing
2. Attribute - Some aspect of the entitiy
3. Relationship - Association between entities

## Components of Database Enviorment
* Hardware: Servers, PCs
* Software: DBMS, DDL, DML 
* Data: Organized in Schema, Divided into Sub-schemas
* Procedures: Govern the Design, Access and use of Database
* People: Administrator DBA, Designers, Application Developers and Users.

## Advantages of Database Approach:
* Control on Data Redundancy - Redundancy is minimized not removed at all
* Data Consistency
* Greater Information gain from same amount of data as comapared to file based data
* Data Sharing
* Improved Data Integrity, Validity and Consistency 
* Improved Access and Security
* Enforcement of Standards
* Economy of Scale, Centralization and Consolidation
* Balancing of Conflicting Requirements
* Improved data accessibility and responsiveness
* Increased Productivity
* Improved Maintenance through data independence
* Increased Concurrency
* Improved Backup and Recovery Services.

## Disadvantages of Database Approach:
* The Database approach is more complex and takes more size also we need greater resources for database approach.
* Cost of DBMS
* Hardware Cost
* Cost of Conversion
* Higher Impact of Failure
* In production Enviornment, Processing can be slow

# Creating DFD:
1. Create a list of Activites
2. Create a context level DFD - Entites and Processess (*Identify Sources and Sinks*)
3. Constrcut Level 0 DFD - Manageable Sub-processes (*Identify logical Subsytem*)
4. Construct Level 1 DFD - Actual Data flow and Data Resources (*Identify where to store data*)
5. Check against Rules of DFD 

## Naming GuideLines:
* External Entity Should Be Noun 
* Data flow 
* Processess should be verb phrase
* Data Store should be noun

# Schema and SubSchema:
Complete Catalog of data stored in the database.