## What does ACID mean in database systems?
ACID refers to a standard set of properties that guarantee database transactions are processed reliably. ACID is especially concerned with how a database recovers from any failure that might occur while processing a transaction. An ACID-compliant DBMS ensures that the data in the database remains accurate and consistent despite any such failures.

## Atomicity
Guarantee that either all of the transaction succeeds or none of it does. If one part of the transaction fails, the whole transaction fails.

## Consistency
Guarantee that all data will be consistent. All data will be valid according to all defined rules, including constraints, cascades and triggers that have been applied to the database.

## Isolation
Guarantees that all transactions will occur in isolation. No transaction will be affected by any other transaction. So a transaction cannot read data from another transaction that has not yet been completed.

## Durability
Means that once a transaction is completed, it will remain in the system. Even if the system crashes immediately following after the transaction, the transaction should still remain in the system. Any changes from the transaction must be stored permanently.