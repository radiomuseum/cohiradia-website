---
title: mid cost, low SNR, only MW and LW
date: 2026-02-04
weight: 10
_build:
  list: never
  render: always
description: >
    Auswahl für < 300€, SNR bei 12 gleich starken Trägern max 40dB, Bandbreite begrenzt auf LW, MW
---

**Möglichkeiten:**

Raspberry Pi (mindestens V4, 4GB) + OSMO fl2k-Dongle

**Vorteile:**

* mittlere Preislage
* unkompliziertes Setup
* kompakteste Lösung
* standalone

**Nachteile:**

* nur 8 bit Auflösung, daher SNR sehr begrenzt, aber ausreichend für die meisten LW und MW-Bänder
* Datenrate durch USB-Port begrenzt --> höchste Frequenz beschränkt auf typ. 5 kHz, kann auch höher sein, ist aber nicht garantiert
* höhere Rechenleistung auf dem PC gefordert als bei FPGA-gestützten Systemen
* nur USB/VGA-Dongles mit Fresco-Chipset unterstützt, Verfügbarkeit wegen Auslaufen der Herstellung begrenzt, Zukunft ungewiss.

Unterstützung durch den COHIWizard, COHI-Mini-Player (projected) und Lösungen anderer Communities wie radio-bastler.de per GNU-Radio Support

Technische Evaluierung siehe TODO CONTENT STILL LACKING
