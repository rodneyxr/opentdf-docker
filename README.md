# Quickstart

Clone the repository and its submodules with the following command:

```bash
git clone --recurse-submodules https://github.com/rodneyxr/opentdf-docker.git
cd opentdf-docker
```

Just run the following command to start the OpenTDF server:

```bash
docker-compose up -d
```

Here is a table of the services that are started:

| Service | URL |
| --- | --- |
| OpenTDF | [http://localhost:8080](http://localhost:8080) |
| Keycloak | [http://localhost:8888/auth](http://localhost:8888/auth) |

The default username and password for Keycloak is `admin` and `changeme`.