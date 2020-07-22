# Docker for Radama PMS - Front part
This repository contains a dockerized environment for Radama PMS - Front part
PHP, MySQL, Nginx, Adminer, Mailcatcher

## Requirements

This project uses [docker](https://www.docker.com/what-docker) and
[docker-compose](https://docs.docker.com/compose/overview/) to simplify
dependencies and deployment.

Note: Tested onlu on Linux Ubuntu 20.04

### Tested versions

- [docker](https://docs.docker.com/install) (Tested: v19.03.8)
- [docker-compose](https://docs.docker.com/compose/install) (Tested: v1.25.0)

## Configuration

### Env variables

In order to copy the default environment variables and set your local configuration, copy the .env.example file

```bash
cp .env.example .env
```

Once done, you can edit all the environment variables in the newly generated `.env`.

SOURCE_DIRECTORY means the directory where are located PMS backend source (laravel)

### Hostname

Make sure to add the hostnames configured in `.env` file to you `/etc/hosts` file:

```bash
127.0.0.1 xxx.yourdomain.devl # check value in .env
```

### Nginx

nginx service can be configured in `nginx/app.conf` file

### PHP

PHP service can be configured in `php/local.ini` file

### MySQL

MySQL service can be configured in `mysql/my.cnf` file

MySQL project data are stored in a docker volume located `/var/lib/docker/volumes/api-radama-db-data/`.

## Launch your envinronment

Simply run the docker-compose command below:

```bash
docker-compose up -d
```

Make sure that ports 80 (and 443?) is free on your local machine
Now go to the APP_DOMAIN_NAME URL.
