FROM php:8.3.16-cli-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer:2.9 /usr/bin/composer /usr/bin/

RUN install-php-extensions apcu bz2 gd intl opcache pdo_mysql pdo_pgsql zip pcntl pcov exif bcmath calendar
RUN apk --no-cache add git openssh-client patch unzip rsync

COPY extra.ini $PHP_INI_DIR/conf.d/php.ini

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins
