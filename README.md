# docker-images

This repository hosts all enginious customized Dockerfile for public images available on [engnious dockerhub](https://hub.docker.com/u/enginious).

## List of available docker images:

- ### [jenkins](https://hub.docker.com/r/enginious/jenkins)
    - #### Description:
      Jenkins docker image built starting from `jenkins/jenkins:lts-jdk17` with bundled OpenJDK-17, Maven-3.8.6 and Docker-20.10.9. Also has *lockable-resources*,
      *generic-webhook-trigger*, *authentication-tokens*, *docker-java-api*, *git-server*, *docker-plugin*, *config-file-provider*, *docker-commons*, *handlebars*,
      *pipeline-github*, *build-user-vars-plugin*, *popper-api*, *bootstrap4-api*, *nexus-artifact-uploader*, *docker-workflow*, *pipeline-utility-steps*, *emailext-template*,
      *pipeline-groovy-lib* as preinstalled plugins.
    - #### Usage:
      ````
      docker run -d --name jenkins \
          -p ${port1}:8080 -p ${port2}:50000 \
          -v ${volume}:/var/jenkins_home/ -v ${docker.sock}:/var/run/docker.sock \ 
          enginious/jenkins
      ````
  