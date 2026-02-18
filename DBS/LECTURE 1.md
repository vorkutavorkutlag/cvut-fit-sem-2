 The goal is understanding not only SQL queries, rather comprehend database logic. You will need not only queries, rather conceptual modelling.
 Will be using database system postgress. Short test in midterm. Ability to design system and queries.
 Semestral work... create, normalize, transfer databases.
 Use MS Teams for communication.

Working on theory in the beginning. No homework... Can make project during labs.

use cookbook, not courses page for lecture slides.

For designing databases first describe what you wish. Then ask what entities exist, and the relation by entities (schema).

Database introduction.
Conceptual, Database, Physical view.

Database is list of records, as are characters numbers, diagrams.
Their systematic structure allows these records searches.
Data - recorded message.
Information - message that can change our knowledge. Information as row data placed into context.

DB - Database
DBS - Database System
DBMS - Database Management System

Data must be persistent (not lost), reliable (able to change), and shared.
DB  benefits include: data independence from the application, effectiveness, fast appdev, data integrity, data management and backup sys, transaction processing, parallel processing, recovering after error.

RDBMS (relational) interface. Comms ensured by SQL (Structured Query Language)
DDL - Data Definition Language (data definition) $\implies$ `CREATE TABLE teachers(id int name varchar(255));`
DML - Data Manipulation Language (inserts queries)
TCL - Transaction Control Language $\implies$ `COMMIT, ROLLBACK;`
DCL - Data Control Language (permissions) $\implies$ `GRANT INSERT, UPDATE ON teachers TO 'Pavlicek'`

Conceptual Modelling has to do with relations. Similar to Discrete Math relations(?)
It fragments into entities (classes), relations (associations), attributes.
Analytic concept. How data is related to other data.

Triangle in end of connections means `has many` relation.