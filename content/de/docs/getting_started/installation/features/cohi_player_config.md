---
title: "cohi_player_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## Konfiguration des COHI-Players

Die drei Grundeinstellungen – **Ausgabe-Hardware** (STEMLAB oder fl2k), **Betriebsart** (COHI-Player, COHI-Stream oder COHI-Player+Stream) und **Displaygröße** – lassen sich am einfachsten mit dem grafischen Konfigurationswerkzeug einstellen. Es ist touch-tauglich und auch auf dem 3,5"-Display bedienbar. Starten Sie es im Programmverzeichnis des COHI-Players:

```bash
python3 cohi_config_gui.py
```

Alternativ gibt es eine Terminal-Version mit nummerierten Menüs, in der zusätzlich die Sprache (Deutsch/Englisch) gewählt werden kann:

```bash
python3 cohi_config_setup.py
```

Alle weiteren Einstellungen (z. B. die Verzeichnisse mit den wav-Aufzeichnungen, die Sprache oder das Herunterfahren des Computers beim Beenden) stehen in der Datei `config_sdr.yaml` im Programmverzeichnis und sind dort kommentiert. Änderungen werden nach einem Neustart des Programms wirksam. Die Senderliste für die Webradio-Streams kann direkt im Programm geladen, bearbeitet und gespeichert werden.

Ein STEMLAB wird im lokalen Netzwerk automatisch gefunden; alternativ kann seine IP-Adresse in `config_sdr.yaml` eingetragen werden.

Details zu allen Einstellungen, zur Bedienung und zur Fehlersuche finden Sie in der [Bedienungsanleitung (README)](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md).
