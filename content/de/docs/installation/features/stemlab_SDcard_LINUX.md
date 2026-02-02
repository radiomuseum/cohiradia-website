---
title: "stemlab_SDcard_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

## Firmware für STEMLAB vorbereiten

Bevor das STEMLAB125-XX mit COHIRADIA in Betrieb genommen werden kann, muss die SD-Karte mit Betriebssystem und Serversoftware vorbereitet werden.
Das STEMLAB wird meist mit einer SDKarte ausgeliefert, die das Betriebssystem beinhaltet. Diese allein ermöglicht aber noch nicht die Kommunikation mit der COHIRADIA-Software auf dem PC. 

**Daher bitte unbedingt eine neue SD-Karte wie folgt erstellen:** 

1. Stecken Sie eine neue SD-Karte (mindestens 8 GB) in den SD-Karten-Slot Ihres PCs (wenn vorhanden) oder in einen mit Ihrem PC verbundenen SD-Kartenleser. Sie können ggf. auch die mitgelieferte Karte überschreiben, aber die möchte man meist sicherheitshalber eher als Original aufbewahren.

2. Laden Sie das [Image-File cohiradia_STEMLAB125_v1.0.img](https://cohiradia.radiomuseum.org/download/software/cohiradia_STEMLAB125_v1.0.img) vom COHIRADIA-Softwarearchiv herunter und speichern Sie es in irgendeinem Verzeichnis.

3. schreiben Sie das Image mit einer geeigneten Software auf die SD-Karte. Unter LINUX eiget sich z.B. der [Balena Etcher](https://etcher.balena.io/#download-etcher). Es geht aber natürlich auch ganz einfach direkt auf der Kommandozeile: 
Zuerst die gemounteten SD-Karten-Partitionen auslesen:

```bash
lsblk -f
```
Diese werden z.B. als sdb1, sdb2 o.ä. gelistet. Dann die SD-Devices unmounten und das Schreiben starten:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE ist dann was Ihr lsblk listet, in meinem Beispiel sbd. Danach:

```bash
sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync
```
Nun wird die Karte beschrieben. Wenn sie fertig ist, Karte auswerfen:

```bash
sudo eject /dev/YOURSDDEVICE
```
Dann kann sie in den SD-Karten-Slot des STEMLAB eingesetzt werden und das STEMLAB sollte damit betriebsbereit sein.


**ACHTUNG: dd ist mit viel Vorsicht zu benutzen. Wenn Sie das falsche Ziel angeben, kann es passieren, dass wichtige Systemdatenträger gelöscht werden. Also bitte dreimal kontrollieren, was man tut !** 





