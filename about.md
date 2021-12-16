---
layout: article
title: About
key: page-about
---

With SQLGrader scoring database query and schema assignments is streamlined through automated environments. Setup assignments for grading in the web interface and select from several common database engine options.

Underneath the web interface is the environment management and grading layer, running in the background and extensible in the source code.

## Try It

SQLGrader is available as a container image. Pull the image and run to give SQLGrader a spin:

```bash
docker pull ghcr.io/robertdroptablestudents/sqlgrader:latest
docker run -p 80:80 --name sqlgrader --privileged -d ghcr.io/robertdroptablestudents/sqlgrader:latest
```

For persistent use of SQLGrader it is recommended to leverage the [mounted volume option](/docs/options#container) to store the core database on your local device.

## Open Source Project

SQLGrader is available in open source for contributions, use, and customization.  The base SQLGrader container image is also available to be pulled for direct use.


## Origin

SQLGrader began as a project by [Drew Skwiers-Koballa](https://www.linkedin.com/in/drew-skwiers-koballa/) for the [Educational Technology course](http://omscs6460.gatech.edu/) at [Georgia Institute of Technology](https://omscs.gatech.edu/).  The original project is described in this [paper](assets/papers/DSK-Fall2021.pdf).