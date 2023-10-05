FROM ghcr.io/basecamp/kamal:v1.0.0

RUN apk --no-cache add shadow

RUN addgroup -g 1000 jenkins

RUN adduser -G jenkins -u 1000 -D jenkins
RUN usermod -aG docker jenkins

ENTRYPOINT []

USER jenkins
