## Database Normalization

Database normalization is the process of organizing the attributes of the database to eliminate data redundancy (having the same data but at different places).

It helps improve the database’s efficiency, consistency and accuracy.

Normalization resolves some of the following issues:

- Insertion anomalies: These occur when it is impossible to insert data into a database because the required fields are missing or because the data is incomplete.

- Deletion anomalies: These occur when deleting a record from a database and can result in the unintentional loss of data.

- Updating anomalies: They occur when modifying data in a database and can result in inconsistencies or errors. For example, if a database contains information about employees and their salaries, updating an employee’s salary in one record but not in all related records could lead to incorrect calculations and reporting.

### Prerequisites for database normalization

- Keys - A key is a unique identifier in a table. For example, in a table of students, the student ID is a key because it uniquely identifies each student. Keys ensure that data is not duplicated and that every record can be uniquely accessed.

- Functional dependency - This helps define the relationships between data in a table. For example, if you know a student’s ID, you can find their name, age and class. 

### Benefits of database normalization
1. Elimination of data redundancy to improve the efficiency and consistency of the database.  Data redundancy refers to the repetition of data in different parts of the database.

2. Ensuring data consistency and accuracy by eliminating redundancy.

3. Simplification of data management by breaking down a complex data structure into simpler tables. This makes it easier to manage the data, update and retrieve it.

4. Improved database design by organizing the data in a structured and systematic way. It also makes the database more flexible and adaptable to changing business needs.

5. Avoiding update anomalies which can occur when updating a single record in a table affects multiple records in other tables.

6. Standardizing the data in the database by organizing the data into tables and defining relationships between.

### Disadvantages of normalization

- Normalization can result in increased performance overhead due to the need for additional join operations and the potential for slower query execution times.

- It can result in the loss of data context, as data may be split across multiple tables and require additional joins to retrieve.

- Proper implementation of normalization requires expert knowledge of database design and the normalization process.

- Normalization can increase the complexity of a database design, especially if the data model is not well understood or if the normalization process is not carried out correctly.

### Types of normalization

### First Normal Form (1NF)

For a table to be in the 1NF, it must meet the following criteria:

- a single cell must not hold more than one value (atomicity).

- There must be a primary key for identification.

- No duplicated rows or columns.

- Each column must have only one value for each row in the table.


|employee_id | name	job_code | job	state_code | home_state |
|------|------ |------|------- |
|E001|	Alice|	J01|	Chef|	26|	Michigan|
|E001|	Alice|	J02	|Waiter|	26|	Michigan|
|E002|	Bob	|J02|	Waiter	|56|	Wyoming|
|E002	|Bob|	J03|	Bartender|	56|	Wyoming|

### Second Normal Form (2NF)

The 1NF only eliminates repeating groups, not redundancy.

A table is said to be in 2NF if it meets the following criteria:

-It’s already in 1NF.

- Has no partial dependency, that is, all non-key attributes are fully dependent on a primary key.

employee_roles Table

|employee_id	|job_code|
|------|------ |
|E001|	J01|
|E001|	J02|
|E002|	J02|
|E002|	J03|

employees Table

|employee_id	|name|	state_code|	home_state|
|------|------ |------|------- |
|E001|	Alice|	26|	Michigan|
|E002|	Bob	|56	|Wyoming|

### Third Normal Form (3NF)

When a table is in 2NF, it eliminates repeating groups and redundancy, but it does not eliminate transitive partial dependency.

This means a non-prime attribute (an attribute that is not part of the candidate’s key) is dependent on another non-prime attribute. 

employees Table

|employee_id|	name	|state_code|
|------|------ |
|E001	|Alice|	26|
|E002	|Bob	|56|
|E003	|Alice|	56|

states Table

|state_code	|home_state|
|------|------ |
|26|	Michigan|
|56|	Wyoming|
