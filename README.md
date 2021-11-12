# Symfony docker

A docker compose to manage a Symfony and other PHP applications.


## Installation

Just clone this repository, and if you want you can change the container names in the docker-compose.yml file and that's it.


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
docker-compose exec container-name /bin/bash
```


## Contributing

For contributions, issues and feature requests please check [issues page](https://github.com/dsabre/countdown/issues).


## Authors

- [Daniele Sabre](https://github.com/dsabre)


## Support me
<a href="https://www.buymeacoffee.com/daniele.sabre" target="_blank">
  <img src="https://raw.githubusercontent.com/dsabre/dsabre/main/images/bmc.png" alt="Buy Me a Coffee" title="Buy Me a Coffee" height="50" />
</a>


## License

[MIT](https://choosealicense.com/licenses/mit/)
