---
title: Installation Server Software
linkTitle: Installation Server
date: 2017-01-01
description: >
  Hier wird die Hardware von Cohiradia beschrieben.
weight: 3
---


##	Installation der Server-Software auf dem STEMLAB125-XX

Bevor das STEMLAB125-XX mit COHIRADIA in Betrieb genommen werden kann, muss die SD-Karte mit Betriebssystem und Serversoftware vorbereitet werden.
Das STEMLAB wird typischerweise mit einer SDKarte ausgeliefert, die das Betriebssystem (eine UBUNTU-Version) beinhaltet. Diese allein ermöglicht aber noch nicht die Kommunikation mit der COHIRADIA-Software auf dem PC. 

**Daher bitte unbedingt eine neue SD-Karte wie folgt erstellen:** 

1. Stecken Sie eine neue SD-Karte (8 GB sind ausreichend, größere Karten funktionieren natürlich ebenso) in den SD-Karten-Slot Ihres PCs (wenn vorhanden) oder in einen mit Ihrem PC verbundenen SD-Kartenleser. Sie können ggf. auch die mitgelieferte Karte überschreiben, aber die möchte man meist sicherheitshalber eher als Original aufbewahren.

2. Laden Sie das [Image-File cohiradia_STEMLAB125_v1.0.img](https://cohiradia.radiomuseum.org/download/software/cohiradia_STEMLAB125_v1.0.img) vom COHIRADIA-Softwarearchiv herunter und speichern Sie es in irgendeinem Verzeichnis.

3. schreiben Sie das Image mit einer geeigneten Software auf die SD-Karte. Unter Windows eigen sich z.B. [Win32Diskimager](https://win32diskimager.org/) oder der [Balena Etcher](https://etcher.balena.io/#download-etcher). Unter LINUX geht es direkt auf der Kommandozeile: 
Zuerst mit  `lsblk -f` die gemounteten SD-Karten-Partitionen auslesen. Diese werden z.B. als sdb1, sdb2 o.ä. gelistet. Dann die SD-Devices unmounten und das Schreiben starten
`sudo umount /dev/YOURSDDEVICE*`. YOURSDDEVICE ist dann was Ihr lsblk listet, in meinem Beispiel sbd. Danach:
`sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync`
**ACHTUNG: dd ist mit viel Vorsicht zu benutzen. Wenn Sie das falsche Ziel angeben, kann es passieren, dass wichtige Systemdatenträger gelöscht werden. Also bitte dreimal kontrollieren, was man tut !** 

Anmerkung: Es gibt noch eine früher benutzte [alternative Installationsmethode](https://www.radiomuseum.org/cohiradia/SDKARTE_method2.html), die aber nicht mehr als erste Wahl empfohlen wird.

4. Werfen Sie die SD-Karte aus und stecken Sie sie in den SD-Karten-Slot des STEMLAB. Nun muss man die IP-Adresse des STEMLAB ermitteln. Dafür gibt es ebenfalls unterschiedliche Möglichkeiten. Am einfachsten ist es, das STEMLAB per Ethernet-Kabel mit dem PC zu verbinden und danach die Versorgungsspannung einzuschalten. Das STEMLAB bootet und man sieht diverse LEDs flackern, bis das Blinken der roten 'Heartbeat'-LED beginnt. **ACHTUNG: Unter Windows kann es leicht passieren, dass die Verbindung über Ethernet nicht funktioniert, wenn das WLAN eingeschaltet ist. Falls die folgenden Schritte also nicht funktionieren, bitte einfach mal das WLAN am PC deaktivieren**

5. Danach einen Webbrowser (z.B. Mozilla Firefox) starten. Auf dem Webbrowser im Adressfeld

    `http://rp-######.local`

eingeben, wobei ###### für die MAC-Adresse steht (z.B. rp-f03e25.local). Die MAC-Adresse ist auf dem Ethernet-Stecker jedes STEMLAB aufgedruckt.

6. Warten bis die STEMLAB-Apps im Webbrowser geladen werden (das kann manchmal etwas dauern). <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> Der Anblick sollte etwa wie in der nebenstehenden Abbildung sein. Man sieht eine Reihe von Icons, mit denen man verschiedene Funktionen auf dem STEMLAB aufrufen kann. Für COHIRADIA ist lediglich das Icon 'System' relevant.

7. Danach den Folder „System“ durch Anklicken öffnen und dort die App „Network Manager“ aufrufen. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In diesem Manager kann nun die vom Router vergebene IP Adresse ausgelesen werden.                           

&nbsp;

&nbsp;

<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;

Diese Adresse benötigen Sie für den Betrieb der COHIRADIA-Apps, denn sie muss bei der ersten Verwendung eingetragen werden.

[Diese alternative Methode](https://redpitaya.readthedocs.io/en/latest/developerGuide/software/console/console/console.html) wird auf der Red-Pitaya-Doku-Page beschrieben, sie funktioniert über ein Terminal und eine zusätzliche USB-Konsolenverbindung. Empfohlen nur für IT-Geübte.


Danach ist das System für den Gebrauch im Sinne von COHIRADIA konfiguriert.