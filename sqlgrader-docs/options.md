---
title: Options
permalink: /docs/options
key: docs-options
---

## Container
Note: Running the SQLGrader container requires the `--privileged` flag due to the use of "docker-in-docker" to provision and manage the grading database environments.

The SQLGrader container image exposes several options:
- **required** port for webUI: `80`
- **recommended** directory to `db.sqlite3` for the core SQLGrader data: `/code/sqlgrader/sqlite`
- directory to uploaded files (environment definitions, student submissions): `/code/sqlgrader/media`
- port for grading API: `5000`
- URL for host access as env variable: `localhost`

## Students
This section still needs to be written.