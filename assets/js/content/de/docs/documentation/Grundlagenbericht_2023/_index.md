---
title: Grundlagen-Bericht
linkTitle: Grundlagen-Bericht
date: 2026-01-01
weight: 3
nav_exclude: false
description: >
---

Alle wichtigen technischen Details zur Implementierung von COHIRADIA wurden im [Bericht 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf) zusammengefasst. Die wichtigen Punkte sind:

* Organisation von COHIRADIA
* Struktur und Regeln für den Aufbau des Archivs
* Analysen zur Signalqualität
* Technische Grundlagen zu den Signalwandlern
* Benötigte Zusatz-Hardware (incl. Selbstbau-Hinweise)
* Grundlagen für das Software-Design
* Referenzen
* Datenstrukturen

Es wird darauf hingewiesen, dass dieser Bericht den Wissensstand des COHIRADIA-Teams im Jahr 2023 repräsentiert und daher in einigen Punkten nicht mehr ganz aktuell ist. Zwei diesbezügliche Punkte sollen daher explizit erwähnt werden:

(1) Damals wurde davon ausgegangen, dass 8-Bit-Signalwandler für COHIRADIA wenig geeignet seien. Während dies für Aufzeichnungen (außer für den Fall exzessiven Oversamplings) weiterhin gilt, wurde für Wiedergabe gezeigt, dass z.B. das OSMO-fl2k-System sehr wohl befriedigende Ergebnisse erlaubt, wenngleich die SNR natürlich nicht an die eines Wandlers mit 12 oder 14 Bit herankommt. Dies stört aber bei vielen Aufzeichnungen und Wiedergabe mit den meisten Rundfunkgeräten auf LW und MW nicht wesentlich.

(2) Ausführung des Koppeltransformators: Hier wird im Bericht 2023 noch von Wicklungen mit lackisoliertem Draht (CuL) berichtet. **Im Sinne ausreichender Sicherheit beim Betreiben alter Röhrenradios wird aber mittlerweile dringend vor der Verwendung lackisolierter Drähte abgeraten, da diese im Fall von Beschädigungen zu gefährlicher galvanischer Kopplung über die oft leitfähigen Ringkerne führen können.** Wir empfehlen daher nur noch die Bauweise, die in der Rubrik  ['Koppelgeräte']({{< relref "/docs/getting_started/koppelgeraet/_index.md" >}}) dieser Webpage beschrieben ist. 



