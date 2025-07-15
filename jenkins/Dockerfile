FROM jenkins/jenkins:2.519-jdk21

USER root

RUN apt-get update \
    && apt-get install --no-install-recommends --assume-yes \
    docker.io \
    make \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN groupmod -g 1750 docker
RUN usermod -aG docker jenkins

USER jenkins
