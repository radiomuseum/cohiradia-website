---
title: Raspberry-Pi + STEMLAB + Linux + COHI-Player Mini
linkTitle: Raspberry-Pi / STEMLAB / Linux / COHI-Player Mini
date: 2026-01-28
weight: 16
nav_exclude: true
_build:
  list: never
  render: always
description: >
  Installationsanleitung für: Raspberry-Pi mit STEMLAB Signalwandler unter Linux mit COHI-Player Mini
---

## Installationsanleitung

Diese Anleitung führt dich durch die Installation für folgende Kombination:
- **Control-Computer:** Raspberry-Pi
- **Signalwandler:** STEMLAB
- **Betriebssystem:** Linux
- **Software:** COHI Player Mini

### Schritt 1: Voraussetzungen

- Raspberry-Pi 4 oder neuer
- Raspberry-Pi OS (Bullseye oder neuer)
- STEMLAB Board mit USB-Verbindung
- Python 3.8 oder neuer

### Schritt 2: System aktualisieren

```bash
sudo apt-get update
sudo apt-get upgrade
```

### Schritt 3: Python und Dependencies

```bash
sudo apt-get install python3-pip python3-dev
pip3 install --upgrade pip
```

### Schritt 4: COHIWizard klonen und installieren

```bash
git clone https://github.com/radiomuseum/cohiradia.git
cd cohiradia
pip3 install -r requirements.txt
```

### Schritt 5: COHIWizard starten

```bash
python3 cohiwizard.py
```

### Performance-Tipps für Raspberry-Pi

- Verwende eine schnelle microSD Karte (Class 10 oder UHS-I)
- Erhöhe die GPU-Memory in raspi-config falls nötig

### Nächste Schritte

Nach der erfolgreichen Installation kannst du mit der Konfiguration beginnen.
