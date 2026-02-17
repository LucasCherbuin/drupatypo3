FROM drupal:10-apache

# Installer extensions PHP utiles
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Copier le code local si nécessaire
COPY html/ /var/www/html/

# Permissions
RUN chown -R www-data:www-data /var/www/html