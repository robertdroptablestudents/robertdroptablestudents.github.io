---
title: Development
permalink: /docs/development
key: development
---

SQLGrader code is available for continued development and local build/customization.

## Development Getting Started


### Environment Prerequisites

- VS Code
- Docker (or comparable container runtime)

### Get the Code

The entire project is stored in a single repository, including the Django web UI and the database interaction API. Git clone from [https://github.com/robertdroptablestudents/sqlgrader](https://github.com/robertdroptablestudents/sqlgrader) and use the provided [devcontainer](https://code.visualstudio.com/docs/remote/containers) definition for a pre-configured development environment.


**VS Code tasks are setup, hit F5 to start the web UI server.**


## Build Locally

### Option 1: VS Code Task
Pressing ⇧⌘B (shift+command/ctrl+B) in VS Code will open a preconfigured build task menu.  Select "Build SQLGrader Container" to start the SQLGrader container build from your local code.

### Option 2: Docker build command

From the root of the project directory on your workstation, run the docker build command from the terminal:

```bash
docker build -t sqlgrader .
```

An optional build arguement for BUILDID allows a custom build number to be injected into the environment during build.  Add `--build-arg BUILDID="specialbuildnumber"` to the docker build command to use:

```bash
docker build --build-arg BUILDID="specialbuildnumber" -t sqlgrader .
```

## Run Locally Built Container

To run the sqlgrader container image you built from code, run the docker run command from the terminal:

```bash
docker run -p 80:80 --privileged -d sqlgrader
```

For more on the available options to customize the SQLGrader container, see [options](options.md) or the [Dockerfile](https://github.com/robertdroptablestudents/sqlgrader/Dockerfile).


## Reset Local Dev Environment

1. Clear all app migrations
```
cd webui/instructor/migrations
rm -r *
```

2. Delete database - remove db.sqlite3 from webui/sqlite folder

3. Run initial migration and re-add super user
```
cd webui
python manage.py migrate
DJANGO_SUPERUSER_USERNAME=admin DJANGO_SUPERUSER_PASSWORD=abc123 DJANGO_SUPERUSER_EMAIL=robert@droptablestudents.com python manage.py createsuperuser --noinput
python manage.py drf_create_token admin
```

4. Run app migrations
```
python manage.py makemigrations instructor
python manage.py migrate
```
