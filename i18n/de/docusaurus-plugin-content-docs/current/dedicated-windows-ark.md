---
id: dedicated-windows-ark
title: "Dedicated Server: ARK Survival Evolved Dedicated Server Setup"
description: Informationen zum Einrichten eines ARK Survival Evolved Dedicated Server auf einem Dedicated Server - ZAP-Hosting.com Dokumentation
sidebar_label: ARK Survival Evolved Dedicated Server Setup
services:
  - dedicated
---

import YouTube from '@site/src/components/YouTube/YouTube';
import InlineVoucher from '@site/src/components/InlineVoucher';

## Einführung

Du hast einen Windows Dedicated Server und möchtest darauf unter anderem Gameserver installieren? Beispielsweise einen ARK: Survival Evolved Dedicated Server? Dann bist du hier genau richtig! Im folgenden werden wir dir Schritt für Schritt erklären, wie du solch einen Dienst auf deinem Server installieren kannst. Verbinde dich für die Einrichtung deines ARK: Survival Evolved Dedicated Server mit deinem vServer oder Rootserver per RDP. Solltest du noch nicht wissen, wie du dich per RDP mit deinem Server verbinden kannst, dann empfehlen wir einen Blick in die [Erstzugang (RDP)](vserver-windows-userdp.md) Anleitung zu werfen. 

<YouTube videoId="YOz_SqsUkg4" imageSrc="https://screensaver01.zap-hosting.com/index.php/s/3nPFfc7n9g9Lnm9/preview" title="ARK: Survival Evolved Dedicated Server Setup on Windows VPS" description="Hast du das Gefühl, dass du etwas besser verstehst, wenn du es in Aktion siehst? Wir haben etwas für dich! Tauche ab in unser Video, welches alles für dich zusammenfasst. Egal, ob du es eilig hast oder einfach nur Informationen auf möglichst verständliche Art und Weise aufnehmen möchtest!"/>

<InlineVoucher />

## Vorbereitung

Für die Einrichtung eines ARK Servers wird die SteamCMD benötigt. Die SteamCMD ist die **Kommandozeilen-Edition des Steam-Clients**. Über dieses Tool können schnell und einfach die Dedicated-Server-Anwendungen beliebter Steam-Games heruntergeladen werden. Die SteamCMD findest du auf der offiziellen Valve Entwickler Webseite: https://developer.valvesoftware.com/wiki/SteamCMD 

Im Anschluss erfolgt der Download. Dieser beinhaltet die **steamcmd.zip** Datei, welche zunächst entpackt werden muss. Erstelle dafür am besten einen separaten Ordner, wo die Datei dann entpackt wird. Als Resultat solltest du nun die **steamcmd.exe** sehen. Führe diese aus und warte, bis der Installationsprozess abgeschlossen ist. 

![image](https://screensaver01.zap-hosting.com/index.php/s/D3mzcgLEWxHQyNy/preview)

Sobald die Meldung **Loading Steam API... OK** angezeigt wird, wurde der Vorgang erfolgreich abgeschlossen und es kann mit der Installation des ARK Servers begonnen werden. 



## Installation

Nach der Installation solltest du die Möglichkeit haben, Befehle in der **Steam Kommandozeile (steamcmd.exe)** auszuführen. Dort ist nun der Login notwendig. Diesen führen wir über den **anonymous** Benutzer durch. Führe dafür folgenden Befehl durch: `login anonymous`

Als nächstes erfolgt die Installation. Diese wird mit dem `app_update 376030` Befehl durchgeführt. Die App ID **376030** steht in dem Fall für die **ARK: Survival Evolved Dedicated Server** Applikation. 

![image](https://screensaver01.zap-hosting.com/index.php/s/xXfJZMaSJHqWcgZ/preview)



>Bitte unterbreche den Vorgang nicht, bevor er abgeschlossen ist, um Fehler zu vermeiden. Es kann einen Moment dauern, aber es lohnt sich, geduldig zu sein! :)



Navigiere nun in das Verzeichnis, wo du die Installation durchgeführt hast, und gehe dort in das folgende Unterverzeichnis: **../steamapps/common/Ark Survival Evolved Dedicated Server/ShooterGame/Binaries/Win64**

Dort muss als nächstes die Startdatei angelegt werden, welche zum Ausführen der Server Software benötigt wird. Erstelle dafür eine Datei mit dem folgenden Namen: start-ark.bat

:::info
Bitte stelle sicher, dass du die Dateiendungen anzeigen Option aktiv hast, damit auch die richtige Dateiendung verwendet wird. 
:::

Öffne diese Datei im Anschluss, füge den folgenden Inhalt hinzu und speichere die neu hinzugefügten Veränderung:

```
start ShooterGameServer.exe TheIsland?listen?SessionName=<server_name>?ServerPassword=<join_password>?ServerAdminPassword=<admin_password>?Port=<port>?QueryPort=<query_port>?MaxPlayers=<max_players>
exit
```



Damit der Server auch extern sichtbar und erreichbar ist, müssen die verwendeten Server Ports in der Firewall freigeschaltet/weitergeleitet werden. Öffne dazu die Windows Firewall Einstellungen. 

![image](https://screensaver01.zap-hosting.com/index.php/s/8tfXEBdFzZQFRdL/preview)



In den Einstellungen müssen nun weitere Regeln angelegt werden. Klicke dazu jeweils, wie im Folgenden beschrieben, auf die eingehenden und ausgehenden Regeln und füge diese für folgende Protokolle und Ports hinzu:

- TCP eingehend und ausgehend: 27020
- UDP eingehend und ausgehend: 27015
- UDP eingehend und ausgehend: 7777-7778


## Konfiguration

Die eigentliche Einrichtung ist damit bereits abgeschlossen. Weitere Änderungen bezüglich der Konfiguration kannst du über die **DefaultGameUserSettings.ini** und **Gameusersettings.ini** Konfigurationsdateien vornehmen. Dort hast du die Möglichkeit den Server Name, Server Passwort, Server Admin Passwort und viele weitere Optionen vorzunehmen. Navigiere dazu in die folgenden Verzeichnisse: 

```
../steamapps/common/Ark Survival Evolved Dedicated Server/ShooterGame/Config/
../steamapps/common/Ark Survival Evolved Dedicated Server/ShooterGame/Saved/Config/WindowsServer/
```


## Spielen

Zum Abschluss der Einrichtung kannst du nun den Server starten, indem du die zuvor erstellte **start-ark.bat** Datei ausführst. Hierdurch sollte sich die Konsole des Servers öffnen und der Startprozess beginnen. Wenn alles wie erwartet verläuft, sollte der Server nach dem erfolgreichen Start in der Liste der Server sichtbar sein.

![image](https://screensaver01.zap-hosting.com/index.php/s/MWpRedqsnq3KC5L/preview)
