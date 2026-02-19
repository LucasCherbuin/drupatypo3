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


# Exposer le port 80
EXPOSE 80

# docker build -t typo3 ./typo3 
# docker compose exec typo3 bash