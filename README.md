[![Last Commit][last-commit]][commits]

# [GoLang][1] workspace with Nginx as reverse proxy (without SSL) <!-- omit in toc -->

- [Description](#description)
- [Default configuration](#default-configuration)
- [Useful commands](#useful-commands)
  - [Start the container in *"detached"* mode](#start-the-container-in-detached-mode)
  - [To attach to the container you can use the container's ID or name](#to-attach-to-the-container-you-can-use-the-containers-id-or-name)
  - [To see what is currently running](#to-see-what-is-currently-running)

## Description
This docker compose file create for you an container with golang image [*golang:1.16.2-alpine3.13*][2] and another with nginx image [*nginx:stable-alpine*][3].

By default the nginx configuration have a reverse proxy pointing to golang container internaly, exposing only the nginx port as 8080. You can access using the url _http://localhost:8080_.

## Default configuration
* **Nginx container:**
  * container's name _*nginx*_
  * internal port 80 exposed in 8080
  * default configuration file mapped from *./nginx/default.conf* **to** */etc/nginx/conf.d/default.conf*
  * reverse proxy to _*http://golang-server:80*_ internally
* **GoLang container:**
  * container's name _*golang-server*_
  * 1GB of shared memory
  * default workdir as */usr/src/myapp*
  * the *source* folder being mapped as */usr/src/myapp*

## Useful commands

### Start the container in *"detached"* mode

```
$ docker-compose up -d
```

### To attach to the container you can use the container's ID or name

```
$ docker container attach golang-server
```
or
```
$ docker container attach nginx
```

### To see what is currently running

```
$ docker-compose ps
```

---

> For more informations about compose file check the [reference guide][reference-guide]

[1]: https://golang.org
[2]: https://github.com/docker-library/golang/blob/fc960e720b9ba539812525220a272aa3961d359c/1.16/alpine3.13/Dockerfile
[3]: https://github.com/nginxinc/docker-nginx/blob/3fb70ddd7094c1fdd50cc83d432643dc10ab6243/stable/alpine/Dockerfile

[reference-guide]: https://docs.docker.com/compose/compose-file/compose-file-v3/
[commits]: https://github.com/wvicente/golang-workspace/commits/nginx-proxy-without-ssl
[last-commit]: https://img.shields.io/github/last-commit/wvicente/golang-workspace/nginx-proxy-without-ssl?style=plastic&logo=github