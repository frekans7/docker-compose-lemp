# LEMP Stack

![Docker Compose](https://img.shields.io/badge/Docker%20Compose-V2-2496ED?logo=docker&logoColor=white)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

![lemp-container](https://github.com/frekans7/docker-compose-lemp/blob/main/htdocs/img/LEMP.gif)

A simple LEMP stack using the *Official* Docker Repository for Alpine Linux, Nginx, MariaDB, PHP 8.4 and phpMyAdmin.

## Stack

| Service | Image |
|---|---|
| Web Server | `nginx:1.30.4-alpine` |
| PHP | `php:8.4.11-fpm-alpine` |
| Database | `mariadb:12.3.2` |
| DB Admin | `phpmyadmin:5.2.3` |

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/frekans7/docker-compose-lemp.git
cd docker-compose-lemp
```

### 2. Copy the environment file and set your passwords

```bash
cp .env.example .env
```

> [!WARNING]
> **Security Risk:** You MUST change the default `change-me` passwords for `MYSQL_ROOT_PASSWORD` and `MYSQL_PASSWORD` in the `.env` file before deploying to any publicly accessible environment.

### 3. Start LEMP

```bash
docker compose up -d
```

### 4. Stop LEMP

```bash
docker compose stop
```

### 5. Remove LEMP

```bash
docker compose down
```

### 6. Remove LEMP with volumes (deletes database data)

```bash
docker compose down -v
```

## Environment Variables

The following variables are available in the `.env` file for configuration:

| Variable | Description | Default Value |
|---|---|---|
| `NGINX_VERSION` | Docker image version for Nginx | `1.30.4-alpine` |
| `PHP_VERSION` | Docker image version for PHP-FPM | `8.4.11-fpm-alpine` |
| `MARIADB_VERSION` | Docker image version for MariaDB | `12.3.2` |
| `PMA_VERSION` | Docker image version for phpMyAdmin | `5.2.3` |
| `MYSQL_ROOT_PASSWORD` | The root password for MariaDB | `change-me` |
| `MYSQL_DATABASE` | The name of the default database created | `lemp` |
| `MYSQL_USER` | The name of the default database user | `lemp` |
| `MYSQL_PASSWORD` | The password for the default database user | `change-me` |
| `NGINX_PORT` | The host port mapped to the Nginx container | `8080` |
| `PMA_PORT` | The host port mapped to the phpMyAdmin container | `8183` |


## Access

| Service | URL |
|---|---|
| Web (PHP/HTML) | http://localhost:8080 |
| phpMyAdmin | http://localhost:8183 |

> Ports can be customized via the `.env` file (`NGINX_PORT`, `PMA_PORT`).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.