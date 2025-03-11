FROM node:22.14-slim

RUN npx -y playwright install-deps

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    git \
    openssh-client \
    patch \
    unzip \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN npm install -g npm
RUN npm install -g corepack

RUN corepack enable pnpm

USER node
