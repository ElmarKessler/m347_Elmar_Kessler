## KN05
## A 
### Befehle
### Container erstellen
![](Bilder/KN05AContainerErstellen.PNG "")
Docker mit dem bind-mount erstellen: docker run -d --name kn05 -v C:\GitHub\GitHub\m347_Elmar_Kessler\KN05:/mnt nginx
![](Bilder/KN05AContainerInspect.PNG "")
Es ist noch kein File vorhanden
![](Bilder/KN05KeinFile.PNG "")
Es ist ein File vorhanden
![](Bilder/KN5FileVorhanden.PNG "")
Inhalt des File:
Schaue im skript.sh nach -> es ist ein basic Text output
## B
### Inhalt Volume
![](Bilder/KN05BInhaltVolume.PNG "")
## C
### Compose Befehle
![](Bilder/KN05CComposeBefehle.PNG "")
### Container 1 und 2
![](Bilder/KN05CContainer1.PNG "")
![](Bilder/KN05CContainer2.PNG "")

### Docker-Compose File (yaml-Datei)
Schaue bei /compose das kn05-compose.yaml an
