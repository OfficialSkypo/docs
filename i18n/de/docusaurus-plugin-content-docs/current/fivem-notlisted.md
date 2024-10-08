---
id: fivem-notlisted
title: "FiveM: Server erscheint nicht in der Serverliste"
description: Informationen, was du tun kannst, wenn dein FiveM-Server von ZAP-Hosting nicht auf der Serverliste erscheint - ZAP-Hosting.com Dokumentation
sidebar_label: Server nicht in Serverliste
services:
  - gameserver
---

import InlineVoucher from '@site/src/components/InlineVoucher';

## Einführung

Wenn der Server nicht in der Serverliste angezeigt wird, kann dies mehrere Gründe haben, falls diese Anleitung das Problem nicht behebt, würden wir dich bitten, unseren [Support](https://zap-hosting.com/en/customer/support/) zu kontaktieren.

<InlineVoucher />

## Konfigurationsfehler

Oftmals sind es simple Konfigurationsfehler, welches dieses Problem verursacht, zuerst sollten wir prüfen, ob unser Server das Listing deaktiviert hat, hierzu prüfen wir die `sv_master1` Zeile:

![image](https://screensaver01.zap-hosting.com/index.php/s/mMb94ffHqgZwr29/preview)

:::info
Diese Zeile sollte **immer** mit einem # auskommentiert werden, wenn dies nicht der Fall ist, wird der Server nicht gelistet.
:::


Ebenfalls sollte der Servername (`sv_hostname`) geprüft werden:

![image](https://screensaver01.zap-hosting.com/index.php/s/kXZCDckKdnaid4a/preview)

In diesem Fall fehlt das Anführungszeichen am Ende der Zeile, bei manchen Servernamen kann es auch durch Formatierung Probleme geben, wir würden in diesem Fall empfehlen, z. B. [DE], Sonderzeichen wie ä, ü, ö zu entfernen.


## Problematische Ressourcen

Es können auch Ressourcen verhindern, dass der Server gelistet wurde, in diesem Fall empfehlen wir zuletzt installierte Ressourcen wieder zu entfernen und danach den Server für ~1h online zu lassen, in den meisten Fällen sollte er dann wieder angezeigt werden.


## Neuinstallation

Falls nichts davon Abhilfe bringt, ist eine Neuinstallation empfehlenswert, damit werden alle Serverdateien auf Standard zurückgesetzt.

:::info
Gehe sicher, dass vor der Neuinstallation ein Backup erstellt wird, ansonsten werden die Daten auf dem Server verloren gehen.
:::
