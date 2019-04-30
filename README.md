This repository contains the sources for the following docker hub images:

- [hhvm/hhvm](https://registry.hub.docker.com/u/hhvm/hhvm/)
- [hhvm/hhvm-proxygen](https://registry.hub.docker.com/u/hhvm/hhvm-proxygen/)

# Building A New Version

```
docker build --tag "gcr.io/qzlt-dev-hhvmpoc/hhvm:3.25.3" hhvm-latest
docker push gcr.io/qzlt-dev-hhvmpoc/hhvm:3.25.3
docker build --build-arg "HHVM_BASE_IMAGE=gcr.io/qzlt-dev-hhvmpoc/hhvm:3.25.3" --tag "gcr.io/qzlt-dev-hhvmpoc/hhvm-proxygen:3.25.3" hhvm-latest-proxygen
```
