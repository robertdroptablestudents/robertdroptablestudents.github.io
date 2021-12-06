---
title: Course Setup
permalink: /docs/course-setup
key: docs-course-setup
---

The basic setup for SQLGrader use is entering students and assignments.  Student management is covered in this article while assignments are covered in depth in [assignments](assignments).

## Students
Students are entered with first name, last name, and a custom ID.  The custom ID could be their email address, student ID, or another globally unique piece of information - it is designated to be useful in correlating a student record from SQLGrader to another system or spreadsheet.

### Groups: Organizing Students
Students are divided into **groups** in SQLGrader.  Each student is assigned to a group, which may correspond to their course section or the entire course.

### Importing Students
Students can be created one at a time on the students tab of SQLGrader, but for efficiency an entire group of students can be imported from a csv with the columns firstname, lastname,  custom ID.  The csv should NOT have a header row.

An [example csv](/assets/samples/sample.csv) would look like:
```
Louie,ThePug,16
Gabby,AnotherPug,8
```
Where Louie ThePug has the custom ID 16 and Gabby AnotherPug has the custom ID 8.

## Assignments
An assignment can contain multiple items/questions of both query and schema type.  A database type (postgres, mssql, or mysql) is selected for the entire assignment and the database environment is further customized at multiple tiers of the assignment. Assignment customization is achieved in the web UI by uploading SQL files to the assignment setup.

Assignments are covered in depth in [assignments](assignments).