FROM php:8.0-apache

COPY ../dbconn.php /var/www/html/dbconn.php
COPY ../index.php /var/www/html/index.php
COPY ../javascript /var/www/html/javascript
COPY ../css /var/www/html/css
COPY ../api /var/www/html/api
COPY . /var/www/html/account

RUN docker-php-ext-install pdo pdo_mysql
RUN a2enmod rewrite
RUN echo "DocumentRoot /var/www/html/account" >> /etc/apache2/sites-available/000-default.conf
RUN echo "DirectoryIndex transactions.php" >> /etc/apache2/apache2.conf

CMD ["apache2-foreground"]

EXPOSE 80
