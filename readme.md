# Docker Development Databases

> A collection of Database dockerfiles intended for use in local development

## Configuration

Configuration is handled via environment variables.

You can create a `.env.development` file in the folder root...

```bash
#.env.development

MYSQL_USER='username'
MYSQL_PASSWORD='password'
MYSQL_ROOT_PASSWORD='password'
MYSQL_PORT=9002

POSTGRES_USER='postgres'
POSTGRES_PASSWORD='postgres'
POSTGRES_PORT=9003

```

and then load it using:

```shell
docker-compose up --env-file ./.env.development -d
```

alternatively you can specify them manually:

```shell
MYSQL_USER='username' MYSQL_PASSWORD='password' MYSQL_ROOT_PASSWORD='password' MYSQL_PORT='9002' POSTGRES_USER='postgres' POSTGRES_PASSWORD='postgres' POSTGRES_PORT='9003' docker-compose up -d
```

## Usage Instructions

### Deleting volumes

To delete volumes for a given docker-compose, go to the directory and run:

```shell
docker-compose --env-file ../.env.development down --volumes
```

### Running all databases

cd to `all` directory, and run `docker-compose up`

To use the env file, use:

```shell
docker-compose --env-file ../.env.development up -d
```

### MySQL

from inside the `mysql` directory, run `docker compose up`

To use the env file, use:

```shell
docker-compose --env-file ../.env.development up -d
```

MySQL will be listening on port `9002`

#### MySQL Credentials

| Credential    | Value      |
| ------------- | ---------- |
| Username      | `username` |
| Password      | `password` |
| Root Password | `password` |

### Postgres

from inside the `postgres` directory, run `docker compose up`.

To use the env file, use:

```shell
docker-compose --env-file ../.env.development up -d
```

Postgres will be listening on port `9003`

#### Postgres Credentials

| Credential | Value      |
| ---------- | ---------- |
| Username   | `postgres` |
| Password   | `postgres` |
