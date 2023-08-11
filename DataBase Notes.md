# Database Modeling and Development

Our main goal is database modeling and development, with a focus on understanding key concepts and techniques in this field.

## Recommended Books

* Modern Database Management (11th Edition) by Jeffrey A. Hoffer, Ramesh Venkataraman, Heikki Topi
* Database Systems: A Practical Approach to Design, Implementation and Management (4th Edition) by Thomas M. Connolly, Carolyn E. Begg

## Introduction to Databases

A **database** is a shared collection of logically related data and a description of this data, designed to meet the information needs of organizations. It consists of entities, attributes, and relationships that represent an organization's information.

### Database Management Systems (DBMS)

A **DBMS** is a software system that enables users to define, create, maintain, and control access to a database.

#### Components of DBMS

* **Data Definition Language (DDL)**: Specifies data types, structure, and constraints.
* **Data Manipulation Language (DML)**: Allows querying and manipulation of data.
* Controlled Access: Ensures data security and integrity.

## File Systems vs. DBMS

### File-Based Systems

A collection of application programs where each program manages its own data. Limitations include data redundancy, isolation, and data dependence.

## Organizing Data

1. Entity: Distinct objects (e.g., person, place, thing)
2. Attribute: Characteristics of entities
3. Relationship: Associations between entities

## Components of a Database Environment

* **Hardware**: Servers, PCs
* **Software**: DBMS, DDL, DML
* **Data**: Organized in schema, divided into sub-schemas
* **Procedures**: Govern design, access, and use of the database
* **People**: Administrator DBA, designers, application developers, users

## Advantages of Database Approach

* Control over data redundancy
* Data consistency
* Greater information gain
* Data sharing
* Improved data integrity, validity, and consistency
* Access and security improvement
* Standards enforcement
* Economy of scale
* Increased productivity
* Data independence and maintenance
* Increased concurrency
* Backup and recovery improvements

## Disadvantages of Database Approach

* Complexity and resource requirements
* Costs (DBMS, hardware, conversion)
* Impact of failure
* Slower processing in production environments

# Creating Data Flow Diagrams (DFD)

1. Create a list of activities.
2. Create a context level DFD (identify sources and sinks).
3. Construct Level 0 DFD (manageable sub-processes).
4. Construct Level 1 DFD (actual data flow and data resources).
5. Check against DFD rules.

### Naming Guidelines

* External entities should be nouns.
* Data flows and processes should be verb phrases.
* Data stores should be nouns.

## Schema and Subschema

A **schema** is a complete catalog of data stored in a database. It includes **sub-schemas**, which are individual views of the data.

### Three-Level Architecture

1. **External Schema**: User view of the database.
2. **Conceptual Schema**: Community view (what data is stored?).
3. **Internal View**: Physical representation (how data is stored?).

## Data Independence

- **Logical Data Independence**: Changes in external schema don't affect conceptual schema.
- **Physical Data Independence**: Changes in conceptual schema don't affect internal schema.

## Database Languages

- Data Definition Language (DDL)
- Data Manipulation Language (DML)

# Database Models

## Data Models

- DDL, DML, Constraints
- Database Models
  - Conceptual Models
    - Entity-Relationship Database Model
    - Object-Oriented Database Model
  - Implementation Models
    - Hierarchical Database Model
    - Network Database Model
    - Relational Database Model
    - Object-Oriented Database Model

### Hierarchical Database Model

| Pros                                     | Cons                                     |
| ---------------------------------------- | ---------------------------------------- |
| Simple structure, easy to understand      | Limited flexibility for complex relations |
| Fast access to data                      | Data redundancy                          |
|                                          | Difficulty accommodating hierarchy changes |

### Network Database Model

| Pros                                  | Cons                                           |
| ------------------------------------- | ---------------------------------------------- |
| Handles complex relationships         | Complex structure                              |
| More flexible than hierarchical model | Limited modern DBMS support                    |
| Fast access to data                   | Difficulty in finding unrelated data           |

### Relational Database Model

| Pros                                       | Cons                                  |
| ------------------------------------------ | ------------------------------------- |
| Simple structure, easy to understand       | Need for understanding normalization |
| Flexibility for complex relationships      | Performance issues with large data   |
| Data integrity enforcement                | Limited support for objects          |
| Widely used and supported                 |                                     |

### Object-Oriented Database Model

| Pros                                    | Cons                                     |
| --------------------------------------- | ---------------------------------------- |
| Handles complex objects and relationships | Lack of standards                        |
| More flexible than relational model      | Limited modern DBMS support              |
| Improved performance with large datasets | Difficulty integrating with relational DBs |
| Supports OOP features (inheritance, polymorphism) | Complex implementation               |

## Relational Model

- Offers degree of data independence
- Addresses data semantic, consistency, and redundancy problems
- Provides set operations through SQL (Structured Query Language)

### Properties of a Relation

- Distinct relation name
- Each cell contains one atomic value
- Distinct attribute values
- Order of attributes doesn't matter

## Identifying Tuples

- **Super Key**: Uniquely identifies a tuple
- **Candidate Key**: Super key with no subsets
- **Primary Key**: Candidate key used to identify tuples uniquely
- **Composite Primary Key**: Primary key on multiple attributes
- **Surrogate Key**: Artificial key introduced for uniqueness

## Criteria for a Primary Key

- Attribute remains the same over the life of identity

## Relational Integrity

- **Entity Integrity**: No attribute of a primary key can be null; every tuple uniquely identified.
- **Referential Integrity**: Relationship between foreign and primary keys maintained.

# Entity-Relationship Diagram (ERD)

An ERD is a visual representation of entities, attributes, and relationships in a system.

## Steps to Create an ERD

1. Identify Entities
2. Define Attributes
3. Identify Relationships
4. Create a Diagram
5. Specify Cardinality
6. Add Additional Details
7. Refine and Review
