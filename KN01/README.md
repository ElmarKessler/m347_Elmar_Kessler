## KN1
## A
![Der VM wird weniger CPUS zugeteilt als der PC zu Verfügung hat.](/KN01A1.PNG "")
![Der VM wird weniger RAM zugeteilt als der PC zu Verfügung hat.](/KN01A2.PNG "")
## B
# 3. docker run -d -p 80:80 docker/getting-started
-d: Führt den Docker-Container im Hintergrund aus.
-p 80:80: Mappt den Port 80 des Hosts auf den Port 80 des Containers.
docker/getting-started: Das Docker-Image, aus dem der Container erstellt wird.
![Der VM wird mehr CPUS zugeteilt als der PC zu Verfügung hat.](/KN01B2.2.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B2.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B4.1.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B4.4.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B5.1.PNG "")
#### Der Befehl "docker run -d ubuntu" wurde erfolgreich ausgeführt. Zuerst wurde das Ubuntu-Image lokal nicht gefunden, daher hat Docker es automatisch von Docker Hub heruntergeladen. Der Container wurde dann erstellt. Der Container wurde nicht gestartet (siehe nächstes Bild) Die Ausgabe enthält die ID des erstellten Containers (hier: 79290ea45770b84009254ccfa7e1751c351d962eb6232aabe4a8dc96c0e31f40).
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B5.2.PNG "")

![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B6.1.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B6.2.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B7.1.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B8.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B9.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01B10.PNG "")
#### Commands siehe KN01B-Commands.txt file
## C
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01C1.PNG "")
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01C2.PNG "")
## D
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/KN01D1.PNG "")
#### Commands
1. Nginx Herunterladen
	- docker pull nginx:latest
Was ist ein Tag?
Ein Tag ist eine Kennzeichnung von einem Docker. Ein Tag wird verwendet um eine Version oder Konfiguration eines Images eindeutig zu identifizieren.
Der Tag "latest" zeigt, dass die neuste Version verwendet wird.

2. Nginx in das eigene repo kopieren
	- docker tag nginx:latest elmarkessler031/m347:nginx
3. MariaDb herunterladen
	- docker pull mariadb:latest
4. MariaDb in das eigene repo kopieren
	- docker tag mariadb:latest elmarkessler031/m347:mariadb
5. Alles auf repo pushen
	- docker push elmarkessler031/m347:nginx
	- docker push elmarkessler031/m347:mariadb
