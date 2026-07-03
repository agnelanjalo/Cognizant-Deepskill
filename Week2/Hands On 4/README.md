# Hands-On 4 — Query Optimisation: Indexes, EXPLAIN & N+1 (Intermediate)

## Topics
Index types (B-Tree, composite, partial), `EXPLAIN`/`EXPLAIN ANALYZE`, query plans, the N+1 query problem, connection pooling (concept).

## Files
- `hands_on_4.sql` — Tasks 1 & 2 (baseline EXPLAIN, index creation, re-run EXPLAIN)
- `hands_on_4_n1_problem.py` — Task 3 (N+1 demo in Python)

## What it does
- **Task 1:** Runs `EXPLAIN` on a 3-table JOIN before any indexing, notes the Seq Scan / estimated cost.
- **Task 2:** Adds a B-Tree index on `enrollment_year`, a composite UNIQUE index on `(student_id, course_id)`, an index on `course_code`, and a partial index for ungraded enrollments; re-runs `EXPLAIN` to confirm Index Scan.
- **Task 3 (Python):** `n_plus_one_version()` issues 1 + N queries fetching students in a loop; `fixed_join_version()` does it in a single JOIN query — both timed and query-counted.

## How to run
```bash
psql -U postgres -d college_db -f hands_on_4.sql
pip install psycopg2-binary --break-system-packages
python hands_on_4_n1_problem.py
```

## Expected outcome
Post-indexing `EXPLAIN` shows an Index Scan instead of Seq Scan. Python script prints `13 queries executed` (N+1 version) vs `1 query executed` (JOIN version).
