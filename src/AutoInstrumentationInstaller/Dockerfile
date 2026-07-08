FROM composer:2.10.2@sha256:5946476338742b200bb9ff88f8be56275ddae4b3949c72305cb0dbf10cfcb760 as composer
FROM php:8.5.8@sha256:5749d0780f2d0c993a63b4eac18501f74d2ca8735aeb97d7fd7c8efb7b9b7467
WORKDIR /srv/app
COPY --from=composer /usr/bin/composer /usr/local/bin/composer
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions \
  && install-php-extensions \
    xdebug \
    zip
