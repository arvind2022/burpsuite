# BURP_SUITE

![logo](https://assets.gitlab-static.net/uploads/-/system/project/avatar/16865306/thumbnail.png)

## INDEX

- [BURP_SUITE](#burpsuite)
  - [INDEX](#index)
  - [BADGES](#badges)
  - [INTRODUCTION](#introduction)
  - [PREREQUISITES](#prerequisites)
  - [INSTALL](#install)
    - [DOCKER RUN](#docker-run)
    - [DOCKER COMPOSE](#docker-compose)
  - [LICENSE](#license)

## BADGES

[![pipeline status](https://gitlab.com/oda-alexandre/burpsuite/badges/master/pipeline.svg)](https://gitlab.com/oda-alexandre/burpsuite/commits/master)

## INTRODUCTION

Docker image of :

- [burpsuite](https://portswigger.net)

Continuous integration on :

- [gitlab pipelines](https://gitlab.com/oda-alexandre/burpsuite/pipelines)

Automatically updated on :

- [docker hub public](https://hub.docker.com/r/alexandreoda/burpsuite)

## PREREQUISITES

Use [docker](https://www.docker.com)

## INSTALL

### DOCKER RUN

```docker run -d --name burpsuite -v ${HOME}:/home/burpsuite -v /tmp/.X11-unix/:/tmp/.X11-unix/ -e DISPLAY --p 8080:8080 alexandreoda/burpsuite
```

### DOCKER COMPOSE

```yml
version: "3.7"

services:
  burpsuite:
    container_name: burpsuite
    image: alexandreoda/burpsuite
    restart: "no"
    privileged: false
    environment:
      - DISPLAY
    volumes:
      - "${HOME}:/home/burpsuite"
      - "/tmp/.X11-unix/:/tmp/.X11-unix/"
    ports:
      - "8080:8080"
```

## LICENSE

[![GPLv3+](http://gplv3.fsf.org/gplv3-127x51.png)](https://gitlab.com/oda-alexandre/burpsuite/blob/master/LICENSE)
