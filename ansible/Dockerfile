FROM python:3.11-alpine

RUN apk add --update --no-cache ansible openssh-client

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins
