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

## Test encrypt/decrypt

Install the `otdfctl` cli tool.

```bash
go install github.com/opentdf/otdfctl@latest
```

Encrypt the some content.

```bash
echo 'demo text' | otdfctl --host=http://localhost:8080 --with-client-creds '{"clientId": "opentdf", "clientSecret": "secret"}' encrypt -t tdf3 -o demo.txt.tdf
```

Decrypt the file.

```bash
otdfctl --host=http://localhost:8080 --with-client-creds '{"clientId": "opentdf", "clientSecret": "secret"}' decrypt demo.txt.tdf
```

The decrypted file will print to stdout.
