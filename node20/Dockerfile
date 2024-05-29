FROM node:20.14-slim

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    git \
    openssh-client \
    patch \
    unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

USER node
