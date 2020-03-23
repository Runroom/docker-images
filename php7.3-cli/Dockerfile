FROM php:7.3-cli-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN install-php-extensions bz2 gd intl pdo_mysql zip

RUN apk --no-cache add git openssh
