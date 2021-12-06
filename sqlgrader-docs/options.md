---
title: Options
permalink: /docs/options
key: docs-options
---

## Container Options
Note: Running the SQLGrader container requires the `--privileged` flag due to the use of "docker-in-docker" to provision and manage the grading database environments.

```bash
docker pull ghcr.io/robertdroptablestudents/sqlgrader:latest
docker run -p 80:80 --name sqlgrader --privileged -d ghcr.io/robertdroptablestudents/sqlgrader:latest
```

The SQLGrader container image exposes several options:

### Ports
- **required** port for webUI: `80`
- port for grading API: `5000`


### Mounted Volumes
- **recommended** directory to `db.sqlite3` for the core SQLGrader data: `/code/sqlgrader/sqlite`
- directory to uploaded files (environment definitions, student submissions): `/code/sqlgrader/media`

### Environment Variables
- DJANGO_SUPERUSER_PASSWORD: **recommended** custom admin password for /admin web UI, default `abc123`
- THISURL: URL for access as env variable, default `localhost`

### Platform
The SQLGrader container image is available for AMD64 and ARM64 architectures.  Override the auto-detected architecute with `--platform=linux/amd64` or `--platform=linux/arm64`.

## Build Options

Should you opt to "build your own" container image, the following build arguments are pre-existing:
- BUILDID: string to display in SQLGrader footer, denoting the version of the build
- the platform is auto-detected during your build, but can be overridden with --platform=linux/arm64 or --platform=linux/amd64

Example local build and run:

```bash
docker build --platform=linux/amd64 --build-arg BUILDID="localbuild" -t sqlgrader .
docker run -p 80:80 --privileged --name sqlgrader -e DJANGO_SUPERUSER_PASSWORD=abcde12345 -d sqlgrader
```