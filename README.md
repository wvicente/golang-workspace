[![Last Commit][last-commit]][commits]
# Simple workspace of [GoLang][1] <!-- omit in toc -->

- [Description](#description)
- [Default configuration](#default-configuration)
- [Useful commands](#useful-commands)
  - [Start the container in *"detached"* mode](#start-the-container-in-detached-mode)
  - [To attach to the container you can use the container's ID or name](#to-attach-to-the-container-you-can-use-the-containers-id-or-name)
  - [To see what is currently running](#to-see-what-is-currently-running)

## Description
This docker compose file create for you an container of golang image [*golang:1.16.2-alpine3.13*][2].


## Default configuration
* container's name _*my-golang-workspace*_
* 1GB of shared memory
* default workdir as */usr/src/myapp*
* the *source* folder being mapped as */usr/src/myapp*
* internal port 80 exposed in 8081
* internal port 443 exposed in 8444

## Useful commands

### Start the container in *"detached"* mode

```
$ docker-compose up -d
```

### To attach to the container you can use the container's ID or name

```
$ docker container exec -it -u root my-golang-workspace /bin/sh
```

### To see what is currently running

```
$ docker-compose ps
```

---

> For more informations about compose file check the [reference guide][reference-guide]

[1]: https://golang.org
[2]: https://github.com/docker-library/golang/blob/fc960e720b9ba539812525220a272aa3961d359c/1.16/alpine3.13/Dockerfile

[reference-guide]: https://docs.docker.com/compose/compose-file/compose-file-v3/
[commits]: https://github.com/wvicente/golang-workspace/commits/master
[last-commit]: https://img.shields.io/github/last-commit/wvicente/golang-workspace/master?style=plastic&logo=github