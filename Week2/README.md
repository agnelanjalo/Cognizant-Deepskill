# Database Integration

This repository contains the hands-on exercises completed as part of the **Digital Nurture 5.0 – Python Full Stack Engineer Track** for the **Database Integration** module.

## Database Schema

A PostgreSQL database named `college_db` (and `college_db_orm` for the ORM/migration exercises) was created based on the given Student Course Registration System. The schema includes all required tables, relationships, constraints, and sample data provided in the hands-on exercise book.

`Hands_On_1/hands_on_1.sql` contains:

* Database creation
* Table creation
* Primary Key and Foreign Key constraints
* Normalisation (1NF–3NF) notes
* ALTER TABLE schema changes

`Hands_On_2/hands_on_2.sql` contains the sample data insertion (departments, students, courses, enrollments, professors) used across all later exercises.

## Hands-On Exercises

Each hands-on exercise is organised in its own directory.

* Every SQL exercise is saved as `hands_on_{n}.sql`, where `n` is the exercise number.
* MongoDB exercises are saved as `.js` scripts for `mongosh`.
* SQLAlchemy ORM and Alembic exercises are implemented using Python.
* Every hands-on directory contains a dedicated `README.md` explaining the objectives, implementation, and expected outcomes.

## Folder Structure

```
Module3_DatabaseIntegration/
│
├── README.md
│
├── Hands_On_1/
│   ├── hands_on_1.sql
│   └── README.md
│
├── Hands_On_2/
│   ├── hands_on_2.sql
│   └── README.md
│
├── Hands_On_3/
│   ├── hands_on_3.sql
│   └── README.md
│
├── Hands_On_4/
│   ├── hands_on_4.sql
│   ├── hands_on_4_n1_problem.py
│   └── README.md
│
├── Hands_On_5/
│   ├── hands_on_5_mongodb.js
│   └── README.md
│
├── Hands_On_6/
│   ├── models.py
│   ├── crud.py
│   └── README.md
│
└── Hands_On_7/
    ├── README.md
    └── migrations/
        ├── env.py
        ├── README.md
        └── versions/
            ├── 0001_initial_schema.py
            ├── 0002_add_is_active.py
            └── 0003_add_course_schedule.py
```

## Topics Covered

* Database Schema Design
* SQL DDL, DML and DQL Operations
* Joins and Aggregate Functions
* Subqueries, Views, Stored Procedures/Functions
* Transactions — COMMIT, ROLLBACK, SAVEPOINT
* Query Optimization and Indexing
* EXPLAIN and Query Execution Plans
* N+1 Query Problem
* MongoDB CRUD Operations
* Aggregation Pipeline
* SQLAlchemy ORM
* ORM Relationships and CRUD Operations
* Eager Loading (joinedload) to Resolve N+1
* Alembic Database Migrations
* Database Versioning and Rollback

## Technologies Used

* PostgreSQL
* MongoDB
* Python
* SQLAlchemy
* Alembic
* psycopg2
* MongoDB Shell (mongosh)
* Visual Studio Code

## Learning Outcomes

After completing this module, I gained practical experience in:

* Designing and creating relational database schemas.
* Writing SQL queries for data retrieval and manipulation.
* Optimising database performance using indexes and query execution plans.
* Working with MongoDB collections, CRUD operations, and aggregation pipelines.
* Building database applications using SQLAlchemy ORM.
* Managing schema changes through Alembic migrations.
* Understanding database versioning, migration history, and rollback strategies.

## Conclusion

This repository demonstrates the practical implementation of database concepts using PostgreSQL, MongoDB, SQLAlchemy ORM, and Alembic. The hands-on exercises cover database design, querying, optimisation, NoSQL operations, ORM integration, and schema versioning, providing a strong foundation in database integration for Python Full Stack development.
