FROM php:fpm-alpine
RUN php7.2-apache \ && docker-php-ext-install pdo_mysql \ && apache2
CMD [ "php-fpm" ]
EXPOSE 30000
ADD src /var/www/
ENV APACHE_DOCUMENT_ROOT=/var/www/html/public
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
RUN useradd /bin/bash Saidou
USER Saidou
WORKDIR /bin/bash