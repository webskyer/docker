This repository contains the sources for the following [docker](https://docker.io) base images:

- [`idoall/ubuntu16.04-nginx:1.18.0`](https://hub.docker.com/r/idoall/ubuntu16.04-nginx/1.18.0)



# Supported tags and respective `Dockerfile` links

- [`7.4.9`(*7.4.9/Dockerfile*)](https://github.com/idoall/docker/blob/master/ubuntu16.04-nginx1.18.0-php/7.4.9/Dockerfile)

  ​


## Developing

```bash
# Pull image
git clone https://github.com/idoall/docker.git
cd ubuntu16.04-nginx1.18.0-php/<version>

# hack hack hack

# build
docker build -t idoall/ubuntu16.04-nginx1.18.0-php:<version> .

# run
docker run -it \
--rm \
--name php \
--hostname php \
-p 2222:2222 \
-p 80:80 \
idoall/ubuntu16.04-nginx1.18.0-php:<version>

# Open http://localhost/ in your browser and you should see "php info!"


# access the contain
docker exec -it php /bin/bash


# ssh  user:work   password:123456
ssh work@<your ip> -p 2222

# view version
docker run -it --rm idoall/ubuntu16.04-nginx1.18.0-php:<version> php -v

```


## Directory structure inside image
/home/work/_app/nginx # Nginx root
/home/work/_logs/nginx # Nginx,PHP logs
/home/work/_app/nginx/html # meant to contain web content

# Custom Nginx Config files
Sometimes you need a custom config file for nginx to achieve this read the [Nginx config guide](https://hub.docker.com/r/idoall/ubuntu16.04-nginx/)

## meant to contain web content
```bash
docker run -d \
--name nginx-php \
--hostname nginx-php \
-v /mysite:/home/work/_app/nginx/html \
-p 80:80 \
idoall/ubuntu16.04-nginx1.18.0-php:<version>
```