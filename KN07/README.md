## A 
### Unterschied Pods und Replicas
Ein Pod ist eine Art Struktur welche ein oder mehrere Container enthalten kann, welche über den localhost (öffentliche IP-Adresse) miteinander kommunizieren.
Der Vorteil ist, dass sich die Container die gemeinsamen Ressourcen (Volume Speicher, Netzwerk Konfiguration sowie IP-Adressen)eines Pods teilen können. 
Pods sind kleine ausführbare Dienste einer App oder einem Dateisystem. Der Unterschied zur Replica besteht darin, dass Replica kopierte Pods darstellt. Mit Replicas kann man mehrer identische Pods verwalten und Skalieren.
Der Vorteil von Replicas sind das man die Last von einem Pod auf mehrer identische Pods aufteilen kann.
### Unterschied Service und Deployment
Ein Service ermöglicht die Kommunikation zwischen den verschiedenen Teilen einer Anwendung im Kubernetes-Cluster. Ausserdem gewährleistet ein Service Load-Balancing. Ein Deployment hingegen verwaltet die Anzahl der laufenden Kopien einer Anwendung und deren Skalierung im Cluster.

### Welches Problem löst Ingress?
Ingress regelt die Steuerung von eingehendem Webverkehr von ausserhalb des Kubernetes-Cluster flexibel. Ein Vorteil ist die einfache Konfiguration von Regeln, um den Webverkehr auf verschiedene Dienste im Cluster zu leiten. Dadurch können Benutzer von außerhalb auf Anwendungen im Cluster zugreifen, ohne dass jeder einzelne Dienst separate Konfigurationen benötigt.

### Was ist ein Statefulset? + Beispiel
Ein StatefulSet in Kubernetes ähnelt einem Deployment, aber jeder seiner Pods hat eine teilweise einzigartige Verbindung. Dadurch können verschiedene Pods unterschiedliche Speicheranforderungen haben. Zum Beispiel persistente Dateien wie index.html für einen Webserver. Es unterstützt anwendungsbezogene Workloads mit spezifischen Persistenz- und Identitätsanforderungen.
