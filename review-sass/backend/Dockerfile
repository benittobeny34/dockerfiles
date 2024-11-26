
FROM php:8.2-fpm

# Install dependencies

RUN apt-get update && apt-get install -y \
    zip unzip curl libpq-dev libonig-dev libicu-dev \
    && docker-php-ext-install pdo pdo_pgsql bcmath mbstring intl opcache \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www

# Copy existing application code
COPY . .

# Install Laravel dependencies
RUN if [ -f composer.json ]; then composer install; fi

# Set permissions
RUN chown -R www-data:www-data /var/www \
    && chmod -R 775 /var/www/storage /var/www/bootstrap/cache

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start Laravel server for development
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]

