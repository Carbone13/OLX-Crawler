FROM php:alpine
RUN apk add --update bash
WORKDIR /code/crawl-olx
COPY crawl-olx .
RUN docker-php-ext-install sockets
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
RUN composer install
#RUN php crawl-data-motor.php
WORKDIR /code/
# Run the cron
RUN echo '*/30 * * * * /usr/local/bin/php /code/crawl-olx/crawl-data-motor.php' > /etc/crontabs/root
