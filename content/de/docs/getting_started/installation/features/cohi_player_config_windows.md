---
title: "cohi_player_config_windows"
nav_exclude: true
_build:
  list: never
  render: always
---

## Konfiguration des COHI-Players

Die Grundeinstellungen – **Ausgabe-Hardware** (STEMLAB oder fl2k) und **Displaygröße** – lassen sich am einfachsten mit dem grafischen Konfigurationswerkzeug einstellen. Starten Sie es im Programmverzeichnis des COHI-Players:

```bash
python3 cohi_config_gui.py
```

Alternativ gibt es eine Terminal-Version mit nummerierten Menüs, in der zusätzlich die Sprache (Deutsch/Englisch) gewählt werden kann:

```bash
python3 cohi_config_setup.py
```

**Betriebsart:** Wählen Sie unter Windows die Betriebsart **COHI-Player**. Die Betriebsarten COHI-Stream und COHI-Player+Stream funktionieren unter Windows derzeit nicht.

Alle weiteren Einstellungen (z. B. die Verzeichnisse mit den wav-Aufzeichnungen, die Sprache oder das Herunterfahren des Computers beim Beenden) stehen in der Datei `config_sdr.yaml` im Programmverzeichnis und sind dort kommentiert. Änderungen werden nach einem Neustart des Programms wirksam.

Ein STEMLAB wird im lokalen Netzwerk automatisch gefunden; alternativ kann seine IP-Adresse in `config_sdr.yaml` eingetragen werden.

Details zu allen Einstellungen, zur Bedienung und zur Fehlersuche finden Sie in der [Bedienungsanleitung (README)](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md).
