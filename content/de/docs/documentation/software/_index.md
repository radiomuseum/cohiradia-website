---
title: Software
linkTitle: Software
date: 2026-01-01
weight: 1
description: >
  Übersicht über die für Cohiradia bereitgestellte Software.
---

## Allgemeines

Für COHIRADIA stehen im RM zwei gleichwertige, offiziell bereitgestellte Programme zur Verfügung, die sich in ihrem Einsatzzweck ergänzen:

* **[COHIWizard](#cohiwizard):** die umfangreiche Software für PC (Windows und Linux) und Raspberry Pi 5. Neben der Wiedergabe der Breitbandaufnahmen bietet sie zahlreiche Werkzeuge, etwa zum Betrachten, Kommentieren, Umrechnen und Synthetisieren von Aufnahmen. Sie unterstützt die Signalwandler STEMLAB, OSMO fl2k und ADALM2000.
* **[COHI-Player](#cohi-player):** die schlanke, ohne manuelle Bedienung auskommende Abspielsoftware, besonders für Stand-Alone-Systeme mit dem Raspberry Pi 4/5 (aber auch für PCs). Sie spielt IQ-Aufzeichnungen nach dem Einschalten automatisch ab und kann zusätzlich Webradio-Streams als AM-Träger ausgeben bzw. in IQ-Aufzeichnungen hineinmischen. Sie unterstützt die Signalwandler STEMLAB und OSMO fl2k.

Welche Kombination aus Computer, Signalwandler und Software für Sie passt, zeigt die [Installationsanleitung](/de/docs/getting_started/installation/).

<a id="cohiwizard"></a>

## COHIWizard

Der COHIWizard ermöglicht das Abspielen der im Archiv gehosteten Breitbandaufnahmen auf analogen Radios, stellt aber darüber hinaus auch etliche nützliche Werkzeuge zur Verfügung. Aktuell sind diese:
* Viewer für die Inspektion der Spektren
* Annotator zur Kommentierung eigener Aufnahmen
* Resampling von Aufnahmen auf vom STEMLAB125-14 unterstützte Samplingraten
* Wav-Header-Editor zum Nacheditieren oder Erstellen der wav-Header
* Synthesizer für das Erstellen eigener AM-Bänder (Modulation beliebig vieler Träger mit Audioinhalten beliebiger Wahl)

Der COHIWizard ist sowohl für [Windows](#windows) als auch für [Linux](#linux) verfügbar. Unter Windows ist eine ausführbare Version (exe) verfügbar. Darüber hinaus ist der COHIWizard als offener Python-Quellcode auf [Github](https://github.com/hermy-sf/COHIWizard) frei zugänglich. Unter LINUX gibt es aktuell nur die Python-Version. 

Wer den COHIWizard unter Python ausführen möchte, findet die Installationsanleitung auf dem GITHUB-Repository in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md). 

Wer auf die jeweils neueste, aber noch in Entwicklung befindliche Version zugreifen möchte, sei auf die Rubrik [Experimentelle Version](#experimentelleV) verwiesen.

Bugreports zu Version 2.2.x sind willkommen.


<a id="windows"></a>

### Windows-10/11
Die exe-Version kann als Zip-Datei heruntergeladen werden und enthält auch ein Benutzerhandbuch. 

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_V2.1.1_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v2.2.5b.zip)

<a id="linux"></a>

### LINUX
Die Python-Version wurde unter Debian 12 und 13 unter Python implementiert. Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard) und folgen den Anweisungen in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md). 

**Das Benutzerhandbuch** kann auch von GITHub [hier heruntergeladen werden.](https://github.com/hermy-sf/COHIWizard/blob/cohiwizard_v2.2/documentation/UserManual_COHIWizard_v2.2_en.pdf). Möglicherweise wird das pdf in Ihrem Browser nicht angezeigt, aber ein Download ist dennoch möglich.

<a id="experimentelleV"></a>

### Experimentelle Versionen

Wenn Sie ein lokales GIT und die Source-Codes verwenden, können Sie auch auf den Entwicklungs-Branch [cohiwizard_v2.2](https://github.com/hermy-sf/COHIWizard/tree/cohiwizard_v2.2) zugreifen. Er ist allerdings experimentell und in ständigem Wandel. Von dort geladene Codes können unerwartetes Verhalten zeigen und werden daher nicht offiziell empfohlen.

Für [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) und Bugreports bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.

### Vorgängerversionen

Wer bereits Vorgängerversionen des aktuellen COHIWizard kennt und ggf. installiert hat, findet im [Software Archiv](alte-versionen.html) alte Versionen bis hin zum RFCorder, der die erste einfache Abspielsoftware darstellt, die für COHIRADIA entstanden ist. Alle diese Vorgängerversionen müssen aber als veraltet angesehen werden und werden auch nicht mehr gewartet.

### Hardware-Unterstützung

Der Player-Teil des COHIWizard ist mit einem Gerätetreiber-System ausgestattet. Damit ist es möglich, unterschiedliche für COHIRADIA geeignete Hardwareprodukte für die Generierung der analogen Antennensignale zu verwenden. 

Bislang wurden drei Geräte-Treiber implementiert:

1. 'STEMLAB125-14': Dies ist der generische Treiber für das STEMLAB125-14 von Red Pitaya, für das der COHIWizard ursprünglich geschrieben wurde. Er ermöglicht Wiedergabe und Recording über eine TCP-Verbindung (LAN-Schnittstelle). Mit 14 Bit Auflösung und 125MSamples/s bietet diese Lösung sehr hohe Daten- und Signalqualität für beliebige AM-Bänder bis max. 60 MHz und ist von allen Treibern bisher am besten getestet.

1. 'fl2k-stream': Dabei handelt es sich um einen  [USB zu VGA-Adapter](https://osmocom.org/projects/osmo-fl2k/wiki), der von verschiedenen Usergruppen als schneller 8-Bit DAC verwendet wird und auch bei einigen Hochfrequenz-Projekten eingesetzt wurde (siehe [fl2k-COHIRADIA-Projekt](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). Mit seinen nur 8 Bit Auflösung ist dieses sehr kostengünstige Gerät natürlich kein vollwertiger Ersatz für das STEMLAB, aber es genügt für viele Wiedergabe-Standardanwendungen durchaus, wie [Beispiele](https://youtu.be/4jC2XtWUFI8) zeigen. **ACHTUNG**: Nur Adapter mit dem Fresco Logic FL2000 Chip sind geeignet, bitte die (auch nicht mehr ganz aktuellen) Hinweise auf der [Osmocom-Wiki](https://osmocom.org/projects/osmo-fl2k/wiki) zu beachten, da dieser Chip nicht mehr hergestellt wird, und daher zunehmend Adapter mit anderen Chips verkauft werden. Bitte dies bei der Beschaffung des Adapter also zu beachten, sonst ist das Ergebnis negativ !

1. ADALM2000: Dieser Treiber erlaubt die Wiedergabe von IQ-Files mit oberen Badngrenzfrequenzen bis zu 2.5 MHz auf dem [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). Dies ist ein im Vergleich zum STEMLAB125-14 kostengünstiges, USB-betriebenes Modul mit 2 ADC- und 2 DAC-Kanälen zu je 12 Bit Auflösung sowie einem GPIO-Port. Es kann als Oszilloskop, Funktionsgenerator oder Logikanalysator betrieben werden, erlaubt aber auch die Wiedergabe von COHIRADIA-IQ-Files. Allerdings gibt es Einschränkungen: Durch die Verwendung von USB2.0 ist die obere Grenzfrequenz mit etwa 2500 kHz limitiert. Dies genügt für LW und MW, erlaubt die Wiedergabe von KW-Aufzeichnungen aber nur mit einem Trick: Durch Einstellen eines geeigneten Wertes im Feld 'LO-Offset' (z.B. -4000kHz für das 49m-Band) kann das Signal ins Mittelwellenband des Radios heruntergemischt und abgehört werden. Dieser Treiber ist noch nicht sehr ausgiebig getestet und muss daher noch als Beta-Version eingestuft werden. Erste Tests ergaben für MW und LW brauchbare Wiedergabe mit besserer Dynamik als das fl2k. Allerdings treten bei bestimmten Aufnahmen leichte Störgeräusche auf, die möglicherweise durch schlechtere Filterung/Interpolation als beim STEMLAB entstehen.

Sowohl (2) als auch (3) punkten zwar durch deutlich geringere Kosten als ein STEMLAB, erfordern aber deutlich mehr Rechenleistung auf dem PC, da sie nicht wie das STEMLAB über ein FPGA für die nötige Umcodierung der komplexen Basisbanddaten verfügen. Der ADALM2000 und das fl2k stellen daher keine gleichwertigen Alternativen zum STEMLAB dar, dessen Leistung nach wie vor unübertroffen bleibt.

<a id="cohi-player"></a>

## COHI-Player

Der COHI-Player von Claus Peter Gallenmiller ist eine schlanke Abspielsoftware, die einen Raspberry Pi oder PC in eine kleine „Sendestation“ für historische Radios verwandelt. Er kommt ohne manuelle Bedienung aus: Nach dem Start spielt er automatisch alle Breitband-IQ-Aufzeichnungen ab, die auf einem USB-Stick oder in einem internen Verzeichnis gespeichert sind. Damit eignet er sich besonders für Sammlungen, Ausstellungen und Museen. Als Signalwandler werden das STEMLAB (Red Pitaya) und der OSMO fl2k-Dongle unterstützt.

### Betriebsarten

* **COHI-Player:** Wiedergabe von Breitband-IQ-Aufzeichnungen (wav-Dateien), z. B. historischer Aufnahmen des kompletten Mittelwellenbands aus dem COHIRADIA-Archiv.
* **COHI-Stream:** Aktuelle **Webradio-Streams** (MP3/AAC/M3U) werden gleichzeitig als AM-Träger auf frei wählbaren Frequenzen ausgegeben – jeder Sender mit eigener Trägerfrequenz und Audiobandbreite. Über M3U-Playlists lassen sich auch lokale Audiodateien als Quelle verwenden. Eine Beispielliste mit 31 Webradio-Sendern (viele davon mit Musik der 1920er- bis 1960er-Jahre) ist enthalten, die Senderliste kann direkt im Programm bearbeitet werden.
* **COHI-Player+Stream:** Kombination aus beidem – Webradio-Streams (bzw. lokale Audiodateien über M3U-Playlists) werden als zusätzliche Träger in eine statische IQ-Aufzeichnung **hineingemischt**.

Für Webradio-Streams ist eine Internetverbindung nötig; um Aussetzer im Ton zu vermeiden, wird eine kabelgebundene LAN-Verbindung dringend empfohlen.

### Plattformen und Leistungsfähigkeit

Unter Linux bzw. Raspberry Pi OS stehen alle drei Betriebsarten zur Verfügung. Unter Windows ist nur die Betriebsart COHI-Player (Wiedergabe von IQ-Aufzeichnungen) möglich, da die für die Streams nötigen C++-Tools nicht für Windows bereitgestellt werden.

Auf dem Raspberry Pi gelten laut Bedienungsanleitung etwa folgende Grenzen (Richtwerte, abhängig von Datenrate und Stabilität der Streams):

| Betriebsart | Raspberry Pi 4 | Raspberry Pi 5 |
|---|---|---|
| COHI-Player mit STEMLAB oder fl2k | ✔ | ✔ |
| COHI-Stream mit STEMLAB | < 25 Streams | > 50 Streams |
| COHI-Stream mit fl2k | < 14 Streams | > 40 Streams |
| COHI-Player+Stream mit STEMLAB | IQ-Aufzeichnung + < 25 Streams | IQ-Aufzeichnung + > 50 Streams |
| COHI-Player+Stream mit fl2k | nicht möglich | IQ-Aufzeichnung + > 40 Streams |

Auf PCs hängt die Leistungsfähigkeit stark von der eingebauten CPU ab.

### Wichtige Hinweise

* Der COHI-Player findet nur Aufzeichnungen, deren Dateiname auf **`_0.wav`** endet (z. B. `MW_Berlin_1936_0.wav`). Unterverzeichnisse werden mit durchsucht, Folgedateien (`_1.wav`, `_2.wav`, …) werden automatisch angeschlossen.
* Der Ausgang liefert ein echtes HF-Signal im Mittelwellenbereich. Verbinden Sie ihn mit dem Radio nur über Kabel und ein [Koppelgerät](/de/docs/getting_started/koppelgeraet/) mit Trenntransformator, und beachten Sie die in Ihrem Land geltenden Vorschriften.

### Quellcode, Bedienungsanleitung und Installation

Der Quellcode ist auf GitHub im Repository [COHI-Player-Universal](https://github.com/CPG-Archive/COHI-Player-Universal) frei verfügbar. Die vollständige Bedienungs- und Konfigurationsanleitung findet sich in der [README-Datei](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md). Für den Raspberry Pi 4 und 5 stehen vorkonfigurierte Images zur Verfügung; die Schritt-für-Schritt-Anleitungen finden Sie in der [Installationsanleitung](/de/docs/getting_started/installation/).

<!-- comment -->