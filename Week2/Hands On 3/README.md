# Hands-On 3 — Advanced SQL: Subqueries, Views & Transactions (Intermediate)

## Topics
Correlated & non-correlated subqueries, views (incl. `WITH CHECK OPTION`), stored procedures/functions, transactions (`COMMIT`/`ROLLBACK`/`SAVEPOINT`).

## File
`hands_on_3.sql`

## What it does
- **Task 1:** Subqueries — students enrolled above average, courses where every student got an 'A', top-paid professor per department, derived-table filter on department average salary.
- **Task 2:** Views — `vw_student_enrollment_summary` (GPA calc) and `vw_course_stats`; demonstrates why multi-table views aren't updatable; recreates a single-table view `WITH CHECK OPTION`.
- **Task 3:** `fn_enroll_student` (blocks duplicate enrollment), `sp_transfer_student` (transactional department transfer + audit log), and a `SAVEPOINT` demo showing partial rollback.

## How to run
```bash
psql -U postgres -d college_db -f hands_on_3.sql
```
Written in PostgreSQL `plpgsql`. For MySQL, rewrite functions using `DELIMITER $$ ... END$$` stored procedures.

## Expected outcome
`fn_enroll_student` raises an error on duplicate enrollment; the SAVEPOINT test leaves only the first insert committed after the second fails.
