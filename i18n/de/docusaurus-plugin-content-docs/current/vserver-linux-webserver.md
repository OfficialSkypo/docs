---
id: vserver-linux-webserver
title: "vServer: Installation eines Webservers"
description: Informationen wie du Nginx und Apache Webserver auf deinen Linx vServer von ZAP-Hosting installieren kannst - ZAP-Hosting.com Dokumentation
sidebar_label: Webserver installieren
services:
  - vserver
---

import InlineVoucher from '@site/src/components/InlineVoucher';

## Einführung

Nginx und Apache sind beliebte Webserver, die verwendet werden, um Webseiten an den Browser eines Benutzers zu übermitteln. Im Folgenden zeigen wir dir, wie du einen der Dienste auf deinem System installieren kannst. 

<InlineVoucher />

## Vorbereitung

Bevor die eigentliche Installation eines Webservers begonnen werden kann, muss sichergestellt werden, dass das System auf dem neusten Stand ist. Dafür verbinden wir uns per SSH mit dem Server. Falls du nicht weißt, was SSH ist und wie du es verwendest, dann schaue dir folgende Anleitung an: [Erstzugriff (SSH)](vserver-linux-ssh.md)

Dort angekommen kann das System je nach Betriebssystem mit dem folgenden Befehl aktualisiert werden:

```
// Debian
sudo apt-get update

// Ubuntu
sudo apt update

// CentOS
sudo yum update

// OpenSUSE
sudo zypper update

// Fedora
sudo dnf upgrade --refresh
```



## Installation

Nachdem die Vorbereitung abgeschlossen wurde, kann nun mit der Installation des Webservers begonnen werden. Je nach Betriebssystem und Webserver müssen dafür folgende Befehle ausgeführt werden:



### Apache

```
// Debian
sudo apt install apache2

// Ubuntu
sudo apt install apache2

// CentOS
sudo yum install httpd

// OpenSUSE
sudo zypper install httpd

// Fedora
sudo dnf install httpd
```

Nach dem Installieren des Webservers können die Dateien deiner Website hochgeladen werden. Verbinde dich dazu per FTP/SFTP mit deinem Server, navigiere in das folgende Verzeichnis und lade die Dateien hoch.

```
/var/www/html/
```



### Nginx

```
// Debian
sudo apt install nginx

// Ubuntu
sudo apt install nginx

// CentOS
sudo yum install nginx

// OpenSUSE
sudo zypper install nginx

// Fedora
sudo dnf install nginx
```

Nach dem Installieren des Webservers können die Dateien deiner Website hochgeladen werden. Verbinde dich dazu per FTP/SFTP mit deinem Server, navigiere in das folgende Verzeichnis und lade die Dateien hoch.

```
/usr/share/nginx/html
```



## Version-Check

Nachdem die Installation abgeschlossen wurde, kannst du mit den Befehlen  `apache2 -v` (Apache) und `nginx -v` (Nginx)  prüfen, ob die Installation erfolgreich gewesen ist. Die Ausgabe sollte im etwa wie im Folgenden aussehen:



### Apache

```
apache2 -v
Server version: Apache/2.4.41 (Ubuntu)
Server built:   XXXX-XX-XXTXX:XX:XX
```



### Nginx

```
nginx -V
nginx version: nginx/1.2.3
...
```


## Abschluss

Glückwunsch, du hast deinen gewünschten Webserver erfolgreich installiert und konfiguriert! Solltest du noch weitere Fragen oder Probleme haben, dann wende dich gerne an unser Support-Team, welches dir jeden Tag zur Verfügung steht! 