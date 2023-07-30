
# ksailnet

 <img src="ksailnet.svg" width="20%" alt="k3sup logo">

 ## k3s codespace nodes as tailscaled exit nodes

 - [tailscale](https://tailscale.io)
 - [k3sup](https://github.com/alexellis/k3sup)


##  the dev container
```
{
  "image": "mcr.microsoft.com/devcontainers/base:ubuntu",
  "runArgs": ["--device=/dev/net/tun"],
  "features": {
    "ghcr.io/tailscale/codespace/tailscale:1": {},
    "ghcr.io/devcontainers/features/sshd:1": {}
  }
}

```
## the Dockerfile

```
from debian:bullseye
RUN wget k3sup
RUN k3sup install --local --ip ${tailscale ip -4}
```