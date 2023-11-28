FROM ghcr.io/basecamp/kamal:v1.3.0

RUN apk --no-cache add shadow

# Move ping group from gid 999 to 99
RUN sed -i "s/999/99/" /etc/group

RUN groupmod -g 999 docker
RUN addgroup -g 1000 jenkins

RUN adduser -G jenkins -u 1000 -D jenkins
RUN usermod -aG docker jenkins

ENTRYPOINT []

USER jenkins
