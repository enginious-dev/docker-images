# Jenkins image with bundled
#  > OpenJDK-17,
#  > Maven-3.8.6
#  > Docker-20.10.9
#
# Preinstalled plugins:
#  > lockable-resources
#  > generic-webhook-trigger
#  > authentication-tokens
#  > docker-java-api
#  > git-server
#  > docker-plugin
#  > config-file-provider
#  > docker-commons
#  > handlebars
#  > pipeline-github
#  > build-user-vars-plugin
#  > popper-api
#  > bootstrap4-api
#  > nexus-artifact-uploader
#  > docker-workflow
#  > pipeline-utility-steps
#  > emailext-template
#  > pipeline-groovy-lib

FROM jenkins/jenkins:lts-jdk17

USER root

ENV DOCKERVERSION=20.10.9
ENV DOCKER_HOME=/opt/docker/bin
RUN mkdir -p ${DOCKER_HOME}
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKERVERSION}.tgz && tar xzvf docker-${DOCKERVERSION}.tgz --strip 1 -C ${DOCKER_HOME} && rm docker-${DOCKERVERSION}.tgz
ENV PATH=$DOCKER_HOME:$PATH
ENV DOCKER_HOST=tcp://localhost:2375

ENV MAVENVERSION=3.8.6
ENV MAVEN_HOME=/opt/maven/bin
RUN mkdir -p ${MAVEN_HOME}
RUN curl -fsSLO https://dlcdn.apache.org/maven/maven-3/${MAVENVERSION}/binaries/apache-maven-${MAVENVERSION}-bin.tar.gz && tar xzvf apache-maven-${MAVENVERSION}-bin.tar.gz --strip 1 -C ${MAVEN_HOME} && rm apache-maven-${MAVENVERSION}-bin.tar.gz
ENV PATH=$MAVEN_HOME:$PATH

RUN jenkins-plugin-cli --plugins lockable-resources
RUN jenkins-plugin-cli --plugins generic-webhook-trigger
RUN jenkins-plugin-cli --plugins authentication-tokens
RUN jenkins-plugin-cli --plugins docker-java-api
RUN jenkins-plugin-cli --plugins git-server
RUN jenkins-plugin-cli --plugins docker-plugin
RUN jenkins-plugin-cli --plugins config-file-provider
RUN jenkins-plugin-cli --plugins docker-commons
RUN jenkins-plugin-cli --plugins handlebars
RUN jenkins-plugin-cli --plugins pipeline-github
RUN jenkins-plugin-cli --plugins build-user-vars-plugin
RUN jenkins-plugin-cli --plugins popper-api
RUN jenkins-plugin-cli --plugins bootstrap4-api
RUN jenkins-plugin-cli --plugins nexus-artifact-uploader
RUN jenkins-plugin-cli --plugins docker-workflow
RUN jenkins-plugin-cli --plugins pipeline-utility-steps
RUN jenkins-plugin-cli --plugins emailext-template
RUN jenkins-plugin-cli --plugins pipeline-groovy-lib