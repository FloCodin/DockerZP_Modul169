# Docker-Compose-Konfigurationsdokumentation
Dies ist eine Docker-Compose-Konfigurationsdatei, 
die mehrere Docker-Container für verschiedene Dienste definiert. 
Jeder Dienst wird mit seinem eigenen Image und seinen eigenen Konfigurationsoptionen gestartet.
Hier ist eine sinnvolle Dokumentation für diese Konfiguration:

### mediawiki-Service:
Image: mediawiki
Ports: Der Service wird auf Port 8085 des Hosts ausgeführt und ist mit Port 80 des Containers verbunden.
Volumes: Ein Docker-Volume mediawiki_data wird verwendet, um die Daten des MediaWiki-Containers persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

### nextcloud-Service:
Image: nextcloud
Ports: Der Service wird auf Port 8080 des Hosts ausgeführt und ist mit Port 80 des Containers verbunden.
Volumes: Ein Docker-Volume nextcloud_data wird verwendet, um die Daten des Nextcloud-Containers persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

### gogs-Service:
Image: gogs/gogs
Ports: Der Service wird auf Port 10080 des Hosts ausgeführt und ist mit Port 3000 des Containers verbunden.
Volumes: Ein Docker-Volume gogs_data wird verwendet, um die Daten des Gogs-Containers persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

### portainer-Service:
Image: portainer/portainer
Ports: Der Service wird auf Port 9000 des Hosts ausgeführt und ist mit Port 9000 des Containers verbunden.
Volumes: Das Docker-Socket-Volume /var/run/docker.sock wird verwendet, um auf die Docker-Engine des Hosts zuzugreifen.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

Diese Docker-Compose-Konfigurationsdatei definiert Container für 
verschiedene Dienste wie MediaWiki, Nextcloud, GitLab/Gogs und Portainer.
Jeder Dienst hat seine eigenen Port- und Volume-Konfigurationen, um die Dienste bereitzustellen und die Daten persistent zu speichern.
Der Neustart ist so konfiguriert, dass er automatisch erfolgt, falls ein Fehler auftritt.
