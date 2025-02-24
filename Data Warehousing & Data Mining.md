# Data Warehousing & Data Mining

**OLAP :** Online Analytical Processing System

**OLTP :** Online Transactional Processing System

**MOLAP :** Multi-dimensional Online Analytical Processing System

### OLTP :

- OLTP systems are designed for managing and processing day-to-day, operational transactions.
- Typically use normalized relational databases with tables and rows.
- Used in applications like e-commerce, banking, and order processing where quick and efficient data manipulation is critical.

### OLAP :

- OLAP systems are geared towards complex, analytical queries and reporting on historical data.
- Utilizes a multidimensional data model, often in the form of data cubes, with dimensions and measures.
- Employed in business intelligence and data warehousing for decision-making, trend analysis, and reporting.

### MOLAP :

- MOLAP is a subset of OLAP that specifically employs multidimensional data storage.
- MOLAP systems store data in a proprietary, highly compressed format for optimized analytical performance.
- Used in scenarios where fast query response times and interactive data exploration are essential, such as in financial analysis and sales reporting.

### Why OLTP Cannot be used for analysis purposes?

- OLTP is normalized and it cannot run complex analytical queries because it will slow down the system and day-to-day transactions will be effected.
- OLTP are optimizes for data integrity, transaction speed and efficiency so the tables are split into multiple tables and requires use of joins for data retrieval.
- OLTP contains real time data but for analysis we need Historical data.
- OLTP contains small amount of data while for analysis we need large dataset.
- OLTP uses normalized model while for analysis we need Multi-dimensional model or data cubes.

### Strategic Information:

The information in the context of business and management, refers to data, facts or insights which are crucial for making long-term decisions and shaping overall directions of an organization.

### Information Crisis :

Information Crisis means the Lack of Information. Data must be large and in diverse format in a format which helps the identifying the trends and patterns easily. The incapability of system or IT to turn the data into usable form.

### History of Decision Support Systems :

- `Ad-Hoc Reports :` Small Programs for each type of reports
- `Special Extract Programs :` Collection of Programs for reports
- `Small Applications :` Small programs for taking parameters from users for generating of reports.
- `IT Centers :` Specialized places where people go for asking pre-generated reports.
- `Decision Support Systems :` Sophisticated Systems, menu driven, online processing, printable reports but were made using extracted files.
- `Executive Information Systems :` Simple reports on user's desktop but again pre-programmed.

### Failure of Decision Support Systems :

- Cannot Provide Strategic Information
- Too many Ad-Hoc Requests by the Users
- Requests Change Over-Time
- Less Performance and Slow
- Rigid Strategic Information is provided in Decision Support Systems

### Data Warehouse Capabilities :

- Provides Enterprise View of the Data.
- Current and historical Data available.
- Analysis possible without disturbing any transactional system.
- Ability for user to generate reports without IT Professionals.
- Data Source for all analytical applications.

### Definition of Data Warehouse :

A data warehouse is a subject-oriented, integrated, non-volatile, time-variant collection of data in favor of decision-making.

`Separate, available, integrated, time-stamped, subject-oriented, non-volatile and accessible`

### Four Properties of Data Warehouse :

- Subject-Oriented
- Integrated Data
- Time Variant
- Non-Volatile

### Major Components :

- Source Data Component
- Data Staging Component
- Data Storage Component
- Information Delivery Component
- Metadata Component
- Management and Control Component

`Source Data` can be grouped into four components:

   - Production Data
   - Internal Data
   - Archived Data
   - External Data

`Data Staging Component :` After Data is extracted, data is to be prepared, changed, converted and formatted. Extract → Transform → Load

`Data Storage Component :` Separate Repository, Data Structured for processing, Increased Redundancy, Updated after specific period, Read Only.

`Information Delivery Component :` Depending upon the type of user the different methods of delivery are used.

`Metadata Component :` Information about the data in the warehouse

   - `Operational Meta-data :` Information about mapping between source system and warehouse.
   - `Extraction & Transformation Meta-data :` Like Extraction Frequencies, Extraction Methods and Data Transformation.
   - `End User Meta-data :` Supports users to navigate information about their own terminologies.

`Management and Control Component :` Concerned to control all the activities in the Data Warehouse Environment.

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Data+Warehousing+&+Data+Mining.md&fileType=undefined&fileExtension=md