---
title: Limitations
permalink: /docs/limitations
key: docs-limitations
---

SQLGrader attempts to cover many common scenarios and base cases for Postgres, MS SQL, and MySQL databases - but known limitations or areas for future development exist.

## Nuances
- Data generation does not function properly on schemas with "-" in the table or schema names.

## Future Opportunities
- Schema comparison does not include indexes, foreign keys, views, or stored procedures.
- MS SQL is not supported on ARM-based processors
