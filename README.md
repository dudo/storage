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

Allow your other compose projects to use these databases by adding networks and/or volumes as needed:

```yaml
services:
  my_service:
    networks:
    - default
    - storage_default
    volumes:
    - storage_bundle:/usr/local/bundle

networks:
  storage_default:
    external: true

volumes:
  storage_node:
    external: true
  storage_bundle:
    external: true
```

## Reading

Learn about [Docker](https://docs.docker.com/compose/gettingstarted).

Learn about [Postgres](https://www.postgresql.org/docs/12/intro-whatis.html).

Learn about [Redis](https://redis.io/documentation).
