# docker-mod_rewrite
Docker file for building Centos 7 with Mod_rewrite enable.

## How to use the image
* To run the container:
        docker run -d -p 8181:80 --name mod-rewrite-container -v "$PWD/src/":/var/www/html/ apache_mod_rewrite
* To inspect the container:
        docker exec -it mod-rewrite-container bash

## To build the image and pushig to dockerHub
        docker build -t <YourDockerHubUsername>/mod_rewrite:version1.0 .
        docker push <YourDockerHubUsername>/mod_rewrite
