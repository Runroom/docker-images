FROM jenkins/jenkins:2.285

USER root

RUN groupadd -g 999 docker
RUN usermod -aG docker jenkins

USER jenkins
