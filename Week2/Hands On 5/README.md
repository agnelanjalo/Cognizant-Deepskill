# Hands-On 5 — MongoDB: Document Modelling, CRUD & Aggregation (Intermediate)

## Topics
Documents & collections, BSON types, CRUD operations, aggregation pipeline, indexes, embedding vs referencing.

## File
`hands_on_5_mongodb.js`

## What it does
- **Task 1:** Creates `college_nosql.feedback` collection, inserts 10 feedback documents (varying ratings/tags/semesters), one intentionally missing the `attachments` field.
- **Task 2:** CRUD — filters by rating, `$elemMatch`-style tag search, field projection, `updateMany` with `$set`/`$push`, `deleteMany` for old semester data.
- **Task 3:** Aggregation pipeline — average rating & feedback count per course (`$match`/`$group`/`$sort`), `$round`-formatted output, `$unwind`-based tag frequency leaderboard, index on `course_code` verified via `explain('executionStats')`.

## How to run
```bash
mongosh < hands_on_5_mongodb.js
```
Or paste the commands into MongoDB Compass's shell tab.

## Expected outcome
`db.feedback.countDocuments()` returns ≥10; tag-frequency pipeline shows `challenging` near the top; `explain()` reports `IXSCAN`, not `COLLSCAN`, after the index is created.
