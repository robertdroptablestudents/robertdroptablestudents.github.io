---
title: Code Dependencies
permalink: /docs/dependencies
key: dependencies
---

Dependencies are managed through the Dockerfiles and pip requirements.txt files in both web UI and API layers. All are automatically installed during container build.

## API Dependencies
The API layer manages container and database interactions.

The [container environment](https://github.com/robertdroptablestudents/sqlgrader/blob/main/Dockerfile) includes:
- Python 3.10
- unixodbc-dev
- (AMD64 only) unixodbc, msodbcsql17
- libpq-dev, postgresq-client
- [Docker-in-Docker](https://github.com/microsoft/vscode-dev-containers/blob/main/script-library/docs/docker-in-docker.md)

Python modules [installed by pip](https://github.com/robertdroptablestudents/sqlgrader/blob/main/api/requirements.txt):
- psycopg
- mysql-connector-python
- (not invoked by ARM64) pyodbc
- flask
- docker SDK
- faker

## Web UI Dependencies
The web UI layer manages ORM and graphical interface interactions.

The [container environment](https://github.com/robertdroptablestudents/sqlgrader/blob/main/webui.Dockerfile) includes:
- Python 3.10

Python modules [installed by pip](https://github.com/robertdroptablestudents/sqlgrader/blob/main/webui/requirements.txt):
- Django
- httpx
- djangorestframework
- docker SDK