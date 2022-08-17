FROM php:7.1.33-cli-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer:2 /usr/bin/composer /usr/bin/

RUN install-php-extensions bz2 gd intl pdo_mysql pdo_pgsql zip mcrypt
RUN apk --no-cache add git openssh-client patch unzip

COPY extra.ini $PHP_INI_DIR/conf.d/php.ini

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins

RUN composer global require hirak/prestissimo
