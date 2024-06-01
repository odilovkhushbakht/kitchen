FROM php:8.3-fpm

ARG USER_ID=1000
ARG GROUP_ID=1000

RUN apt-get update && apt-get install -y gnupg gosu curl ca-certificates zip unzip

RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable pdo_mysql

RUN groupadd -g $GROUP_ID appuser && useradd -u $USER_ID -g $GROUP_ID -m appuser

RUN chown -R appuser:appuser /var/www/html

USER appuser

WORKDIR /var/www/html

EXPOSE 9000

CMD ["php-fpm"]
