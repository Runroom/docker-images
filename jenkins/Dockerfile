FROM jenkins/jenkins:2.391

USER root

RUN apt-get update \
    && apt-get install --no-install-recommends --assume-yes \
    docker.io

RUN groupadd -g 999 docker
RUN usermod -aG docker jenkins

USER jenkins
