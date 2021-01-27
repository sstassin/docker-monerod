
# docker-monerod

## Description

Run a Monero full node.

The blockchain is loaded from the `/bitmonero` volume. This volume should contain a config file like the included `bitmonero.conf`.

## How to run

```sh
# Clone repository
git clone https://github.com/sstassin/docker-monerod
cd docker-monerod
# Build image:
make build
# Create blockchain volume and copy configuration:
mkdir /opt/bitmonero && cp bitmonero.conf /opt/bitmonero
# Run container
docker run -p 18080:18080 -p 18081:18081 --restart=always -v bitmonero:/bitmonero --name=monerod -td sstassin/monerod
# View logs
docker logs -f monerod
```
