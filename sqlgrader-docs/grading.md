---
title: Grading
permalink: /docs/grading
key: docs-grading
---


## Query Grading
This section still needs to be written.


![SQLGrader Query Results comparison](/assets/diagrams/querycomparison.png)

## Schema Grading
All schema comparisons are done in a case-insensitive manner.

Any assignment item that is the "schema" type will be graded by comparing the columns and tables, storing the percentage correct in score_primary.  Column name, data type, and whether it is nullable are all compared for validation.

Indexes are compared on type, first column, remaining column order, and any included columns.


## Customizing Grading
This section still needs to be written.

Grading occurs within the `api/` code and can be altered to score query and schema questions differently.