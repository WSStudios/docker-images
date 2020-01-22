
Wonderstorm Docker Images
=================

These are the various docker images that Wonderstorm uses.

Note, this is a public repo

Images
============

See [Docker Hub](https://hub.docker.com/_/wonderstorm) for all images

* [`wonderstorm/docker-images:ws-amazoncorretto-11`](https://hub.docker.com/r/wonderstorm/docker-images) [[dockerfile]](https://github.com/WSStudios/docker-images/ws-amazoncorretto-11/Dockerfile)
    * Based on: https://github.com/carlossg/docker-maven

Adding another image to be built
============
Instructions pending

Manually building and pushing
============
```
# NOTE: you'll need to run "docker login" and login to an account with push permissions to "wonderstorm/docker-images"

#cd to the image you wish to build
cd ws-amazoncorretto-11/
# edit the dockerfile if needed
vim Dockerfile
# this builds image locally and puts it in your local cache
docker build --tag wonderstorm/docker-images:3.6-amazoncorretto-11 .
# this pushes the image to wonderstorm's public docker hub registry where we store it.
docker push wonderstorm/docker-images:3.6-amazoncorretto-11
```
