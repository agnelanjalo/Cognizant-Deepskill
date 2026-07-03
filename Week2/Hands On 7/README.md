# Hands-On 7: Migrations & Versioning

Setup once:
```
pip install alembic psycopg2-binary
alembic init migrations          # already scaffolded here
```

Set `sqlalchemy.url` in `alembic.ini` to your `college_db_orm` connection string.

## Task 1 — Baseline
```
alembic revision --autogenerate -m "initial schema"   # -> 0001_initial_schema.py
alembic upgrade head
alembic current
```

## Task 2 — Incremental changes
```
alembic revision --autogenerate -m "add is_active to students"   # -> 0002_add_is_active.py
alembic upgrade head
alembic revision --autogenerate -m "add course_schedule table"   # -> 0003_add_course_schedule.py
alembic upgrade head
alembic history --verbose
```

## Task 3 — Rollback & recovery
```
alembic current                  # note current head hash
alembic downgrade -1             # drops is_active
alembic downgrade base           # undo everything
alembic upgrade head             # reapply all, back to latest
```

Bonus (Django equivalent):
```
python manage.py makemigrations
python manage.py migrate
python manage.py migrate <app_name> <previous_migration_number>   # rollback
```
