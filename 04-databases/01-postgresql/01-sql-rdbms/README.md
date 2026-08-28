# Module 16: SQL and RDBMS Fundamentals

Learn relational modeling, PostgreSQL schema definition, constraints, CRUD, aggregates, and normalization using the [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html), [data definition](https://www.postgresql.org/docs/current/ddl.html), and [data manipulation](https://www.postgresql.org/docs/current/dml.html).

## Practice Deliverable

Design and seed the TeamOps users, teams, projects, memberships, and tasks schema. Create migrations, seed data, and a simple relationship diagram. Use primary/foreign keys, `NOT NULL`, uniqueness, and check constraints where each rule belongs to the database.

## Verify

```bash
psql "$DATABASE_URL" -f migrations/<migration>.sql
psql "$DATABASE_URL" -f seed.sql
psql "$DATABASE_URL" -c "SELECT * FROM tasks LIMIT 5;"
```

## Completion Criteria

- [ ] Explain table, row, column, key, constraint, and relationship choices.
- [ ] Insert, select, update, and delete representative records safely.
- [ ] Model ownership and membership without duplicating data unnecessarily.
- [ ] Show that invalid foreign keys, duplicates, or invalid states are rejected.

## Common Mistakes

Missing constraints, storing multiple values in one column, nullable columns that hide required data, using application IDs without keys, and treating seed data as a migration.

## Next

Continue to [Module 17](../02-joins-advanced-queries/).
