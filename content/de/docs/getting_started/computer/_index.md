---
title: Computer
linkTitle: Computer
date: 2026-01-01
weight: 30
description: >
---

Der Steuercomputer hat die Aufgabe, die Daten von den Aufzeichnungs-Dateien zu lesen und an den jeweils angeschlossenen Signalwandler zu übertragen. Je nach Steuergerät müssen die Daten entweder nur weitergeleitet oder ggf. vorher umgerechnet und aufbereitet werden. Damit dies bequem vonstatten gehen kann, läuft auf diesem Computer eine geeignete Software. 

Je nach ausgewählter Konfiguration (siehe dazu die Auswahlhilfe), kann der Comuter ein handelsüblicher PC oder ein ausreichend leistungsfähiger Single-Board-Computer wie etwa ein Raspberry-Pi, Modell 4 oder 5 sein.

### PC als Steuerrechner

Wenn als Signalwandler ein mit FPGA ausgestattetes Gerät wie etwa das RedPitaya STEMLAB 125-14 verwendet wird, ist lediglich ein schnelles Lesen der Daten (ggf. von externer Disk über USB3.0) und ein LAN-Anschluss vonnöten, an den Computer werden keine sehr hohen Anforderungen gestellt.

Wird hingegen z.B. der OSMO fl2k-Dongle benutzt, wird gewisse Rechenleistung benötigt. Entwickelt wurde die Software bisher auf einem Lenovo T590 mit Intel Core i7 mit 32GB Arbeitsspeicher. Getestet wurde die Software auf PCs bisher unter Windows 10, Windows 11 und LINUX Debian 12 und Debian 13.

Getestet wurde die Anwendung mit deutlich schwächeren Rechnern, wie z.B. ???TODO ???

## Raspberry Pi als Steuerrechner

Ein Raspberry Pi 4 eignet sich als kleinster bisher getesteter Single-Board Computer in Zusammenspiel mit einer auf das Nötigste reduzierten Software, dem COHI-Player Mini, sehr gut für reines Abspielen. Zusammen mit dem OSMO-flk2 läßt sich damit das bisher kostengünstigste System realisieren, das allerdings gewisse Einschränkungen hat. Mit einem Raspberry Pi 5 kann man auch die Vollversion der für den PC geschriebenen Python-Variante der Software und alternative Abspielprogramme (siehe dazu Links unter 'Projekte') problemlos betreiben. Für den Raspberry Pi 4 mit COHI-Player Mini reichen 4GB Arbeitsspeicher, beim Raspberry Pi 5 wurde bisher noch keine 4GB-Version getestet, 8GB sind aber jedenfalls ausreichend.  


<!-- comment -->