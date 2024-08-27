FROM jenkins/jenkins:2.474

USER root

RUN apt-get update \
    && apt-get install --no-install-recommends --assume-yes \
    docker.io \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN groupmod -g 999 docker
RUN usermod -aG docker jenkins

USER jenkins
