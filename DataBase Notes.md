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
Complete Catalog of data stored in the database. (Individual Views are known as Sub-Schemas)

## Three Level Architechture:
- External Schema (User View of Database)
- Conceptual Schema (Community View) (What data is stored?)
- Internal View (Physical Representation) (How data is stored?)

1. Each User should be able to access same data but should have a different  customized view of data.
2. User should not have to deal directly to physical database.
3. Database structure should be changeable without affecting the user views.
4. Changes on high level should not make any changes on low level.


## Data Independence
- Logical Data Independence (Changes in external schema doesn't affect conceptual schema)
- Physical Data Independence (Changes in conceptual schema to changes in internal schema)

## Database Languages
- Data Definition Language
- Data Manipulation Language

# Models
- Data Models (DDL, DML, Constraints)
- Database Models
	- Conceptual Models
		- Entity Relationship Database Model
		- Object Oriented Database Model
	- Implementation Models
		- Hierarchial Database Model
		- Network Database Model
		- Relational Database Model
		- Object Oriented Database Model


Hierarchical Database Model

| Pros | Cons |
| --- | --- |
| Simple structure that is easy to understand and navigate. | Limited flexibility to handle complex relationships. |
| Fast access to data. | Data redundancy. |
|  | Difficulty in accommodating changes to the hierarchy. |

Network Database Model

| Pros | Cons |
| --- | --- |
| Ability to handle more complex relationships. | Complexity of the structure. |
| More flexible than the hierarchical model. | Limited support from modern database management systems. |
| Speed of access. | Difficulty in finding data that is not directly related to the starting point. |

Relational Database Model

| Pros | Cons |
| --- | --- |
| Simple structure that is easy to understand and maintain. | Need for a sound understanding of data normalization. |
| Flexibility to accommodate complex relationships. | Performance issues with large datasets. |
| Ability to enforce data integrity. | Limited ability to handle objects or non-tabular data. |
| Widely used and supported. |  |

Object-Oriented Database Model

| Pros | Cons |
| --- | --- |
| Ability to handle complex objects and relationships. | Lack of standards. |
| More flexible than the relational model. | Limited support from modern database management systems. |
| Improved performance with large datasets. | Difficulty in integrating with existing relational databases. |
| Support for object-oriented programming features such as inheritance and polymorphism. | Complexity of implementation. |


### Hierarchial Database Model
- Each Parent Has Many Children
- Each Children Has only one parent
- A single table acts as root while other tables branch out from this table
- Relationship is children and parents
- TIed together by links


## Functions of a RDBMS:
- Data Storage, Retrieval and update
- User Accessible Catalog
- Transaction Support
- Concurrency Control Services
- Recovery Services
- Authorization Services
- Data Communication
- Integrity Services
- Services to promote data independence

Query -> Transaction -> Journal -> Buffered -> OS

## Metadata 
Metadata can be defined as data about data or it is the value that leads us to actual data.
- Technical Metadata (Table, DB names, Tabel size, datatype, values and attributes, foriegn key, primary keys)
- Business Metadata (Business Rules and Regulations, change in policies, ownership of data)
- Operational Metadata (Same as Business Metadata)
- Descriptive Metadata (data about file,folders, book, images etc like title, author, size)
- Metadata stores names of user authorized to access the DBMS
- Names of all data items in the database
- Column names there datatype and constraints on them is Metadata.

# Relational Model
- Degree of Data Independence
- Data semantic, consistency and redundancy problems
- Allows Set of operations throught data manipulation language like SQL

## Properties of Relation
- Distinct relation name
- Each cell contain one atomic value
- Distince attribute value
- Order of attributes does not matter

A Tuple is the instance of data in a column like in firstname "Zohaib" is a tuple

## Identifying Tuple
- Super Key (Uniquely identify a tuple)
- Candidate Key (A super key with no subset)
- Primary Key (A candidate key which is used to identify tuples uniquely in a relation)
- Composite Primary Key(Primary Key on Multiple Attributes)
- Surrogate Key
- Foriegn Key

## Criteria for a Primary Key
- Attribute remains same over the life of identity (Never Changes)

## Relational Integrity
- Entity Integrity (No attribute of a primary key can be null, Every Tuple should be uniquely identified).
- Refrencial Integrity 




# ERD
An ERD is a visual representation of entities and their relationships that helps to organize and understand complex data. It consists of three main components: entities, attributes, and relationships.

1. Identify Entities: Begin by identifying the main entities in the system you are designing. An entity is a representation of a real-world object or concept, such as a customer, order, or product.

2. Define Attributes: For each entity, identify the attributes, or characteristics, that are associated with it. For example, a customer entity might have attributes such as name, address, and phone number.

3. Identify Relationships: Examine the relationships between the entities to determine how they interact with one another. Relationships can be one-to-one, one-to-many, or many-to-many.

4. Create a Diagram: Using a diagramming tool, such as Lucidchart or Visio, create a visual representation of the entities, attributes, and relationships. Entities are represented as rectangles, attributes as ovals, and relationships as diamonds.

5. Specify Cardinality: For each relationship, specify the cardinality, or number of entities that can be involved in the relationship. For example, a one-to-many relationship between customers and orders would indicate that each customer can have many orders, but each order is associated with only one customer.

6. Add Additional Details: Include any additional details, such as constraints or business rules, that are relevant to the system design.

7. Refine and Review: Refine and review the diagram to ensure that it accurately represents the relationships and meets the requirements of the system design.
