---
title: Data Generation
permalink: /docs/datagen
key: docs-datagen
---

Datasets can be automatically generated for schemas for use in testing queries for grading.  The datasets are built with random data and foreign keys are respected.

## Data Generation Use
Data generation does not function properly on schemas with "-" in the table or schema names.


## Data Generation Implementation

Data generation is implemented through the Python [faker](https://github.com/joke2k/faker) library, which generates SQL `INSERT` statements to load generated data into a table.  Foreign keys and uniqueness constraints are detected to specify data generation ordering and ensure the generated data adheres to the schema requirements.

For efficiency during grading, a single container is created and the data inserted before a snapshot is taken to preserve the completed environment state.  The snapshot is used as a container image for all student submissions to be graded, eliminating the need to run the large insert statements on additional database instances.


### Data Types Observed
The following data types are observed for data generation:
- string, nvarchar, varchar, nchar, char, text
- uniqueidentifier
- int, tinyint, smallint, bigint
- float
- decimal, numeric
- money, currency
- binary
- bit
- date, time, datetime, datetime2, datetimeoffset

Data types not listed may generate a blank column.