---
id: webspace-plesk-ssl
title: "Webspace: SSL Zertifikat erstellen"
description: Informationen, wie du eni SSL Zertifikat für deinen Webspace von ZAP-Hosting erstellen kannst - ZAP-Hosting.com Dokumentation
sidebar_label: SSL Zertifikat erstellen
services:
  - webspace
---

import InlineVoucher from '@site/src/components/InlineVoucher';

## Webseite mit SSL verschlüsseln

>Es wird vorausgesetzt das die Domain bereits auf die IP des Webspaces zeigt.

Wird eine Domain im Webspace angelegt, so ist diese am Anfang immer unverschlüsselt. 
Dies ist A im Plesk Panel zusehen: 

![image](https://user-images.githubusercontent.com/13604413/159176735-65c6494b-0cba-4e92-a6c7-c33b28b3a153.png)

Und B im Browser, beim Öffnen der Domain:

![image](https://user-images.githubusercontent.com/13604413/159176736-661b1f50-ffa2-45a8-8635-4e008d29c20a.png)
![image](https://user-images.githubusercontent.com/13604413/159176743-154bf742-e93e-4743-8a0a-0f43e46952a9.png)

Durch ein SSL Zertifikat kann eine Domain entsprechend geschützt/verschlüsselt werden.

<InlineVoucher />

## Anlegen des Zertifikats 

Schritt 1️⃣: Durch einen Doppelklick auf "SSL/TLS-Zertifikat" öffnet sich folgendes Menü:

![image](https://user-images.githubusercontent.com/13604413/159176748-32786fa1-7e69-441d-a3e3-1c8da3fbdb4a.png)

Dort kann kostenlos ein Let's Emcrypt Zertifikat angefordert werden. 

Schritt 2️⃣: Erforderliche Angaben eintragen/setzen. 
Damit das Zertifikat angefordert werden kann, müssen Angeben erfolgen. 

Es muss eine Mail Adresse angegeben werden sowie muss angehakt werden, für was das Zertifikat gültig sein soll. 
In der Regel hat jede Domain auch die Subdomain "www" aktiv, daher wird es ebenfalls ausgewählt, sofern es auch im DNS der Domain eingetragen wurde. 

![](https://user-images.githubusercontent.com/13604413/159176751-d001f779-d5be-48be-ae8b-7ef8716fe592.png)

Anschließend wird das Zertifikat mit einem Klick auf "Kostenlos nutzen" angefordert.

Schritt 3️⃣: Das Zertifikat wurde nun erstellt, dies ist oben rechts zu sehen. Zusätzlich muss jetzt die automatische Weiterleitung von HTTP zu HTTPS erfolgen, da sonst keine Verschlüsslung aufgebaut werden kann. 
Dies erfolgt mit einem Klick auf den Schieberegler bei "Von HTTP auf HTTPS umleiten" links am Rand:

![](https://user-images.githubusercontent.com/13604413/159176758-4c6cd586-64d7-42d3-a8ae-eddfb605e8d3.png)

Sofern auch Webmail genutzt wird und im DNS der Domain als Subdomain hinterlegt ist, kann dieses mit darauf angewendet werden. 
Soll es ohne Webmail geschen, so kann dies entsprechend deaktiviert werden, mit einem Klick auf die blaue Checkbox:

![](https://user-images.githubusercontent.com/13604413/159176761-64ef2d83-8c05-4610-bb4e-40a1506e25d8.png)

Ist dies erfolgt, so ist die Weiterleitung jetzt aktiv. Egal ob man die Seite mit http oder direkt HTTPS öffnet im Browser, es wird jetzt immer zu HTTPS geleitet. 

![](https://user-images.githubusercontent.com/13604413/159176764-6a3be7b8-6e0c-4ab0-8a51-bded7476c556.png)

Schritt 4️⃣: Nun kann im Browser geprüft werden, ob das Zertifikat anerkannt wurde:

Ebenfalls sollte die Zertifikat-Info, welche mit einem Klick auf das Schloss geöffnet werden kann, die Domain anzeigen.

Die Webseite ist nun korrekt geschützt/verschlüsselt. 

## Zertifikate für Subdomains 

Die gleichen Schritte sind bei einer Subdomain theoretisch ebenfalls zu befolgen. 
Jedoch gibt es auch eine einfachere Möglichkeit alle Subdomains gleichzeitig zu verschlüsseln, egal ob bereits bestehende oder welche, die erst noch neu hinzukommen. Dazu kann ein "Wildcard-Zertifikat" genutzt werden. Dies benötigt einen speziellen TXT Eintrag im DNS der Domain, kann, sobald dieser vorhanden ist, jedoch für alle Subdomains ein SSL Zertifikat ausstellen. 

Schritt 1️⃣: Es wird erneut das SSL/TLS Zertifikat Menü geöffnet. 

![](https://user-images.githubusercontent.com/13604413/159176787-2ffd121c-0ad0-44ca-bea1-185e13ac81ad.png)

Anschließend wird links oben auf "Zertifikat erneuern" geklickt. 
Nun öffnet sich das Anfragefenster von Let's Emcrypt:

![](https://user-images.githubusercontent.com/13604413/159176792-4d648b72-9903-4526-9a6e-984b3cb6a35a.png)

Dort wird nun "Wildcard-Domain schützen" ausgewählt:

![](https://user-images.githubusercontent.com/13604413/159176798-7c6fff87-f9ac-4fd8-9a54-2697c3b5575b.png)

Es wird automatisch die Subdomain "www" sowie "webmail" hinzugefügt. 
Anschließen wird wieder der Button "Kostenlos nutzen" angeklickt. 

Schritt 2️⃣: Es erscheint nun eine blaue Box mit wichtigen Informationen: 

![](https://user-images.githubusercontent.com/13604413/159176800-483c32c6-bb31-47bf-91bb-38aab2b47288.png)

Dort wird ein Domainname sowie ein Wert genannt. 
Dieser muss als TXT dauerhaft im DNS der Domain abrufbar sein, nur so kann Let's Emcrypt sicherstellen, dass die Domain echt ist und verifiziert werden kann. 

Ein Eintrag im DNS sollte so aussehen: 

![](https://user-images.githubusercontent.com/13604413/159176807-99f29bd6-3ae0-499b-a048-308752083b03.png)

>Ein DNS Eintrag kann nach der Eintragung bist zu 24 Stunden benötigen, bis dieser von der ganzen Welt aus erreichbar ist. 

Um sicherzustellen, dass der TXT Eintrag bereits aktiv ist, kann das "TXT-Lookup-SuperTool" von mxtoolbox genutzt werden: https://mxtoolbox.com/SuperTool.aspx:

![](https://user-images.githubusercontent.com/13604413/159176810-2491729f-2604-47af-aa08-525f12ea2085.png)

Sofern der eingetragene Eintrag bereits angezeigt wird, kann es in der blauen Box in Plesk bestätigt werden, mit einem Klick auf "Neu laden". 
Nun wird geprüft, ob der DNS Eintrag vorhanden ist, da dies der Fall ist, wird nach wenigen Sekunden "geschützt" bei "SSL/TLS-Platzhaltezertifikat" aka "Wildcard-Zertifikat" angezeigt: 

![](https://user-images.githubusercontent.com/13604413/159176811-32bf65ce-57cf-40c4-9c84-2f0a6fbf1cdc.png)

Wird nun eine Subdomain angelegt, ist diese bereits geschützt: 

![image](https://user-images.githubusercontent.com/13604413/159176814-75297c89-134d-4e54-a471-3baf6e7dc627.png)

Nun erfolgt der vollständige Datentransfer zur Seite verschlüsselt, fertig. 

