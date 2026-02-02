---
title: "stemlab_SDcard_WINDOWS"
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

3. schreiben Sie das Image mit einer geeigneten Software auf die SD-Karte. Unter Windows eigen sich z.B. [Win32Diskimager](https://win32diskimager.org/) oder der [Balena Etcher](https://etcher.balena.io/#download-etcher). 


Danach werfen Sie die Karte aus und stecken sie in den SD-Karten-Slot des STEMLAB. Das STEMLAB sollte damit betriebsbereit sein.


