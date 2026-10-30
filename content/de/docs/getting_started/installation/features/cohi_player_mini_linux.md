---
title: "Cohi-Player_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

## COHI-Player als Python-Version für LINUX installieren

Sie können den COHI-Player aus dem [Quellcode auf GitHub](https://github.com/CPG-Archive/COHI-Player-Universal) installieren. Laden Sie dazu das Release herunter bzw. klonen Sie das Repository in ein Verzeichnis Ihrer Wahl und befolgen Sie die Installationsanleitung im Abschnitt „Installation“ der [README-Datei](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md). Sie umfasst im Wesentlichen

* die Installation einiger Systempakete (u. a. PyQt5, ffmpeg und – für den fl2k-Dongle – osmo-fl2k),
* die Installation der Python-Pakete aus `requirements.txt` und
* das Kompilieren der C++-Tools mit `make` (nötig für die Webradio-Stream-Betriebsarten und den fl2k-Dongle).

Gestartet wird das Programm im Programmverzeichnis mit

```bash
python3 cohi_player_main.py
```

Die Leistungsfähigkeit auf einem PC hängt stark von der eingebauten CPU ab.

**Bei speziellen Fragen zum COHI-Player wenden Sie sich bitte an Claus Peter Gallenmiller: [E-Mail](mailto:cpg-radio@gmx.de).**
