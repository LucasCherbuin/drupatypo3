# Utiliser l'image officielle Drupal avec PHP 8.2 et Apache
FROM drupal:10-php8.2-apache

# Installer des extensions PHP utiles pour Drupal
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libzip-dev \
    unzip \
    git \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd pdo_mysql zip opcache \
    && a2enmod rewrite

# Copier le code Drupal 

# COPY drupal/ /var/www/html/
COPY public/ /var/www/html/

# Définir le répertoire de travail
WORKDIR /var/www/html

# Définir les droits d'écriture pour Apache
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Exposer le port 80
EXPOSE 80

# docker build -t drupal ./drupal 