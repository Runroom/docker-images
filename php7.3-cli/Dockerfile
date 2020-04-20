FROM php:7.3.17-cli-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN install-php-extensions bz2 gd intl pdo_mysql zip

RUN apk --no-cache add git openssh-client patch

RUN addgroup -g 1000 jenkins
RUN adduser -G jenkins -u 1000 -D jenkins

USER jenkins

RUN composer global require hirak/prestissimo
