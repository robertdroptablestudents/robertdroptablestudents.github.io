---
title: Options
permalink: /docs/options
key: docs-options
---

## Container
Note: Running the SQLGrader container requires the `--privileged` flag due to the use of "docker-in-docker" to provision and manage the grading database environments.

The SQLGrader container image exposes several options:
- directory to `db.sqlite3` for the core SQLGrader data: `/code/sqlgrader/sqlite`
- directory to uploaded files (environment definitions, student submissions): `/code/sqlgrader/media`
- port for webUI: `80`
- port for grading API: `5000`

## Students
This section still needs to be written.