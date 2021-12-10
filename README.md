# vault-docker

Run a Vault instance for experimentation within Docker.

# Install

```
git clone https://github.com/mscribellito/vault-docker.git

cd vault-docker

mkdir -p volumes/{file,logs}
```

# Config

You can set the log level in `docker-compose.yml` or `volumes/config/vault-server.hcl`.

# Start

```
docker-compose up
```

* UI: http://localhost:8200/ui
* API: http://localhost:8200/

# Install CLI

```
brew install vault

export VAULT_ADDR='http://127.0.0.1:8200'
```

# Initialize

Note: Don't do this in production!

```
vault operator init -key-shares=1 -key-threshold=1

vault operator unseal <unseal-key>

vault login <root-token>
```