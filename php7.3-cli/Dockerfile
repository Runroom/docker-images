FROM php:7.3.22-cli-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer:1 /usr/bin/composer /usr/bin/
COPY --from=composer:2 /usr/bin/composer /tmp/composer-v2

# Remove this trick when using only one version of composer
RUN echo -e '#!/bin/ash\nCOMPOSER_HOME=~/.composer-v2 /tmp/composer-v2 "$@"' > /usr/bin/composer-v2 && \
    chmod +x /usr/bin/composer-v2

RUN install-php-extensions bz2 gd intl pdo_mysql zip pcov

RUN apk --no-cache add git openssh-client patch unzip

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins

# Remove this when using only composer 2
RUN composer global require hirak/prestissimo
