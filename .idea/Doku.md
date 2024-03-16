Docker-Compose-Konfigurationsdokumentation mit MySQL-Integration für GitLab
Diese Dokumentation beschreibt die Docker-Compose-Konfigurationsdatei, 
die MediaWiki, Nextcloud, GitLab, MySQL und Portainer-Container definiert und konfiguriert. 
Die Konfiguration umfasst die Integration einer MySQL-Datenbank für GitLab.

Dienste und Konfigurationen:
mediawiki-Service:
Image: mediawiki
Ports: Der Service wird auf Port 8085 des Hosts ausgeführt und ist mit Port 80 des Containers verbunden.
Volumes: Ein Docker-Volume mediawiki_data wird verwendet, um die Daten des MediaWiki-Containers persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

nextcloud-Service:
Image: nextcloud
Ports: Der Service wird auf Port 8080 des Hosts ausgeführt und ist mit Port 80 des Containers verbunden.
Volumes: Ein Docker-Volume nextcloud_data wird verwendet, um die Daten des Nextcloud-Containers persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

gitlab-Service:
Image: gitlab/gitlab-ce
Ports: Der Service wird auf Port 4444 des Hosts ausgeführt und ist mit Port 80 des Containers verbunden.
Volumes: Ein Docker-Volume gitlab_data wird verwendet, um die Daten des GitLab-Containers persistent zu speichern.
Umgebungsvariablen:
GITLAB_OMNIBUS_CONFIG: Konfiguration von GitLab, um die MySQL-Datenbank zu verwenden.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

mysql-Service:
Image: mysql:latest
Umgebungsvariablen: Konfiguration des MySQL-Dienstes mit einem Root-Passwort.
Volumes: Ein Docker-Volume mysql_data wird verwendet, um die Daten der MySQL-Datenbank persistent zu speichern.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

portainer-Service:
Image: portainer/portainer
Ports: Der Service wird auf Port 9000 des Hosts ausgeführt und ist mit Port 9000 des Containers verbunden.
Volumes: Das Docker-Socket-Volume /var/run/docker.sock wird verwendet, um auf die Docker-Engine des Hosts zuzugreifen.
Restart: Der Service wird immer automatisch neu gestartet, falls ein Fehler auftritt.

Konfigurationsspezifika:
Für GitLab wurde eine MySQL-Datenbank integriert, um die Daten zu speichern. Die Umgebungsvariable GITLAB_OMNIBUS_CONFIG wird verwendet, um GitLab zu konfigurieren, damit es die MySQL-Datenbank verwendet.

Volumes:
Es wurden separate Docker-Volumes für jede Anwendung erstellt, um die Daten persistent zu speichern:
mediawiki_data, nextcloud_data, gitlab_data und mysql_data.
Diese Docker-Compose-Konfigurationsdatei ermöglicht das gleichzeitige Bereitstellen mehrerer Dienste, 
darunter MediaWiki, Nextcloud, GitLab mit MySQL-Integration, MySQL-Datenbank und Portainer für die Docker-Container-Verwaltung. 
Die Integration der MySQL-Datenbank ermöglicht eine effiziente Datenpersistenz und -verwaltung für den GitLab-Dienst.
