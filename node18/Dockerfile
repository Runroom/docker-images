FROM node:18-slim

RUN apt update \
    && apt install -y --no-install-recommends \
    git \
    openssh-client \
    patch \
    unzip \
    && apt clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

USER node
