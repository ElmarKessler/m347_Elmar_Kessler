# Verwende das offizielle PHP-Image mit Apache als Basis
FROM php:8.0-apache

# Installiere mysqli-Erweiterung für PHP
RUN docker-php-ext-install mysqli

# Setze das Arbeitsverzeichnis im Container
WORKDIR /var/www/html

# Kopiere die PHP-Dateien in das Arbeitsverzeichnis im Container
COPY info.php .
COPY db.php .

# Port 80 für Apache freigeben
EXPOSE 80
