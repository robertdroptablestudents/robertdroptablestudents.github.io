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



## Build Locally

### Option 1: VS Code Task
Pressing ⇧⌘B (shift+command/ctrl+B) in VS Code will open a preconfigured build task menu.  Select "Build SQLGrader Container" to start the SQLGrader container build from your local code.

### Option 2: Docker build command

From the root of the project directory on your workstation, run the docker build command from the terminal:

```bash
docker build --build-arg BUILDID="mylocalbuild" -t sqlgrader .
```
(The build argument for BUILDID is optional)


## Run Locally Built Container

To run the sqlgrader container image you built from code, run the docker run command from the terminal:

```bash
docker run -p 80:80 --privileged -d sqlgrader
```

For more on the available options to customize the SQLGrader container, see [options](options.md) or the [Dockerfile](https://github.com/robertdroptablestudents/sqlgrader/Dockerfile).