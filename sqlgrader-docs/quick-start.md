---
title: Quick Start
permalink: /docs/quick-start
key: docs-quick-start
---

SQLGrader is available as a container image. Pull the image and run to give SQLGrader a spin:

```bash
docker pull ghcr.io/robertdroptablestudents/sqlgrader:latest
docker run -p 80:80 --name sqlgrader --privileged -d ghcr.io/robertdroptablestudents/sqlgrader:latest
```

For persistent use of SQLGrader it is recommended to leverage the [mounted volume option](/docs/options#container) to store the core database on your local device.