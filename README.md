# MTG-Proxy Config

[MTG-Proxy](https://github.com/9seconds/mtg)

## Installation

`docker` and `git` required

Clone this repository

```bash
git clone https://github.com/SamWarden/mtg-proxy
cd mtg-proxy
```

Copy `config.toml.template` to `config.toml`

```bash
cp config.toml.template config.toml
```

## Generate secret

Generate a secret key for a domain and save it to config.toml

```bash
docker compose run --rm mtg-proxy generate-secret google.com
```

> This secret is a keystone for a proxy and your password for a client. You need to keep it secured.
> 
> We recommend choosing a hostname wisely. Here we have a google.com but in reality, all providers can easily detect that this is not a Google. Google has a list of networks it officially uses and your IP address won't probably belong to it. It is a great idea to hide behind some domain that has some relation to this IP address.
> 
> For example, you've bought a VPS from Digital Ocean. Then it might be a good idea to generate a secret for digitalocean.com then.

## Run a proxy

```bash
docker compose up -d
```
