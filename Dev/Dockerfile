# Verwende das offizielle Nginx-Image als Basis
FROM nginx

# Setze das Arbeitsverzeichnis im Container
WORKDIR /usr/share/nginx/html

# Kopiere die HTML-Datei in das Arbeitsverzeichnis im Container
COPY helloworld.html .

# Setze den Container so, dass er auf Port 80 lauscht
EXPOSE 80
