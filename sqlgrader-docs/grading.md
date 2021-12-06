---
title: Grading
permalink: /docs/grading
key: docs-grading
---


The grading process for an assignment loops through each assignment item, grading an item for all student submissions before moving onto the next item.  The grading process is grouped by assignment items/environments to better leverage image caching and reduce overhead.

## Query Grading

Query correctness grading is performed by running a student's query against a known correct query on 1 or more data sets.

It is expected that columns be in the same order although the column names may differ (eg SUM(salary) as total_salary or SUM(salary) as salary_total).  Row order is evaluated as the identical grading environments will result in identical row order, even in so-called "unordered" queries.

![SQLGrader Query Results comparison](/assets/diagrams/querycomparison.png)

## Schema Grading

Any assignment item that is a "schema" type will be graded by comparing the resulting tables, columns, and indexes between the provided schema and a student's schema.  All schema comparisons are done in a case-insensitive manner, however object names, data types, snd whether the column participates in an auto-increment or otherwise unique column must match.


```sql
select stuff from information_schema
```

Indexes are compared on type, first column, remaining column order, and included columns.




Support for grading views is incomplete.

## Customizing Grading
This section still needs to be written.

Grading occurs within the `api/` code and can be altered to score query and schema questions differently.