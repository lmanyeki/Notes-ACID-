## ACID Transactions

### Transactions

Database transactions are a group of database read and write operations that have been completed successfully.

- Single transactions: This refers to a series of one or more database operations resulting in one action, **completed successfully**. Once complete, the transaction is accepted and can be found in a transaction log. An example is the withdrawal of money from an ATM.

- Multi-transactions: Sometimes called a distributed transaction, consists of multiple, interdependent transactions spread across different databases and systems (e.g., distributed systems). Records of these transactions are also found in a transaction log. Examples include transferring money from one account to another or an employer issuing a new employee a security badge with a photo.

## ACID Properties

An acronym that stands for Atomicity, Consistency, Isolation and Durability.

They ensure that a set of database operations leave the database in a valid state even in the event of unexpected errors.

### Atomicity
Atomicity guarantees that all of the commands that make up a transaction are treated as a single unit and either succeed or fail together. 

This is important in the event of a system failure or power outage, in that if a transaction wasn't completely processed, it will be discarded and the database maintains its data integrity.

It uses transaction logs to record changes before they're applied and implements rollback mechanisms to undo changes if needed.

**Example**:  In a bank transfer, both the debit from one account and credit to another must succeed together. If either fails, both operations are canceled.

### Consistency
Consistency guarantees that changes made within a transaction are populated across the database system and in alignment with DBMS invariants such as rules, constraints and triggers.

If data consistency is going to be negatively impacted by a transaction in an inconsistent state, the entire transaction will fail.

**Example**: If a database requires that account balances never go negative, any transaction that would violate this rule is aborted.

### Isolation
Each transaction is isolated from the other transactions to prevent data conflicts. 

This also helps database operations in relation to managing multiple entries and multi-level transactions. 

It uses locking mechanisms (shared locks, exclusive locks) and implements multi-version concurrency control (MVCC).

May use optimistic concurrency control in some systems.

**Example**: If two users are trying to modify the same data (or even the same transaction), the DBMS uses a mechanism called a lock manager to suspend other users until the changes being made by the first user are complete.

### Durability
Durability guarantees that once the transaction completes and changes are written to the database, they are persisted. 

This ensures that data within the system will persist even in the case of system failures like crashes or power outages. 

This utilizes Write-ahead logging (WAL), where changes are logged before being applied.

Transaction logs are stored on durable storage and periodic backups and replication for additional protection.

**Example**: After a customer receives confirmation that their bank transfer was successful, they can be certain the transaction won't be lost even if the database server crashes immediately afterward.

### Importance of ACID transactions

- Maintain data integrity and reliability.

- Ensuring that vital data which is subject to governmental or industry regulation  meet required standards. 

- ACID compliance is often a prerequisite for implementing data replication in distributed database systems.


