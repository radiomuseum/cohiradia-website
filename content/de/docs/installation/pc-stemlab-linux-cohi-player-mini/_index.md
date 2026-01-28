---
title: PC + STEMLAB + Linux + COHI-Player Mini
linkTitle: PC / STEMLAB / Linux / COHI-Player Mini
date: 2026-01-28
weight: 15
nav_exclude: true
combo:
  computer: pc
  wandler: stemlab
  os: linux
  software: cohi-player-mini
description: >
  Installationsanleitung für: PC mit STEMLAB Signalwandler unter Linux mit COHI-Player Mini
---

## Installationsanleitung

Diese Anleitung führt dich durch die Installation für folgende Kombination:
- **Control-Computer:** PC
- **Signalwandler:** STEMLAB
- **Betriebssystem:** Linux
- **Software:** COHI-Player Mini

### Schritt 1: Voraussetzungen

- Linux System (Ubuntu 20.04+, Debian 11+, etc.)
- STEMLAB Board mit USB-Verbindung
- Python 3.8 oder neuer (für COHI-Player Mini)

### Schritt 2: Abhängigkeiten installieren

```bash
sudo apt-get install python3-pip python3-dev
pip3 install --upgrade pip
```

### Schritt 3: COHI-Player Mini herunterladen

```bash
git clone https://github.com/radiomuseum/cohi-player-mini.git
cd cohi-player-mini
```

### Schritt 4: Dependencies installieren

```bash
pip3 install -r requirements.txt
```

### Schritt 5: Konfigurieren und starten

```bash
python3 player.py
```

### Nächste Schritte

Nach der erfolgreichen Installation kannst du mit der Konfiguration beginnen.
