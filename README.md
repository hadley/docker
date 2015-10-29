# Docker containers

> This is my docker container. There are many like it, but this one is mine.
> 
> My container is my best friend. It is my life. I must master it as I must 
> master my life.

These docker containers are adaptations of the [rocker](https://github.com/rocker-org) containers, customised for my development workflow.

## To build

```sh
# If on mac:
docker-machine start default
eval "$(docker-machine env default)"

docker pull r-base # ensure we have latest base image
docker build -t hadley/rdevel .
```

## To use

```sh
cd /package/dir

docker run -ti --rm \
  -v $(pwd):/mnt \
  hadley/rdevel /bin/bash

cd /mnt
R
install_deps(dep = T)
```
