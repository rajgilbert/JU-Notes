# DBMS

* For long integer ```bigint```
* Primary Key can never be NULL but unique key can be
* To remove a column ```Alter table table-name drop column-name```
* To Update Values ```Update Table-name Column-name=value where condition```
* To Delete Values ```Delete from Table-name where condition```
* Query Optimization ~> The query optimizer attempts to determine the most efficient way to execute a given query by considering the possible query plans.

* Anomally
Anomalies are problems that can occur in poorly planned, un-normalised databases where all the data is stored in one table (a flat-file database).

Insertion Anomaly - The nature of a database may be such that it is not possible to add a required piece of data unless another piece of unavailable data is also added. E.g. A library database that cannot store the details of a new member until that member has taken out a book.

Deletion Anomaly - A record of data can legitimately be deleted from a database, and the deletion can result in the deletion of the only instance of other, required data, E.g. Deleting a book loan from a library member can remove all details of the particular book from the database such as the author, book title etc.

Modification Anomaly - Incorrect data may have to be changed, which could involve many records having to be changed, leading to the possibility of some changes being made incorrectly.

* Problems with File System:
    1. Data Redundancy: It is possible that the same information may be duplicated in different files. ...
    2. Data Inconsistency: ...
    3. Difficulty in Accessing Data: ...
    4. Limited Data Sharing: ...
    5. Integrity Problems: ...
    6. Atomicity Problems: ...
    7. Concurrent Access Anomalies: ...
    8. Security Problems:

## Keys
* it is used for identifying unique rows from table. It also establishes relationship among tables.
    1. Primary Key – A primary is a column or set of columns in a table that uniquely identifies tuples (rows) in that table and is not NULL.

    2. Super Key – A super key is a set of one of more columns (attributes) to uniquely identify rows in a table.

    3. Candidate Key – A super key with no redundant attribute is known as candidate key. There can be more then one candidate key.

    4. Alternate Key – Out of all candidate keys, only one gets selected as primary key, remaining keys are known as alternate or secondary keys.

    5. Composite Key – A key that consists of more than one attribute to uniquely identify rows (also known as records & tuples) in a table is called composite key.

    6. Foreign Key – Foreign keys are the columns of a table that points to the primary key of another table. They act as a cross-reference between tables.

* What is the Domain of an attribute
    It is the type of value that is present that is int,string,char etc.

* Normalisation
    1. Functional Dependency ~> Analyse on which dependency database is set, Relationship between two attributes
    2. Remove redundancy
    3. Minimise Insertion/Deletion/Update anomalies

* Types of languages in DBMS
    1. DDL  ~> Data Definition Language (Create/Alter/Drop/Truncate)
    2. DML ~> Data Manipulation Language (Select,Insert,Update)
    3. DCL ~> Data Control Language (Grant/Revoke)
    4. TCL ~> Trasaction Control Language (Commit/Roll back)
    5. VDL ~> View Definition Language

* Levels of abstraction in DBMS
    1. Physical ~> This is the lowest level of data abstraction. It describes how data is actually stored in database. You can get the complex data structure details at this level.
    2. Logical ~> It describes what data is stored in database
    3. View ~> This level describes the user interaction with database system.

* Aggregation
    1. Maintain relationship between 2 RDBMS
    2. Feature of Entity relation model which allow 1 relationship set to participate with another Relationship set
    3. How more then one record collectively represent a dataset

* Properties of Transaction are ACID properties
* Locking Scheme in Transaction:
    1. Shared Lock ~> Other transaction can only read and not write (paise nikalte samey)
    2. Exclusive Lock ~> Other transaction can neither read nor write (for other operations like pin change karna/check balance)

* UNIQUE Key can be NULL for once only
* Triggers
    * Set of commands executed when certain event occurrs
* Stored Procedure is basically a set of SQL queries that are executed all together in a pre-maded sequence

* the most commonly used normal forms:
    1. First normal form(1NF) ~> A relation is in first normal form if every attribute in that relation is singled valued attribute.
    2. Second normal form(2NF) ~> A relation must be in first normal form and relation must not contain any partial dependency.
    3. Third normal form(3NF) ~> Transitive dependencies are removed in this form
    4. Boyce & Codd normal form (BCNF)

* Weak Entity Set
    A weak entity set is an entity set that does not contain sufficient attributes to uniquely identify its entities
* Multivalue Attrivute
    An attribute that can hold multiple values is known as multivalued attribute. It is represented with double ovals in an ER Diagram.
* Strong Entity Set
    A strong entity set is an entity set that contains sufficient attributes to uniquely identify all its entities.

* Functional Dependency
    1. It is of 2 types:
        * Trival
        * Non-Trival
* Inference Rule

* Partial Dependency
    Partial Dependency occurs when a nonprime attribute is functionally dependent on part of a candidate key.
* Fully-functionally Dependency
    An attribute is fully functional dependent on another attribute, if it is Functionally Dependent on that attribute and not on any of its proper subset.

* Concurrency Control ~> Concurrency control is the procedure in DBMS for managing simultaneous operations without conflicting with each another. It helps you to make sure that database transactions are performed concurrently without violating the data integrity of respective databases.

# Data Model
<a href="https://afteracademy.com/blog/what-is-data-model-in-dbms-and-what-are-its-types">Learn More</a>

* Data Model gives us an idea that how the final system will look like after its complete implementation.
* Some of them are:
1. Hierarchical Model ~> Hierarchical Model was the first DBMS model. This model organises the data in the hierarchical tree structure. The hierarchy starts from the root which has root data and then it expands in the form of a tree adding child node to the parent node.

2. Network Model ~> a record can have more than one parent.

3. Entity-Relationship Model ~> the real-world problem in the pictorial form to make it easy for the stakeholders to understand. 

4. Relational Model ~> In this model, the data is maintained in the form of a two-dimensional table. All the information is stored in the form of row and columns. The basic structure of a relational model is tables. So, the tables are also called relations in the relational model.

5. Object-Oriented Data Model ~> both the data and relationship are present in a single structure known as an object. 

6. Object-Relational Data Model ~> This model was built to fill the gap between object-oriented model and the relational model. We can have many advanced features like we can make complex data types according to our requirements using the existing data types.

7. Flat Data Model ~> It is a simple model in which the database is represented as a table consisting of rows and columns. To access any data, the computer has to read the entire table. This makes the modes slow and inefficient.

8. Semi-Structured Data Model
Associative Data Model
Context Data Model



# Basics
* To connect to database ```\connect root@localhost:3306```
* To disconnect from database ```\quit```
* To change language from ```JS``` to ```SQL``` use ```\sql```
* To Create a database ```create database db-name```
* To Create a table 
```sql
create table tb-name(
    col1-name data-type,
    col2-name data-type
);
```
* To check the schema of table ```describe tb-name```
* To insert row ```insert into tb-name(col1-name,col2-name) values("piyush",12);``` or ```insert into tb-name values("piyush",12);```

* To delete rows ```delete from tb-name where condition```
* To update rows ```update tb-name set col-name=new-value where condition```