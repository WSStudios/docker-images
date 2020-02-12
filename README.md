
Wonderstorm Docker Images
=================

These are the various docker images that Wonderstorm uses.

Any changes to this repo are automatically built and pushed to docker hub.

Note, this is a public repo

Images
============

See [Docker's tags](https://hub.docker.com/r/wonderstorm/docker-images/tags) for all images

* [`wonderstorm/docker-images:ws-amazoncorretto-11`](https://hub.docker.com/r/wonderstorm/docker-images/tags) [[dockerfile]](https://github.com/WSStudios/docker-images/ws-amazoncorretto-11/Dockerfile)
    * Based on: https://github.com/carlossg/docker-maven
* [`wonderstorm/docker-images:ws-amazoncorretto-11-pwsh`](https://hub.docker.com/r/wonderstorm/docker-images/tags) [[dockerfile]](https://github.com/WSStudios/docker-images/ws-amazoncorretto-11-pwsh/Dockerfile)
    * Based on: https://github.com/carlossg/docker-maven with powershell added as the entry point

Adding another image to be built
============
* Go to https://hub.docker.com/repository/docker/wonderstorm/docker-images/builds/edit
* Add a new build rule matching your folder and tag that you want
* Click Save and Build!

Manually building and pushing
============
```
# NOTE: you'll need to run "docker login" and login to an account with push permissions to "wonderstorm/docker-images"

#cd to the image you wish to build
cd ws-amazoncorretto-11/
# edit the dockerfile if needed
vim Dockerfile
# this builds image locally and puts it in your local cache
docker build --tag wonderstorm/docker-images:ws-amazoncorretto-11 .
# this pushes the image to wonderstorm's public docker hub registry where we store it.
docker push wonderstorm/docker-images:ws-amazoncorretto-11
```
