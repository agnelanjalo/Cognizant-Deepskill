# Hands-On 2 — Writing SQL Queries: DML, Joins & Aggregations (Beginner)

## Topics
DML (INSERT/UPDATE/DELETE), SELECT with WHERE/ORDER BY, INNER/LEFT JOIN, aggregate functions, GROUP BY / HAVING.

## File
`hands_on_2.sql`

## What it does
- **Task 1:** Loads all sample data, inserts 2 extra students, updates a grade, deletes ungraded enrollments, verifies row counts.
- **Task 2:** Single-table filtering — students by enrollment year, high-credit courses, salary range, email pattern match, student counts per year.
- **Task 3:** Multi-table joins — student + department, 3-table enrollment view, students with no enrollments (LEFT JOIN), courses with zero enrolments, departments with no professors.
- **Task 4:** Aggregations — enrollments per course, average salary per department, high-budget departments, grade distribution for CS101, HAVING filter on enrollment counts.

## How to run
```bash
psql -U postgres -d college_db -f hands_on_2.sql
```
Requires the schema from Hands-On 1 to already exist.

## Expected outcome
`students` table has 10 rows; `enrollments` has only non-NULL grades after the DELETE; join/aggregate queries return the row counts noted in the exercise book.
