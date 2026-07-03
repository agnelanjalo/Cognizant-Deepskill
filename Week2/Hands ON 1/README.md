# Hands-On 1 — Schema Design & Core SQL (Beginner)

## Topics
Database schema design, normalisation (1NF–3NF), ER relationships, DDL (CREATE/ALTER/DROP), referential integrity.

## File
`hands_on_1.sql`

## What it does
- **Task 1:** Creates the `college_db` database and all 5 tables (`departments`, `students`, `courses`, `enrollments`, `professors`) with PK/FK/UNIQUE/NOT NULL constraints.
- **Task 2:** Documents 1NF, 2NF, 3NF compliance as SQL comments, with a focus on the `enrollments` composite key.
- **Task 3:** Extends the schema with `ALTER TABLE` — adds `phone_number`, `max_seats`, a `CHECK` constraint on `grade`, renames `hod_name` → `head_of_dept`, then drops `phone_number` to simulate a rollback.

## How to run
```bash
psql -U postgres -f hands_on_1.sql
```
(For MySQL, swap `SERIAL` → `AUTO_INCREMENT` and use `CHANGE` instead of `RENAME COLUMN`.)

## Expected outcome
All 5 tables created with no errors; `\d students` (or `DESCRIBE students`) shows the final columns and constraints.
