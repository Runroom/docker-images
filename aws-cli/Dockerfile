FROM python:3.10-alpine

RUN pip install awscli ecs-deploy --upgrade

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins
