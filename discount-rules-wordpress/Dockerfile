
# Use the official WordPress image as a parent image
FROM wordpress:latest

## Install Xdebug  for this image wordpress:php7.4-apache
#RUN pecl install xdebug-3.1.5
#RUN docker-php-ext-enable xdebug
#
# Install WP-CLI
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
chmod +x wp-cli.phar && \
mv wp-cli.phar /usr/local/bin/wp

# Copy xdebug.ini into the container


#COPY xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
#COPY xdebug.ini /usr/local/etc/php/php.ini

#COPY /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini

