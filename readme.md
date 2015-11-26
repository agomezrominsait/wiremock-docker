# Wiremock Docker

> [Wiremock](http://wiremock.org) standalone HTTP server Docker image

## Supported tags and respective Dockerfile links :

- `2.0.6-beta`, `latest` [(2.0/Dockerfile)](https://github.com/rodolpheche/wiremock-docker/blob/2.0.6-beta/Dockerfile)

## How to use this image

The image include 

- `EXPOSE 8080 443` : the wiremock http/https server port.

- `VOLUME /home/wiremock` : the wiremock data storage.

Launch a Wiremock container

```sh
$ docker run -d -v $PWD/stub:/home/wiremock -p 8080:8080 rodolpheche/wiremock
```

> Simply access [http://localhost:8080/__admin](http://localhost:8080/__admin) to check your mappings

Launch a Wiremock container with Wiremock arguments

```sh
$ docker run -d -v $PWD:/home/wiremock -p 8080:8080 -e WIREMOCK_ARGS="--verbose" rodolpheche/wiremock
```

> `mappings` and `files__` folders created if not exist

Stop the container with Wiremock HTTP API

```sh
$ curl -XPOST http://localhost:8080/__admin/shutdown
```