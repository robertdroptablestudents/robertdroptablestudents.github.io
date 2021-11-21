---
title: Grading
permalink: /docs/grading
key: docs-grading
---

TeXt Theme is 100% compatible with GitHub Pages and it has been developed as a [gem-based themes](https://jekyllrb.com/docs/themes/) for easier use.


## Query Grading

## Schema Grading
All schema comparisons are done in a case-insensitive manner.

Any assignment item that is the "schema" type will be graded by comparing the columns and tables, storing the percentage correct in score_primary.  Column name, data type, and whether it is nullable are all compared for validation.

Indexes are compared on type, first column, remaining column order, and any included columns.