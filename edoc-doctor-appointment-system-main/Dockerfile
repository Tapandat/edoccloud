# ✅ Use latest stable PHP + Apache base image
FROM php:8.1-apache

# ✅ Enable required PHP extensions
RUN docker-php-ext-install mysqli pdo pdo_mysql

# ✅ Enable Apache rewrite module (needed for .htaccess, clean URLs)
RUN a2enmod rewrite

# ✅ Set working directory and copy project files
WORKDIR /var/www/html
COPY . .

# ✅ Set correct ownership for Apache
RUN chown -R www-data:www-data /var/www/html

# ✅ Expose port 80 (used by Apache)
EXPOSE 80

# ✅ Start Apache in foreground (needed for Docker)
CMD ["apache2-foreground"]
