---
title: Raspberry Pi (mindestens V4, 4GB) + OSMO fl2k-Dongle
date: 2026-02-04
weight: 10
_build:
  list: never
  render: always
description: >
    Auswahl für < 300€, max. SNR bei 29 gleich starken Trägern 40dB, Bandbreite begrenzt auf LW, MW und 49m SW
---

**alternative Möglichkeiten bei dieser Perfomance:**

aktuell keine

**Vorteile:**

* mittlere Preislage
* unkompliziertes Setup
* kompakteste Lösung
* standalone
* automatische Wiedergabe nach dem Hochfahren bei Verwendung des COHI-Player-Mini

**Nachteile:**

* nur 8 bit Auflösung, daher SNR begrenzt, aber ausreichend für die meisten LW und MW-Bänder sowie KW 49m
* Datenrate durch USB-Port begrenzt; max. nutzbare Frequenz ist je nach Betriebssystem beschränkt, nähere Details siehe ['hier']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})
* höhere Rechenleistung auf dem PC gefordert als bei FPGA-gestützten Systemen
* nur USB/VGA-Dongles mit Fresco-Chipset unterstützt, Verfügbarkeit wegen Auslaufen der Herstellung begrenzt, Zukunft ungewiss.

**Software-Unterstützung:**

COHIWizard, COHI-Mini-Player (projected) und Lösungen anderer Communities wie radio-bastler.de per GNU-Radio Support

Technische Evaluierung siehe ['SNR-Messungen']({{< relref "/docs/documentation/Testberichte/snr_messungen/_index.md" >}}) und ['OSMO-fl2k-Frequenzabdeckung']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})
