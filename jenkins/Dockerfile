FROM jenkins/jenkins:latest

USER root

RUN groupadd -g 999 docker
RUN usermod -aG docker jenkins

USER jenkins
