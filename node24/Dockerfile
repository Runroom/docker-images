FROM node:24.11-slim

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

RUN npm install -g npm corepack

RUN corepack enable pnpm

USER node
