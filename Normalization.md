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