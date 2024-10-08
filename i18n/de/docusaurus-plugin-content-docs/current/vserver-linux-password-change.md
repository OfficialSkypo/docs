---
id: vserver-linux-password-change
title: "vServer: Root Passwort für Linux-Server ändern"
description: Informationen, wie du das Root-Passwort für deinen Linux vServer von ZAP-Hosting ändern kannst - ZAP-Hosting.com Dokumentation
sidebar_label: Passwort ändern
services:
  - vserver
---

import InlineVoucher from '@site/src/components/InlineVoucher';

<InlineVoucher />

## Webinterface

Das Passwort kann über unser Webinterface bei dem jeweiligen Server geändert werden. 
Öffne dazu die Seite „Zugang und Sicherheit“, diese findet man Links im Menü

![](https://screensaver01.zap-hosting.com/index.php/s/N7NmZjHq2baYxSk/preview)

Dort findet man das Eingabefeld „Root Password“. 
Dort kann man ein neues Wunschpasswort eintragen.

>Bitte beachte das dies mindestens 8 Zeichen lang sein muss sowie aus Klein und Groß Buchstaben (a-z/A-Z), Zahlen (1-9) und Sonderzeichen (!@=#$%&-?_;:.,) bestehen muss. 
Sollte dies nicht der Fall sein, wird es bei dem Server nicht gesetzt. 

![](https://screensaver01.zap-hosting.com/index.php/s/snHG3maY9nEfoA5/preview)

Nun bestätigt das System, dass das Passwort geändert wurde. 

Das Passwort kann ab jetzt noch 3 Stunden in unserem Webinterface eingesehen werden, danach löschen wir dieses aus Sicherheitsgründen zur Einsicht raus. Um das Passwort einzusehen, genügt ein Klick auf das Auge bei "Passwort" auf der Seite "Login und Sicherheit". 

![](https://screensaver01.zap-hosting.com/index.php/s/PybrA4Wz4CTJdHo/preview)

Anschließend öffnet sich ein Pop-up wo das Passwort angezeigt wird.



## Server Konsole

Das Passwort kann auch über die Server Console geändert werden, dabei ist es egal, ob man diese via Putty erreicht oder z. B. via VNC/Serial.
:::info
Wichtig: Diese Option funktioniert nur, wenn noch Zugriff zum Server besteht, sprich man noch auf die Konsole verbinden sowie anmelden kann. 
:::

Ist man in der Konsole angemeldet, kann über den Befehl "passwd" das Passwort geändert werden. 
Nachdem man diesen Befehl "abgesendet" hat, mit der Taste "Enter" wird man aufgefordert sein neues Passwort einzugeben. 
Dies geschieht "Unsichtbar"

Anschließend muss man das Passwort erneut zur Bestätigung eingeben werden. 
Ist dies gemacht und das Passwort stimmte mit der ersten Eingabe überein, so bestätigt die Konsole die Änderung. 

Stimmen die beiden Eingaben nicht überein, so wird die Konsole den Vorgang beenden und man muss erneut den Befehl "passwd" eingeben. 

:::info
Wichtig: Ändert man das Password via Konsole, kann es nicht für 3 Stunden in unserem Webinterface unter Zugang und Sicherheit angezeigt werden. 
:::
