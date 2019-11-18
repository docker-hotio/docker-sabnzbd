# sabnzbd

[![GitHub](https://img.shields.io/badge/source-github-lightgrey)](https://github.com/hotio/docker-sabnzbd)
[![Docker Pulls](https://img.shields.io/docker/pulls/hotio/sabnzbd)](https://hub.docker.com/r/hotio/sabnzbd)
[![Discord](https://img.shields.io/discord/610068305893523457?color=738ad6&label=discord&logo=discord&logoColor=white)](https://discord.gg/CdaP4VT)

## Starting the container

Just the basics to get the container running:

```shell
docker run --rm --name sabnzbd -p 8080:8080 -v /tmp/sabnzbd:/config -e TZ=Etc/UTC hotio/sabnzbd
```

The environment variables below are all optional, the values you see are the defaults.

```shell
-e PUID=1000
-e PGID=1000
-e UMASK=022
```

## Tags

| Tag      | Description                    | Build Status                                                                                                                                              | Last Updated                                                                                            |
| ---------|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| latest   | The same as `stable`           |                                                                                                                                                           |                                                                                                         |
| stable   | Stable version                 | [![Build Status](https://cloud.drone.io/api/badges/hotio/docker-sabnzbd/status.svg?ref=refs/heads/stable)](https://cloud.drone.io/hotio/docker-sabnzbd)   | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/hotio/docker-sabnzbd/stable)   |
| unstable | Unstable version, pre-releases | [![Build Status](https://cloud.drone.io/api/badges/hotio/docker-sabnzbd/status.svg?ref=refs/heads/unstable)](https://cloud.drone.io/hotio/docker-sabnzbd) | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/hotio/docker-sabnzbd/unstable) |

You can also find tags that reference a commit or version number.

## Executing your own scripts

If you have a need to do additional stuff when the container starts or stops, you can mount your script with `-v /docker/host/my-script.sh:/etc/cont-init.d/99-my-script` to execute your script on container start or `-v /docker/host/my-script.sh:/etc/cont-finish.d/99-my-script` to execute it when the container stops. An example script can be seen below.

```shell
#!/usr/bin/with-contenv bash

echo "Hello, this is me, your script."
```
