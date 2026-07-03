# Hands-On 6 — ORM Integration: SQLAlchemy (Advanced)

## Topics
SQLAlchemy Core & ORM, model relationships, sessions, CRUD via ORM, eager loading (`joinedload`) to fix N+1.

## Files
- `models.py` — Task 1 (ORM model definitions)
- `crud.py` — Tasks 2 & 3 (CRUD operations, N+1 fix)

## What it does
- **Task 1:** Defines `Department`, `Student`, `Course`, `Enrollment`, `Professor` classes mapped to the `college_db` schema, with `relationship()` links between them; `Base.metadata.create_all(engine)` builds the tables in `college_db_orm`.
- **Task 2:** Seeds departments/students/courses/enrollments via `session.add_all()`; queries CS students with a `join()` + `filter()`; reads enrollments with lazy loading (`echo=True` reveals N+1 in the SQL log); updates and deletes records.
- **Task 3:** Rewrites the read with `joinedload(Enrollment.student, Enrollment.course)`, collapsing the N+1 pattern into a single JOIN query.

## How to run
```bash
pip install sqlalchemy psycopg2-binary --break-system-packages
python models.py   # creates tables
python crud.py      # seeds data, shows N+1 vs eager-loaded query counts
```

## Expected outcome
With `echo=True`, the lazy-loading read shows 13 SQL statements; the `joinedload` version shows 1.
