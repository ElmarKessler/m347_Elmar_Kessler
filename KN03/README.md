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
