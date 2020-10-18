golang 1.13.8-alpine3.11.3-source
=============

## Developing

```bash
# Pull image
git clone https://github.com/idoall/docker.git
cd golang/1.13.8/alpine3.11.3-source

# hack hack hack

# Build
docker build -t idoall/golang:1.13.8-alpine3.11.3-source .


# view golang version
docker run -it \
--rm \
--name golang \
--hostname golang \
idoall/golang:1.13.8-alpine3.11.3-source \
go version


# run
docker run -it \
--rm \
--name golang \
--hostname golang \
idoall/golang:1.13.8-alpine3.11.3-source


# access the contain
docker exec -it golang /bin/bash
```
