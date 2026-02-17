# Utiliser une image PHP avec Apache
FROM php:8.2-apache

# Installer les extensions PHP nécessaires pour TYPO3
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    git \
    && docker-php-ext-install pdo_mysql mbstring gd xml opcache \
    && a2enmod rewrite

# Copier le code TYPO3 dans le conteneur
COPY public/ /var/www/html/

# Définir le répertoire de travail
WORKDIR /var/www/html

# Donner les droits d'écriture nécessaires
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Exposer le port 80
EXPOSE 80

# docker build -t typo3 ./typo3 
