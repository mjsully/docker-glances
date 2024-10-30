![Github All Releases](https://img.shields.io/github/downloads/mjsully/docker-glances/total)

# Glances in a Docker container
This container packages the popular system monitoring tool [Glances](https://glances.readthedocs.io/en/latest/index.html) into an Alpine container. This allows easy deployment of a system monitoring tool with a nice web UI, stats logging and Home Assistant integration with a simple docker compose deployment.
## Why not use the official container?
The main reason is that Home Assistant currently only supports v3 of the Glances API, but the official Glances containers are on v4. Therefore, to integrate devices into Home Assistant, a custom image was needed based on an older version of the API. 
## Versions
There are 3 image tags provided: `minimal`, `standard` and `gpu`. The baseline libraries included are `containers,graph,web,ip`, see the [docs](https://glances.readthedocs.io/en/develop/aoa/index.html) for more information. The differences in the images are described below:
| Tag    | `minimal` | `standard` | `gpu` |
| -------- | ------- | ------- | ------- |
| Baseline  | ✅ | ✅ | ✅ |
| Prometheus client |  | ✅ | ✅ |
| GPU |  |  | ✅ |
## Deployment
An example `docker-compose.yml` is provided below:
```
services:
  glances:
    image: ghcr.io/mjsully/docker-glances:minimal
    ports:
      - 61208:61208
    container_name: glances
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock:ro
    restart: unless-stopped
    pid: host
```
