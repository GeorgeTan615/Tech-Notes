## What are Relational databases
Data is organized in tables, where columns are attributes and rows represent records

## What are NoSQL databases
A database data is stored in a non-relational structure, thus its schemaless and avoids joins. Due to its scalability, high performance and flexible nature, its popularity is rising in Big data and real time applications.
- Type of NoSQL Databases
	- Key Value Stores
	- Document oriented database
	- Column Stores
	- Graph Databases

## Comparison between both
![Comparison](https://cdn.discordapp.com/attachments/776828668386213908/1090679683839955004/image.png)

## Which is more scalable?
NoSQL is more scalable as horizontal and vertical scaling can be done for NoSQL databases, meanwhile horizontal scaling is difficult for relational databases.

It is also cheaper to do horizontal scaling, plus vertical scaling has a limit. Thus relational databases that can only perform vertical scaling is limited in that sense.

Horizontal scaling for relational databases is hard because:
- relational databases are designed to run on a single server
- relational databases are designed to guarantee ACID compliance, which means transactions have to be executed in a certain order and in a consistent manner. When horizontal scaled, transactions may be executed on different servers, which makes it harder to guarantee consistency.
- data partitioning is difficult because we need a very good partitioning strategy to spread data across multiple servers, and this is difficult when the data is highly interconnected.

## Which is faster?
TLDR = NoSQL
- NoSQL is not acid, it is designed to be faster by forgoing one of the ACID properties.
- NoSQL stores commonly accessed data together as we are avoiding joins, thus they have better performance on reads/writes on a single entity.
- Due to NoSQL's schemaless nature, NoSQL avoids the computation power needed to validate schema changes during data changes, unlike SQL, thus leading to higher write operations per second.
- NoSQL is slower when it comes to complex queries as data in relational databases are broken down and stored in tables. Joins in NoSQL are done by retrieving the multiple entities and joining them manually.
- Indexes are more efficient for SQL, indexes work by duplicating existing data and efficiently storing them in the RAM. They work better for structured data and thus SQL benefits from it.

## Which is more secure?
TLDR = SQL <br/>
Confidentiality - only authorized users can access <br/>
Integrity - accuracy and consistency of data <br/>
Availability - data is available when needed <br/>
- SQL guarantees ACID transaction, NoSQL does not and thus lacks confidentiality and integrity. This means a race condition (two threads access a shared variable at the same time) is an issue and simultaneous transactions can affect each other.
- NoSQL has minimal in-built security feature, have to build them into your app instead
- Horizontal scaling has higher availability, so NoSQL benefits more from this

## Pros of SQL
- Reduced data storage
	- Normalization removed data redundancy and duplication
- ACID compliant
	- Strong data integrity, security and consistency
- Normalization
	- Database engines are better at optimizing queries to fit on desk representations
- Great for complex queries
	- SQL is efficient at processing queries and joining data across tables
- Predefined schema
	- Validations are done on the database layer and not the application layer
- Standardized language across different RDBMS

## Cons of SQL
- Vertical scaling is more expensive than horizontal scaling
- Rigid data model, require up front design and changes are harder to make 
- Single point of failure, mitigated by replication and failover techniques

## Pros of NoSQL
- Schemaless, easy to make changes
- Flexible data model, each entity can have its own structure
- Horizontal scaling, relatively cheaper and easier esp for Big data
- Highly performant, data that is accessed together are typically stored together

## Cons of NoSQL
- Less secure, difficult to verify data integrity and consistency (only can achieve eventual consistency)
- Schemaless, lacks standardization of data types
- No normalization, database engines are not as good at optimizing queries
- Larger data storage, lack of normalization leads to more duplicated data stored. But is a relatively small drawback as storage is cheap
- 
