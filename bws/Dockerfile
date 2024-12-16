FROM debian:trixie-slim

ENV BITWARDEN_VERSION=1.0.0

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    unzip \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN ARCH=$(uname -m) && \
    curl --insecure -Lo bws.zip https://github.com/bitwarden/sdk-sm/releases/download/bws-v${BITWARDEN_VERSION}/bws-${ARCH}-unknown-linux-gnu-${BITWARDEN_VERSION}.zip

RUN unzip bws.zip -d /usr/local/bin
RUN chmod +x /usr/local/bin/bws
RUN rm bws.zip

RUN groupadd --gid 1000 jenkins
RUN useradd --uid 1000 --gid 1000 jenkins --create-home

USER jenkins
