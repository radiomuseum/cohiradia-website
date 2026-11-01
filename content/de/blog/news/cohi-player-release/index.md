---
date: 2026-11-01
title: Der neue COHI-Player macht den Raspberry Pi zur Breitband-Mittelwellen-Sendestation
linkTitle: Neuer COHI-Player
description: >
  Der neue COHI-Player von Claus Peter Gallenmiller ist da: fertige Images für Raspberry Pi 4 und 5, historische Aufzeichnungen und aktuelle Webradio-Streams auf frei wählbaren Mittelwellenfrequenzen.
author: Hermann Scharfetter
---

Sie drehen am Senderknopf Ihres alten Radios, und auf der Skala meldet sich ein Sender nach dem anderen, ganz wie zu seiner Zeit. Genau das ermöglicht der neue **COHI-Player** von Claus Peter Gallenmiller, der Nachfolger des COHI-Player mini: Er verwandelt einen Raspberry Pi in eine kleine „Sendestation“ für historische Radios.

<figure>
  <img src="/images/COHIPlyer_Teaser1_CPG_image021.png" alt="Raspberry Pi mit Touch-Display und laufendem COHI-Player vor einem historischen Radio Telefunken 8001W" style="width: 380px; max-width: 100%; height: auto;"/>
  <figcaption><em>Der COHI-Player auf dem Raspberry Pi vor einem Telefunken 8001W. Foto: Claus Peter Gallenmiller</em></figcaption>
</figure>

### Drei Betriebsarten

* **COHI-Player:** spielt Aufzeichnungen ganzer Mittelwellenbänder ab, zum Beispiel aus dem [COHIRADIA-Archiv](/de/archiv/).
* **COHI-Stream:** sendet aktuelle Webradio-Streams gleichzeitig auf mehreren frei wählbaren Trägerfrequenzen. Eine Beispielliste mit 31 Sendern ist dabei, viele davon mit Musik der 1920er- bis 1960er-Jahre. Über M3U-Playlists lassen sich auch eigene Audiodateien einbinden.
* **COHI-Player+Stream:** mischt Webradio-Streams als zusätzliche Träger in eine historische Bandaufzeichnung.

### Einschalten und Radio hören

Der COHI-Player braucht keine Bedienung, um loszuspielen: Nach dem Start gibt er automatisch alle Aufzeichnungen wieder, die auf einem USB-Stick oder in einem internen Verzeichnis liegen. Damit eignet er sich auch ideal, um historische Empfänger in großen Sammlungen und Museen mit Antennensignalen zu versorgen.

### Fertige Images für den Raspberry Pi

Für den Raspberry Pi 4 und 5 stehen vorkonfigurierte Images bereit. Sie werden einfach auf eine SD-Karte geschrieben, danach ist das System betriebsbereit. Neue Aufzeichnungen und Programmupdates lassen sich bequem über das Netzwerk übertragen.

Das HF-Signal erzeugt entweder ein STEMLAB (Red Pitaya) oder ein preisgünstiger fl2k-USB-VGA-Dongle. Für den COHI-Player reicht ein Raspberry Pi 4. Für viele gleichzeitige Streams empfiehlt sich der Raspberry Pi 5, der laut Bedienungsanleitung mehr als 40 Live-Streams (fl2k) bzw. mehr als 50 (STEMLAB) schafft.

### So geht es los

* [Installationsanleitung](/de/docs/getting_started/installation/): Wählen Sie Ihre Kombination aus Computer und Signalwandler.
* [Dokumentation → Software](/de/docs/documentation/software/#cohi-player): alle Betriebsarten und Leistungsdaten im Überblick.
* [Quellcode und Bedienungsanleitung auf GitHub](https://github.com/CPG-Archive/COHI-Player-Universal): Der COHI-Player steht unter der Lizenz GPL-3.0.

**Wichtig:** Der COHI-Player erzeugt ein echtes HF-Signal im Mittelwellenbereich. Senden ohne Lizenz ist in den meisten Ländern verboten und kann andere Funkdienste stören. Verbinden Sie den Ausgang daher per Kabel und Trennübertrager mit dem Antenneneingang des Radios oder verwenden Sie eine Koppelschleife mit vernachlässigbarer Abstrahlung. Hinweise dazu finden Sie unter [Koppelgerät](/de/docs/getting_started/koppelgeraet/).
