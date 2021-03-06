# server-images

Repo containing some server images used in our projects.

## k8s-baseimage

Base AMI used for all Kubernetes cluster nodes. This image is built automatically in the [`server-images` pipeline on Concourse](https://ci.skyscrape.rs/teams/skyscrapers/pipelines/server-images), but if you need to build it manually, run `make build` to build it, providing the correct Kubernetes version, e.g.:

```bash
KUBERNETES_VERSION=1.8 make build
```

## teleport

AMI for Teleport servers. It basically contains the Teleport binaries and `certbot`. This image is built automatically in the [`server-images` pipeline on Concourse](https://ci.skyscrape.rs/teams/skyscrapers/pipelines/server-images), but if you need to build it manually, run `packer build` providing the correct variables, e.g.:

```bash
packer build -var 'source_ami=ami-cc166eb5' -var 'teleport_version=2.4.2' packer.json
```
