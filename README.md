# SponsorBlock Mirror
Docker containers to mirror the [SponsorBlock](https://sponsor.ajay.app) database + API

This work is dual-licenced under GPL-3.0-only AND MIT

---
## SponsorBlock Database Licence
SponsorBlock data and databases are under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) from https://sponsor.ajay.app.

---

[![sb-mirror](https://img.shields.io/docker/image-size/mchangrh/sb-mirror/alpine?label=sb-mirror)](https://hub.docker.com/r/mchangrh/sb-mirror)
[![sb-server-runner](https://img.shields.io/docker/image-size/mchangrh/sb-server-runner/latest?label=sb-server-runner)](https://hub.docker.com/r/mchangrh/sb-server-runner)
[![rsync](https://img.shields.io/docker/image-size/mchangrh/rsync/alpine?label=rsync)](https://hub.docker.com/r/mchangrh/rsync)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)


## Usage
This copies the latest SponsorBlock database to the `./sb-mirror` local directory

```sh
docker run --rm -it -v "${PWD}/sb-mirror:/mirror" mchangrh/sb-mirror:alpine
```
docker-compose
```yml
sb-mirror:
  image: mchangrh/sb-mirror
  container_name: sb-mirror
  volumes:
    - ./sb-mirror:/mirror
  ports:
  #  - 873:873
  restart: unless stopped
  environment:
  #  - MIRROR=TRUE
```
---
## Mirroring

If you would like to set up an active mirror, allow `873/tcp` through your firewalls for rsyncd and uncomment lines in docker-compose

If you would like to set up a full API mirror, see [containers](./docs/containers.md)

---

Contributions & Pull request are always welcome & appreciated

non-exhaustive list of packages & respective licences [here](./oss-attribution/attribution.md)

There is an active rsync mirror that only downloads once every 24 hours and can be found [here](http://sb-archive.mchang.xyz/)

---

Special thanks to [Ajay](https://ajay.app/), [SponsorBlock](https://github.com/ajayyy/SponsorBlock/graphs/contributors), [SponsorBlockServer](https://github.com/ajayyy/SponsorBlockServer/graphs/contributors) and [SponsorBlockSite](https://github.com/ajayyy/SponsorBlockSite/graphs/contributors) contributors, SponsorBlock VIPs and the community for their contributions.

Don't be shy! Join us on [Discord](https://discord.gg/SponsorBlock) or [Matrix](https://matrix.to/#/#sponsor:ajay.app?via=ajay.app&via=matrix.org&via=mozilla.org)