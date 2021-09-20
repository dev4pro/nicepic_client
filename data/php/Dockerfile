FROM php:7.4-fpm-buster
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions gd bz2 bcmath calendar exif ffi gettext \
    imagick ioncube_loader mcrypt mysqli odbc opcache pdo_mysql sqlsrv pdo_sqlsrv \
    redis pcntl soap sockets xlswriter xmlrpc yaml zip shmop sysvmsg sysvsem sysvshm xsl @composer
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"
RUN bash -c "mkdir /var/nicepic && chown -R www-data:www-data /var/nicepic"