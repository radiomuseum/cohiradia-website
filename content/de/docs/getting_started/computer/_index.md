---
title: Computer
linkTitle: Computer
date: 2026-01-01
weight: 30
description: >
---

Der Steuercomputer hat die Aufgabe, die Daten von den Aufzeichnungs-Dateien zu lesen und an den jeweils angeschlossenen Signalwandler zu übertragen. Je nach Steuergerät müssen die Daten entweder nur weitergeleitet oder ggf. vorher umgerechnet und aufbereitet werden. Damit dies bequem vonstatten gehen kann, läuft auf diesem Computer eine geeignete Software. 

Je nach ausgewählter Konfiguration (siehe dazu die Auswahlhilfe), kann der Comuter ein handelsüblicher PC oder ein ausreichend leistungsfähiger Single-Board-Computer wie etwa ein Raspberry-Pi, Modell 4 oder 5 sein.

Da die Datenfiles typischerweise sehr groß sind, werden sie oft auf externen Datenträgern (Festplatten, große USB-Sticks) gelagert. Beispielsweise benötigt man für ein MW-Band bei Standard-IQ-Aufzeichnungsformat (1.25MS/s, 4Byte/sample) etwa 18GB je Stunde Laufzeit. Hier hat der PC den Vorteil, dass er bei Vorhandensein einer großen Festplatte auch gleichzeitig als Speicher für Aufzeichnungen genutzt werden. Weiters ist er oft bereits ohnehin für andere Zwecke im Haushalt vorhanden. Möchte man aber ein kompaktes Stand-Alone-System haben, bietet sich ein Einplatinen-Computer an.

### PC als Steuercomputer

Wenn als Signalwandler ein mit FPGA ausgestattetes Gerät wie etwa das RedPitaya STEMLAB 125-14 verwendet wird, ist lediglich ein schnelles Lesen der Daten (ggf. von externer Disk über USB3.0) und ein LAN-Anschluss vonnöten, an den Computer werden keine sehr hohen Anforderungen gestellt.

Wird hingegen z.B. der OSMO fl2k-Dongle benutzt, wird gewisse Rechenleistung benötigt. Getestet wurde bisher auf folgenden Computern unter Windows 10 und Windows 11:

Lenovo T430, Intel-Core i5-3320M, 8GB Ram
Acer Swift, AMD Ryzen 5 4500U, 8GB Ram
Acer Aspire 5, Intel-Core i7-1165G7, 16GB Ram
TODO: Rechner von Walter
TODO: Rechner von Claus-Peter
TODO: Rechner von Stan

Entwickelt wurde die Software bisher auf einem Lenovo T590 mit Intel Core i7 mit 32GB Arbeitsspeicher. Getestet wurde die Software auf PCs bisher unter Windows 10, Windows 11 und LINUX Debian 12 und Debian 13.


## Raspberry Pi als Steuercomputer

Ein Raspberry Pi 4 eignet sich als kleinster bisher getesteter Single-Board Computer in Zusammenspiel mit einer auf das Nötigste reduzierten Software, dem COHI-Player Mini, sehr gut für reines Abspielen. Zusammen mit dem OSMO-flk2 läßt sich damit das bisher kostengünstigste System realisieren, das allerdings gewisse Einschränkungen hat. Mit einem Raspberry Pi 5 kann man auch die Vollversion der für den PC geschriebenen Python-Variante der Software und alternative Abspielprogramme (siehe dazu Links unter 'Projekte') problemlos betreiben. Für den Raspberry Pi 4 mit COHI-Player Mini reichen 4GB Arbeitsspeicher, beim Raspberry Pi 5 wurde bisher noch keine 4GB-Version getestet, 8GB sind aber jedenfalls ausreichend.  


<!-- comment -->