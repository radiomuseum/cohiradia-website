---
title: Raspberry-Pi + fl2k-Dongle + Linux + COHIWizard Python
linkTitle: Raspberry-Pi / fl2k-Dongle / Linux / COHIWizard Python
date: 2026-01-28
weight: 14
nav_exclude: true
combo:
  computer: raspberry-pi
  wandler: fl2k-dongle
  os: linux
  software: cohiwizard-python
description: >
  Installationsanleitung für: Raspberry-Pi mit fl2k-Dongle Signalwandler unter Linux mit COHIWizard Python
---

## Installationsanleitung

Diese Anleitung führt dich durch die Installation für folgende Kombination:
- **Control-Computer:** Raspberry-Pi
- **Signalwandler:** fl2k-Dongle
- **Betriebssystem:** Linux
- **Software:** COHIWizard Python

### Schritt 1: Voraussetzungen

- Raspberry-Pi 3B+ oder neuer (empfohlen: Pi 4)
- Raspberry-Pi OS (Bullseye oder neuer)
- fl2k-Dongle USB Device
- Python 3.8 oder neuer

### Schritt 2: System aktualisieren

```bash
sudo apt-get update
sudo apt-get upgrade
```

### Schritt 3: fl2k-Dongle Unterstützung installieren

```bash
sudo apt-get install libusb-1.0-0-dev
pip3 install pyusb
```

### Schritt 4: COHIWizard klonen und installieren

```bash
git clone https://github.com/radiomuseum/cohiradia.git
cd cohiradia
pip3 install -r requirements.txt
```

### Schritt 5: Berechtigungen für USB-Device

```bash
sudo usermod -a -G plugdev $USER
```

### Schritt 6: COHIWizard starten

```bash
python3 cohiwizard.py
```

### Nächste Schritte

Nach der erfolgreichen Installation kannst du mit der Konfiguration beginnen.
