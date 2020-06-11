# Storage

Data layer for local development.

## Setup

This tooling makes heavy use of docker compose. Setting up docker is beyond the scope of this readme.

```shell
mkdir ~/projects/cardbinder/
cd ~/projects/cardbinder/

git clone git@github.com:cardbinder/storage.git

docker-compose up -d
```

Allow your other compose projects to use these databases by adding the following:

```yaml
services:
  my_service:
    networks:
    - default
    - storage_default

networks:
  storage_default:
    external: true
```

## Reading

Learn about [postgres](https://www.postgresql.org/docs/12/intro-whatis.html).
Learn about [redis](https://redis.io/documentation).
