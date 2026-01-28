---
title: PC + STEMLAB + Linux + COHIWizard Python
linkTitle: PC / STEMLAB / Linux / COHIWizard Python
date: 2026-01-28
weight: 11
_build:
  list: never
  render: always
description: >
  Installationsanleitung für: PC mit STEMLAB Signalwandler unter Linux mit COHIWizard Python
---

## Installationsanleitung

Diese Anleitung führt dich durch die Installation für folgende Kombination:
- **Control-Computer:** PC
- **Signalwandler:** STEMLAB
- **Betriebssystem:** Linux
- **Software:** COHIWizard Python

### Schritt 1: Voraussetzungen

- Linux System (Ubuntu 20.04+, Debian 11+, etc.)
- Python 3.8 oder neuer
- STEMLAB Board mit USB-Verbindung

### Schritt 2: Abhängigkeiten installieren

```bash
sudo apt-get install python3-pip python3-dev
pip3 install --upgrade pip
```

### Schritt 3: COHIWizard Python klonen oder herunterladen

```bash
git clone https://github.com/radiomuseum/cohiradia.git
cd cohiradia
```

### Schritt 4: Dependencies installieren

```bash
pip3 install -r requirements.txt
```

### Schritt 5: COHIWizard starten

```bash
python3 cohiwizard.py
```

### Nächste Schritte

Nach der erfolgreichen Installation kannst du mit der Konfiguration beginnen.
