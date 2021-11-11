# Symfony docker

A docker compose to manage a Symfony and other PHP applications.


## Useful commands

Generate containers using docker compose:

```bash
docker-compose up -d --build
```

Remove all container created by your docker compose:

```bash
docker-compose down --rmi all
```

To enter in a named container use:

```bash
docker-compose exec php /bin/bash
```
