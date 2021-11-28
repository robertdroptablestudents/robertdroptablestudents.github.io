---
title: Development
permalink: /docs/development
key: development
---

SQLGrader code is available for continued development and local build/customization.

## Get the Code

The entire project is stored in a single repository, including the Django web UI and the database interaction API. Git clone from 

## Build Locally

From the root of the project directory on your workstation, run the docker build command from the terminal:

```bash
docker build --build-arg BUILDID="mylocalbuild" -t sqlgrader .
```
(The build argument for BUILDID is optional)




To run the sqlgrader container image you built from code, run the docker run command from the terminal:

```bash
docker run -p 80:80 --privileged -d sqlgrader
```

For more on the available options to customize the SQLGrader container, see [options](options.md) or the [Dockerfile](https://github.com/robertdroptablestudents/sqlgrader/Dockerfile).