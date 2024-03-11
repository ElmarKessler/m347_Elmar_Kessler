# Verwende das offizielle MariaDB-Image als Basis
FROM mariadb

# Umgebungsvariablen für MariaDB setzen
ENV MYSQL_ROOT_PASSWORD=password
ENV MYSQL_DATABASE=mysql
ENV MYSQL_USER=root
ENV MYSQL_PASSWORD=password

# Kopiere SQL-Skript für Initialisierung in das Docker-Image
# COPY init.sql /docker-entrypoint-initdb.d/

# Port 3306 für MySQL freigeben
EXPOSE 3306