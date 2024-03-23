# Docker Compose ZP by Claudio, Florian und Terry
Dieses Projekt stellt verschiedene Docker-Container für MediaWiki, Nextcloud, GitLab und Portainer bereit. Diese Container können verwendet werden, um eine firmeninterne MediaWiki-Instanz, eine Nextcloud-Dateifreigabe und Collaboration-Plattform, sowie eine GitLab-Instanz für die Verwaltung von Quellcode einzurichten. Portainer wird ebenfalls bereitgestellt, um die Docker-Container zu überwachen und zu verwalten.

## Verwendung
Um dieses Projekt zu verwenden, führen Sie die folgenden Schritte aus:
1. Klonen Sie dieses Repository auf Ihren lokalen Computer.
2. Navigieren Sie zum Projektverzeichnis.
3. Starten Sie die Docker-Container
4. npm/ yarn run dev bei dem package.json
5. Warten Sie, bis die Container gestartet wurden und greifen Sie dann über die entsprechenden Ports auf die Dienste zu:
        MediaWiki: http://localhost:8085
        Nextcloud: http://localhost:8080
        GitLab: http://localhost:4444
        Portainer: http://localhost:9000
        Webseite: http://localhost:300
6. Konfiguration
Die Konfiguration der Dienste erfolgt hauptsächlich über Umgebungsvariablen in der docker-compose.yml-Datei. Stellen Sie sicher, dass Sie die erforderlichen Umgebungsvariablen für die MySQL-Datenbanken von Nextcloud und GitLab festlegen, bevor Sie die Container starten.

Beitrag:
Beiträge zu diesem Projekt sind willkommen! Wenn Sie Probleme melden, Verbesserungsvorschläge machen oder neue Funktionen hinzufügen möchten, erstellen Sie bitte eine Issue oder eine Pull-Anfrage in diesem Repository.

Erstellt wurde dieses Repo über IntelliJ Ultimate auf einem Windows 11 Pro Gerät mit der Docker Desktop App.
