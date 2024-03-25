# m347_Elmar_Kessler

# Elmar_Kessler_M346

## Inhaltsverzeichnis

- [KN1](#kn1)
- [KN2](#kn2)
    - [A Lab 4.1 - EC2](#a-lab-41---ec2)
    - [A Lab 4.2 - S3](#a-lab-42---s3)
    - [B](#b)
- [KN3](#kn3)
    - [A](#a-1)
    - [B](#b-1)
    - [C](#c-1)
- [KN07](#kn07)
    - [A 1 Rehosting](#a-1-rehosting)
    - [A 2 Replatforming](#a-2-replatforming)
    - [A 3 Repurchasing](#a-3-repurchasing)
    - [B Interpretation der Resultate](#b-interpretation-der-resultate)
- [KN04](#kn04)
    - [A](#a-2)
    - [B](#b-2)
    - [C](#c-2)
    - [D](#d)
- [KN05](#kn05)
  
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
## KN2
### A
### Dockerbefehle stehen im KN02A.txt

### Screenshot aus Docker Desktop, welcher das Image kn02a zeigt
![](/KN02ADocker.PNG "")
### Screenshot der HTML-Seite, der die Seite helloworld.html zeigt, nachdem der Container gestartet wurde
![](/KN02AHelloWorld.PNG "")

### B
### DB: telnet Befehl der zeigt, dass der Zugriff auf den DB Server funktioniert (Screenshot)
![](/KN02BTelnet.PNG "")
### Web: Screenshots der beiden Seiten info.php und db.php
![](/KN02BInfo.PNG "")
![](/KN02Bdb.PNG "")
### DB: docker build und docker run Befehle für Ihren DB-Container
![](/KN02B.PNG "")

### Commands für DB und Web sind im KN02B-Commands.txt file.
Angepasste PHP-Dateien im Repo

## KN03
1)
busybox1:
- Ip:172.17.0.3
- Gateway:172.21.0.1

usybox2:
- Ip:172.17.0.2
- Gateway:172.21.0.1

busybox3:
- Ip:172.18.0.3
- Gateway:172.17.0.1

busybox4:
- Ip:172.18.0.2
- Gateway:172.17.0.1
### Interaktive Session auf busybox1
### ping busybox2, ping IP-von-busybox2
![](/KN03A2.2-4.PNG "")
### ping busybox3, ping IP-von-busybox3
![](/KN03A2.3-5.PNG "")

### Interaktive Session auf busybox3
### ping busybox1, ping busybox4
![](/KN03A3.2-3.PNG "")
### ping IP-von-busybox1, ping IP-von-busybox4
![](/KN03A3.4-5.PNG "")

### Zusammenfassung:
Die Befehle: ping busybox2 und ping busybox3 funktionieren in der Interaktiven Session auf busybox1 nicht. Ausserdem erhält der ping IP-von-busybox3 keine Antwort zurück.
Der Grund ist, dass diese nicht den gleichen Default-Gateway wie busybox1(172.17.0.3)haben. Kurz gesagt: Sind die container nicht im gleichen Netzwerk.

Die ping busybox4 Befehl in der Interaktiven Session  von busybox3 funktioniert als einziger.

In Kn02 befanden sich die beiden Docker Container im Bridge Netzwerk. Sie konnten zusammen über den Link kommunizieren. 
Container können ohne Link kommunizieren, wenn sie im gleichen Netzwerk sind.

## KN07
## A
## 1 Rehosting
![](/Uebersicht.PNG "")
![](/UebersichtAz.PNG "")
## Warum diese Auswahl:
Ich habe bei der Konfiguration des EC2 Webservers darauf geachtet, dass alle Anforderungen erfüllt oder sogar übertroffen wurden. Ich entschied mich jedoch immer für die günstigste Variante der Konfiguration. Wenn die Anforderung z.B. 20 GB Speicher war und entweder 16 oder 32 GB zur Auswahl stünden, entschiede ich mich für 32 GB um die Anforderung abzudecken. 
Dies habe ich bei AWS sowie auch Azure getan, wobei die vorgegeben Ressourcenpakete näher an den Anforderungen waren.

## 2 Replatforming
![](/HekoruUebersicht.PNG "")
![](/PerformanceM.PNG "")
![](/Premium.PNG "")
## Warum diese Auswahl:
Beim Dynos entschied ich ich für die Performance M Variante, da sie mit 2.5 GB RAM die Anforderung von 2 GB RAM erfüllt. Das Performance M Paket verfügt über die meisten Funktionen, die ein Nutzer braucht. Bei der Datenbank entschied ich mich für die Heroku Postgres Premium Variante. Gründe dafür waren die hohe Zuverlässigkeit und maximale Auszeit von nur 15 Minuten pro Monat.

## 3 Repurchasing

## Zoho CRM
![](/zoho.PNG "")

## Salesforce
![](/salesforce.PNG "")

## Warum diese Auswahl:
Bei ZOHO CRM kostet das Standardangebot für 16 Mitarbeiter insgesamt 224$ pro Monat, während das Starterangebot bei Salesforce für 16 Mitarbeiter 400$ pro Monat kostet. Ich habe mich für die kostengünstigste Option bei beiden Anbietern entschieden. Obwohl die Angebote nicht übermäßig teuer sind, ist Salesforce teurer als Zoho CRM. Aufgrund des Preisunterschieds habe ich mich für Zoho CRM als SaaS-Option entschieden.

Beim Vergleich der verschiedenen Cloud-Service-Modelle, nämlich SaaS (Software as a Service), PaaS (Platform as a Service) und IaaS (Infrastructure as a Service), sind einige wichtige Überlegungen zu beachten.

SaaS: Unternehmen wie Zoho und Salesforce bieten SaaS-Lösungen an. Mit SaaS erhalten Sie fertige Produkte, ohne sich um die technischen Details kümmern zu müssen. Dies ermöglicht eine schnelle Bereitstellung und ist besonders attraktiv für Unternehmen, die eine benutzerfreundliche Lösung suchen. Allerdings können SaaS-Optionen aufgrund der enthaltenen Wartung und Aktualisierungskosten etwas teurer sein. Ihre Entscheidung für SaaS hängt von der Dringlichkeit Ihrer Anforderungen und Ihrem Budget ab.

PaaS: Heroku und Google App Engine sind Beispiele für PaaS-Anbieter. Mit PaaS müssen Sie sich nicht um die Serverkonfiguration kümmern, müssen jedoch Ihre eigenen Anwendungen entwickeln und programmieren. Dies ist ideal für Unternehmen, die die Flexibilität wünschen, eigene Anwendungen zu erstellen und zu verwalten, aber die Serverseite auslagern möchten. PaaS-Modelle sind oft kostengünstiger als SaaS, insbesondere wenn Sie über die erforderlichen Entwicklerfähigkeiten und Ressourcen verfügen.

IaaS: Amazon Web Services (AWS) und Microsoft Azure sind führende IaaS-Anbieter. Bei IaaS sind Sie für die vollständige Konfiguration und Verwaltung der Infrastruktur verantwortlich. Dies bietet maximale Kontrolle und Flexibilität, kann jedoch komplex sein und erfordert technisches Know-how. IaaS ist in der Regel kostengünstiger als SaaS und PaaS, erfordert jedoch mehr technisches Wissen und Ressourcen für die Verwaltung. Ihre Wahl für IaaS sollte von Ihrem Bedarf an Kontrolle über die Infrastruktur und den vorhandenen Fähigkeiten in Ihrem Team abhängen.

Die endgültige Entscheidung zwischen diesen Modellen sollte sorgfältig abgewogen werden. Berücksichtigen Sie Faktoren wie Skalierbarkeit, Sicherheit, langfristige Kosten, die Verfügbarkeit von Personalressourcen und die Fähigkeit, zukünftige Anforderungen zu erfüllen. Eine gründliche Analyse Ihrer Geschäftsanforderungen ist ratsam, und es kann auch sinnvoll sein, eine Kombination dieser Modelle in Betracht zu ziehen, um die besten Ergebnisse für Ihr Unternehmen zu erzielen.

## B Iterpretation der Resulatate

Die Unterschiede zwischen den verschiedenen Optionen sind ziemlich groß. Wenn wir über den Preis sprechen, ist AWS mit seinem Rehosting-Service normalerweise am günstigsten. Herokus Replatforming-Service ist im Vergleich dazu teurer. Das liegt daran, dass Heroku eine umfassendere Konfiguration bietet, was die Kosten erhöht.

Die Frage nach dem "kostengünstigsten" hängt stark von Ihren individuellen Anforderungen ab. In der Regel ist AWS jedoch in Bezug auf den Preis wettbewerbsfähig und bietet oft eine wirtschaftliche Lösung.

Warum kostet eine Option mehr als die andere? Dies kann vor allem auf die zusätzlichen Funktionen und individuellen Anforderungen zurückzuführen sein. Heroku bietet beispielsweise eine umfangreichere Anpassungsmöglichkeit, was die Kosten erhöhen kann. Dennoch bietet es auch einen erweiterten Funktionsumfang.

Es ist entscheidend zu beachten, dass "teurer" nicht zwangsläufig "übermäßig teuer" bedeutet. Die höheren Kosten können durch zusätzliche Leistungen und Funktionen gerechtfertigt sein, die möglicherweise für Ihre speziellen Anforderungen von großem Wert sind. Daher ist es ratsam, Ihre Entscheidung nicht ausschließlich aufgrund des Preises zu treffen, sondern auch die individuellen Anforderungen und den Mehrwert jeder Option sorgfältig abzuwägen.

Persönlich neige ich zur Auswahl zwischen AWS und Zoho, da beide preislich attraktiv sind und eine breite Palette von Dienstleistungen bieten. Für mich hängt die endgültige Entscheidung von den spezifischen Anforderungen meines Projekts ab, aber diese beiden Optionen bieten eine solide Grundlage für die meisten Anwendungsfälle.

## KN04
## A
## Screenshot der S3-Objekte im Bucket
![](/KN04S3Bucket.PNG "")
## Screenshot des Bildes im Browser (mit sichtbarer URL)
![](/KN04BildInS3.PNG "")
## B
## Screenshot der Seite image.php (mit sichtbarer URL)
![](/KN04Bimage-phpPNG.PNG "")
## Neues Cloud-Init für die Web-Instanz (Siehe KN04yaml.PNG)
![](/KN04yaml.PNG "")
## C
## Screenshots der Liste der EBS (2 Volumen) der Instanz
![](/KN4NewVolume.PNG "")

## D

Name	            Typ	  Persistenz
EBS Root	        Hot	  Nein
EBS 2nd volume	  Hot	  Ja
S3	              Warm	Ja

Die EBS-Root-Konfiguration spielt eine entscheidende Rolle, da sie als Host für den Webserver fungiert und stets die image.php-Datei bereitstellen muss. Sie ist zweifellos "hot", da sie bei Bedarf sofortige Zugriffe ermöglicht. Allerdings ist sie nicht persistent, da sämtliche Dateien nach dem Herunterfahren der Instanz gelöscht werden.
Das EBS-Second-Volume hingegen zeichnet sich durch seine Kälte aus, da es zwar keine direkte Bereitstellung von Daten bietet, jedoch aufgrund seiner Persistenz die Informationen auch nach dem Herunterfahren der Instanz bewahrt, ohne sie zu löschen.
S3 ist für die Bereitstellung des Bildes, das von der image.php-Datei genutzt wird, von großer Bedeutung. Die Persistenz dieses Speichers ist bemerkenswert, da die Daten auch nach dem Herunterfahren erhalten bleiben, ohne gelöscht zu werden.
ChatGPT
Hier ist eine beispielhafte Struktur, die du in dein README.md einfügen könntest, um ein Inhaltsverzeichnis zu erstellen:

markdown
Copy code
# Elmar_Kessler_M346
- [KN1](#kn1)
- [KN2](#kn2)
  - [A Lab 4.1 - EC2](#a-lab-41---ec2)
  - [A Lab 4.2 - S3](#a-lab-42---s3)
  - [B](#b)
- [KN3](#kn3)
  - [A](#a)
  - [B](#b-1)
  - [C](#c)
- [KN07](#kn07)
  - [A 1 Rehosting](#a-1-rehosting)
  - [A 2 Replatforming](#a-2-replatforming)
  - [A 3 Repurchasing](#a-3-repurchasing)
  - [B Interpretation der Resultate](#b-interpretation-der-resultate)
- [KN04](#kn04)
  - [A](#a-2)
  - [B](#b-2)
  - [C](#c-2)
  - [D](#d)
  
## KN1
### Der VM wird weniger CPUS zugeteilt als der PC zu Verfügung hat.
![Bild1](/wenigerCPU.png "")
### Der VM wird weniger RAM zugeteilt als der PC zu Verfügung hat.
![Bild2](/wenigerRAM.png "")
### Der VM wird mehr CPUS zugeteilt als der PC zu Verfügung hat.
![Bild3](/zuvielCPU.png "")
### Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.
![Bild4](/zuvielRAM.png "")

## KN2
### A Lab 4.1 - EC2
![Bild5](/WebseiteMitUrlEC2.PNG "")
![Bild6](/ListeInstanzenEC2.PNG "")
![Bild7](/DetailsEC2.PNG "")
![Bild8](/ListeInboundRegelnEC2.PNG "")

### A Lab 4.2 - S3
![Bild9](/ListeBucketsS3.png "")
![Bild10](/webseiteMitUrlS3.PNG "")
![Bild11](/ListeDateienInucketS3.PNG "")
![Bild12](/EigenschaftenS3.png "")

### B
![Bild13](/Authenticated.PNG "")
![Bild14](/Unauthenticated.PNG "")
![Bild15](/SeeKeyPair.PNG "")

## KN3
### A
![Bild16](/KN3UsedKey.PNG "")
![Bild17](/KN3ErsterKey.PNG "")
![Bild18](/KN3List.PNG "")
![Bild19](/KN3ZweiterKey.PNG "")

### B
![Bild20](/KN3C.PNG "")

## KN07
### 1 Rehosting
![Bild21](/Uebersicht.PNG "")
![Bild22](/UebersichtAz.PNG "")

### 2 Replatforming
![Bild23](/HekoruUebersicht.PNG "")
![Bild24](/PerformanceM.PNG "")
![Bild25](/Premium.PNG "")

### 3 Repurchasing
![Bild26](/zoho.PNG "")
![Bild27](/salesforce.PNG "")

### B Interpretation der Resultate
Die Unterschiede zwischen den verschiedenen Optionen...

## KN04
### A
![Bild28](/KN04S3Bucket.PNG "")
![Bild29](/KN04BildInS3.PNG "")

### B
![Bild30](/KN04Bimage-phpPNG.PNG "")
![Bild31](/KN04yaml.PNG "")

### C
![Bild32](/KN4NewVolume.PNG "")

### D
Beschreibung der Persistenz der verschiedenen Speichertypen.
Das ist eine grobe Darstellung, wie du das Inhaltsverzeichnis und die Bilder in dein README.md einfügen könntest. Bitte achte darauf, die Bild- und Textbeschreibungen sowie die Verlinkungen entsprechend deiner spezifischen Ordner- und Dateistruktur in deinem Projekt anzupassen.

## KN1
### Der VM wird weniger CPUS zugeteilt als der PC zu Verfügung hat.
![Der VM wird weniger CPUS zugeteilt als der PC zu Verfügung hat.](/wenigerCPU.png "")
### Der VM wird weniger RAM zugeteilt als der PC zu Verfügung hat.
![Der VM wird weniger RAM zugeteilt als der PC zu Verfügung hat.](/wenigerRAM.png "")
### Der VM wird mehr CPUS zugeteilt als der PC zu Verfügung hat.
![Der VM wird mehr CPUS zugeteilt als der PC zu Verfügung hat.](/zuvielCPU.png "")
### Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.
![Der VM wird mehr RAM zugeteilt als der PC zu Verfügung hat.](/zuvielRAM.png "")
(KN1 in Zusammenarbeit mit Ruben gemacht.)

## KN2
## A Lab 4.1 - EC2
### HTML-Seite, inkl. URL
![](/WebseiteMitUrlEC2.PNG "")
### Liste der EC2-Instanzen
![](/ListeInstanzenEC2.PNG "")
### Details der Web Server-Instanz (öffentliche IP sichtbar)
![](/DetailsEC2.PNG "")
### Security-Group: Liste der Inbound-Regeln
![](/ListeInboundRegelnEC2.PNG "")

## A Lab 4.2 - S3
### Liste der Buckets
![](/ListeBucketsS3.png "")
### HTML-Seite, inkl. URL
![](/webseiteMitUrlS3.PNG "")
### Liste der Dateien im Bucket
![](/ListeDateienInucketS3.PNG "")
### Eigenschaften von "Static website hosting"
![](/EigenschaftenS3.png "")

## B 
### Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des ersten Schlüssels
![](/Authenticated.PNG "")
### Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des zweiten Schlüssels
![](/Unauthenticated.PNG "")
### Screenshot der Instanz-Detail (oder Liste), so dass der verwendete Schlüssel sichtbar ist
![](/SeeKeyPair.PNG "")

## C
### Screenshot von Index Seite
![](/Apache2.PNG "")
### Screenshot von Info Seite
![](/PhpPage.PNG "")
### Screenshot von DB Seite
![](/DBPage.PNG "")
## KN3
## A 
Siehe commented-cloud-config.yaml file im Repository an.

## B 
### Ein Screenshot der Details oder Liste der Instanz, welcher den verwendeten Key zeigt
![](/KN3UsedKey.PNG "")
### Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des ersten Schlüssels
![](/KN3ErsterKey.PNG "")
![](/KN3List.PNG "")
### Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des zweiten Schlüssels
![](/KN3ZweiterKey.PNG "")

## C
![](/KN3C.PNG "")

## KN07
## A
## 1 Rehosting
![](/Uebersicht.PNG "")
![](/UebersichtAz.PNG "")
## Warum diese Auswahl:
Ich habe bei der Konfiguration des EC2 Webservers darauf geachtet, dass alle Anforderungen erfüllt oder sogar übertroffen wurden. Ich entschied mich jedoch immer für die günstigste Variante der Konfiguration. Wenn die Anforderung z.B. 20 GB Speicher war und entweder 16 oder 32 GB zur Auswahl stünden, entschiede ich mich für 32 GB um die Anforderung abzudecken. 
Dies habe ich bei AWS sowie auch Azure getan, wobei die vorgegeben Ressourcenpakete näher an den Anforderungen waren.

## 2 Replatforming
![](/HekoruUebersicht.PNG "")
![](/PerformanceM.PNG "")
![](/Premium.PNG "")
## Warum diese Auswahl:
Beim Dynos entschied ich ich für die Performance M Variante, da sie mit 2.5 GB RAM die Anforderung von 2 GB RAM erfüllt. Das Performance M Paket verfügt über die meisten Funktionen, die ein Nutzer braucht. Bei der Datenbank entschied ich mich für die Heroku Postgres Premium Variante. Gründe dafür waren die hohe Zuverlässigkeit und maximale Auszeit von nur 15 Minuten pro Monat.

## 3 Repurchasing

## Zoho CRM
![](/zoho.PNG "")

## Salesforce
![](/salesforce.PNG "")

## Warum diese Auswahl:
Bei ZOHO CRM kostet das Standardangebot für 16 Mitarbeiter insgesamt 224$ pro Monat, während das Starterangebot bei Salesforce für 16 Mitarbeiter 400$ pro Monat kostet. Ich habe mich für die kostengünstigste Option bei beiden Anbietern entschieden. Obwohl die Angebote nicht übermäßig teuer sind, ist Salesforce teurer als Zoho CRM. Aufgrund des Preisunterschieds habe ich mich für Zoho CRM als SaaS-Option entschieden.

Beim Vergleich der verschiedenen Cloud-Service-Modelle, nämlich SaaS (Software as a Service), PaaS (Platform as a Service) und IaaS (Infrastructure as a Service), sind einige wichtige Überlegungen zu beachten.

SaaS: Unternehmen wie Zoho und Salesforce bieten SaaS-Lösungen an. Mit SaaS erhalten Sie fertige Produkte, ohne sich um die technischen Details kümmern zu müssen. Dies ermöglicht eine schnelle Bereitstellung und ist besonders attraktiv für Unternehmen, die eine benutzerfreundliche Lösung suchen. Allerdings können SaaS-Optionen aufgrund der enthaltenen Wartung und Aktualisierungskosten etwas teurer sein. Ihre Entscheidung für SaaS hängt von der Dringlichkeit Ihrer Anforderungen und Ihrem Budget ab.

PaaS: Heroku und Google App Engine sind Beispiele für PaaS-Anbieter. Mit PaaS müssen Sie sich nicht um die Serverkonfiguration kümmern, müssen jedoch Ihre eigenen Anwendungen entwickeln und programmieren. Dies ist ideal für Unternehmen, die die Flexibilität wünschen, eigene Anwendungen zu erstellen und zu verwalten, aber die Serverseite auslagern möchten. PaaS-Modelle sind oft kostengünstiger als SaaS, insbesondere wenn Sie über die erforderlichen Entwicklerfähigkeiten und Ressourcen verfügen.

IaaS: Amazon Web Services (AWS) und Microsoft Azure sind führende IaaS-Anbieter. Bei IaaS sind Sie für die vollständige Konfiguration und Verwaltung der Infrastruktur verantwortlich. Dies bietet maximale Kontrolle und Flexibilität, kann jedoch komplex sein und erfordert technisches Know-how. IaaS ist in der Regel kostengünstiger als SaaS und PaaS, erfordert jedoch mehr technisches Wissen und Ressourcen für die Verwaltung. Ihre Wahl für IaaS sollte von Ihrem Bedarf an Kontrolle über die Infrastruktur und den vorhandenen Fähigkeiten in Ihrem Team abhängen.

Die endgültige Entscheidung zwischen diesen Modellen sollte sorgfältig abgewogen werden. Berücksichtigen Sie Faktoren wie Skalierbarkeit, Sicherheit, langfristige Kosten, die Verfügbarkeit von Personalressourcen und die Fähigkeit, zukünftige Anforderungen zu erfüllen. Eine gründliche Analyse Ihrer Geschäftsanforderungen ist ratsam, und es kann auch sinnvoll sein, eine Kombination dieser Modelle in Betracht zu ziehen, um die besten Ergebnisse für Ihr Unternehmen zu erzielen.

## B Iterpretation der Resulatate

Die Unterschiede zwischen den verschiedenen Optionen sind ziemlich groß. Wenn wir über den Preis sprechen, ist AWS mit seinem Rehosting-Service normalerweise am günstigsten. Herokus Replatforming-Service ist im Vergleich dazu teurer. Das liegt daran, dass Heroku eine umfassendere Konfiguration bietet, was die Kosten erhöht.

Die Frage nach dem "kostengünstigsten" hängt stark von Ihren individuellen Anforderungen ab. In der Regel ist AWS jedoch in Bezug auf den Preis wettbewerbsfähig und bietet oft eine wirtschaftliche Lösung.

Warum kostet eine Option mehr als die andere? Dies kann vor allem auf die zusätzlichen Funktionen und individuellen Anforderungen zurückzuführen sein. Heroku bietet beispielsweise eine umfangreichere Anpassungsmöglichkeit, was die Kosten erhöhen kann. Dennoch bietet es auch einen erweiterten Funktionsumfang.

Es ist entscheidend zu beachten, dass "teurer" nicht zwangsläufig "übermäßig teuer" bedeutet. Die höheren Kosten können durch zusätzliche Leistungen und Funktionen gerechtfertigt sein, die möglicherweise für Ihre speziellen Anforderungen von großem Wert sind. Daher ist es ratsam, Ihre Entscheidung nicht ausschließlich aufgrund des Preises zu treffen, sondern auch die individuellen Anforderungen und den Mehrwert jeder Option sorgfältig abzuwägen.

Persönlich neige ich zur Auswahl zwischen AWS und Zoho, da beide preislich attraktiv sind und eine breite Palette von Dienstleistungen bieten. Für mich hängt die endgültige Entscheidung von den spezifischen Anforderungen meines Projekts ab, aber diese beiden Optionen bieten eine solide Grundlage für die meisten Anwendungsfälle.

## KN04
## A
## Screenshot der S3-Objekte im Bucket
![](/KN04S3Bucket.PNG "")
## Screenshot des Bildes im Browser (mit sichtbarer URL)
![](/KN04BildInS3.PNG "")
## B
## Screenshot der Seite image.php (mit sichtbarer URL)
![](/KN04Bimage-phpPNG.PNG "")
## Neues Cloud-Init für die Web-Instanz (Siehe KN04yaml.PNG)
![](/KN04yaml.PNG "")
## C
## Screenshots der Liste der EBS (2 Volumen) der Instanz
![](/KN4NewVolume.PNG "")

## D

Name	            Typ	  Persistenz
EBS Root	        Hot	  Nein
EBS 2nd volume	  Hot	  Ja
S3	              Warm	Ja

Die EBS-Root-Konfiguration spielt eine entscheidende Rolle, da sie als Host für den Webserver fungiert und stets die image.php-Datei bereitstellen muss. Sie ist zweifellos "hot", da sie bei Bedarf sofortige Zugriffe ermöglicht. Allerdings ist sie nicht persistent, da sämtliche Dateien nach dem Herunterfahren der Instanz gelöscht werden.
Das EBS-Second-Volume hingegen zeichnet sich durch seine Kälte aus, da es zwar keine direkte Bereitstellung von Daten bietet, jedoch aufgrund seiner Persistenz die Informationen auch nach dem Herunterfahren der Instanz bewahrt, ohne sie zu löschen.
S3 ist für die Bereitstellung des Bildes, das von der image.php-Datei genutzt wird, von großer Bedeutung. Die Persistenz dieses Speichers ist bemerkenswert, da die Daten auch nach dem Herunterfahren erhalten bleiben, ohne gelöscht zu werden.

## KN05
## A
## Diagramm als Bild
![](/KN05A.PNG "")
## B
## Screenshot der Subnetzen, die die Namen zeigen
![](/KN05BSubnet.PNG "")
IP 1: 172.31.2.0 IP 2: 172.31.4.0
## C
## PHP Page, Apache2
![](/PhpPage.PNG "")
![](/Apache2.PNG "")
## Screenshot der Liste der Sicherheitsgruppe mit sprechenden Namen/Feldern
![](/KN05CSecurityGroups.PNG "")
## Screenshot der Inbound-Regel für die DB-Sicherheitsgruppe
![](/KN05CInboundRules.PNG "")
## Screenshot der Liste der Elastic IPs mit sprechenden Namen
![](/KN05CElasticIPs.PNG "")

## Screenshot der Liste der Instanzen, wenn beide Instanzen gestoppt sind.
![](/KN05ListeInstanzenStopped.PNG "")
## Screenshot der Details beider Instanzen, so dass die Subnet ID sichtbar ist
## EC2 DB-Server
![](/KN05DetailDBServer.PNG "")
## EC2 Webserver
![](/KN05CWebserverDetails.PNG "")
