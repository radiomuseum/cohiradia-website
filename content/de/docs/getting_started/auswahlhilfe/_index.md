---
title: Auswahlhilfe
linkTitle: Auswahlhilfe
date: 2026-02-04
weight: 1
nav_exclude: true
description: >
  Auswahlhilfe mit intelligenter Auswahl
---

## Gundsätzliches

Diese Seite soll das rasche Zusammenstellen der für Sie geeigneten Komponenten ermöglichen. Der unten eingebaute Konfigurator ermöglicht es, je nach gewünschtem Steuercomputer für eine bestimmte Preiskategorie zu ermitteln, welcher Signalwandler für die gewünschten Anforderungen an SNR und abspielbare AM-Bänder verfügbar ist. 

Die gelisteten Signalwandler sind alle mit Transmit-Ausgang und schnelle Digital-Analogwandlern sowie entsprechender Firmware-Unterstützung ausgestattet. Breitbandige Aufzeichnung von AM-Signalen direkt von einer Antenne wird hingegen nicht von allen Komponenten unterstützt. Dafür gibt es etliche kommerzielle SDRs, die allerdings häufig wiederum über keinen Transmit-Ausgang verfügen. Diese sind daher nicht Gegenstand dieser Übersicht.

Anmerkung: Wenn ein PC als Steuercomputer benutzt wird, so wird er nicht in die Preisabschätzung einbezogen, da er meist ohnehin vohanden ist. Sollte dies nicht der Fall sein, sind seine Anschaffungskosten hinzuzurechnen. Wenn man eine Stand-alone-Version möchte, die ohne PC auskommt, so wird ein Single-Board-Computer, aktuell der Raspberry-Pi, eingesetzt.

Die SNR-Angaben beziehen sich auf den etwaigen theoretischen Wert für den eingesetzten DAC, wenn man mit 12 dominanten, gleich starken aber vollständig dekorrelierten Trägern im Band rechnet. Die Definition der SNR entspricht der im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).  

## Konfigurator

Wählen Sie Ihre Anforderungen für die Hardware, um zur passenden Auswahl zu gelangen:

 {{< selection-guide basepath="/de/docs/getting_started/auswahlhilfe/" >}}


## Verfügbare Kombinationen

Die folgende Tabelle zeigt eine Übersicht der verfügbaren Kombinationen:

| Control-Computer | Signalwandler |
|------------------|---------------|
| PC               | STEMLAB       |
| PC               | fl2k-Dongle   | 
| PC               | ADALM2000     |
| Raspberry-Pi     | STEMLAB       | 
| Raspberry-Pi     | fl2k-Dongle   |

**Hinweis:** Diese Kombinationen sind aktuell verfügbar. Weitere Kombinationen folgen, wenn neue Optionen bekannt werden.