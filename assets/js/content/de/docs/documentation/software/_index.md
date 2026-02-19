---
title: Software
linkTitle: Software
date: 2026-01-01
weight: 1
description: >
  Cohiradia Software
---

## Allgemeines

Die offiziell im RM bereitgestellte Software für COHIRADIA ist der COHIWizard. Er ermöglicht das Abspielen der im Archiv gehosteten Breitbandaufnahmen auf analogen Radios, stellt aber darüber hinaus auch etliche nützliche Werkzeuge zur Verfügung. Aktuell sind diese:
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

## Windows-10/11
Die exe-Version kann als Zip-Datei heruntergeladen werden und enthält auch ein Benutzerhandbuch. 

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_V2.1.1_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v2.2.1.zip)

<a id="linux"></a>

## LINUX
Die Python-Version wurde unter Debian 12 und 13 unter Python implementiert. Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard) und folgen den Anweisungen in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md). 


<a id="experimentelleV"></a>

## Experimentelle Versionen

Wenn Sie ein lokales GIT und die Source-Codes verwenden, können Sie auch auf den Entwicklungs-Branch [cohiwizard_v2.2](https://github.com/hermy-sf/COHIWizard/tree/cohiwizard_v2.2) zugreifen. Er ist allerdings experimentell und in ständigem Wandel. Von dort geladene Codes können unerwartetes Verhalten zeigen und werden daher nicht offiziell empfohlen.

Für [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) und Bugreports bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.

## Vorgängerversionen

Wer bereist Vorgängerversionen des aktuellen COHIWizard kennt und ggf. installiert hat, findet unter [diesem Link](https://www.radiomuseum.org/cohiradia/L3Software_L4software_previous_vs.html) alte Versionen bis hin zum RFCorder, der die erste einfache Abspielsoftware darstellt, die für COHIRADIA entstanden ist. Alle diese Vorgängerversionen müssen aber als veraltet angesehen werden und werden auch nicht mehr gewartet.

## Hardware-Unterstützung

Der Player-Teil des COHIWizard ist mit einem Gerätetreiber-System ausgestattet. Damit ist es möglich, unterschiedliche für COHIRADIA geeignete Hardwareprodukte für die Generierung der analogen Antennensignale zu verwenden. 

Bislang wurden drei Geräte-Treiber implementiert:

1. 'STEMLAB125-14': Dies ist der generische Treiber für das STEMLAB125-14 von Red Pitaya, für das der COHIWizard ursprünglich geschrieben wurde. Er ermöglicht Wiedergabe und Recording über eine TCP-Verbindung (LAN-Schnittstelle). Mit 14 Bit Auflösung und 125MSamples/s bietet diese Lösung sehr hohe Daten- und Signalqualität für beliebige AM-Bänder bis max. 60 MHz und ist von allen Treibern bisher am besten getestet.

1. 'fl2k-stream': Dabei handelt es sich um einen  [USB zu VGA-Adapter](https://osmocom.org/projects/osmo-fl2k/wiki), der von verschiedenen Usergruppen als schneller 8-Bit DAC verwendet wird und auch bei einigen Hochfrequenz-Projekten eingesetzt wurde (siehe [fl2k-COHIRADIA-Projekt](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). Mit seinen nur 8 Bit Auflösung ist dieses sehr kostengünstige Gerät natürlich kein vollwertiger Ersatz für das STEMLAB, aber es genügt für viele Wiedergabe-Standardanwendungen durchaus, wie [Beispiele](https://youtu.be/4jC2XtWUFI8) zeigen. **ACHTUNG**: Nur Adapter mit dem Fresco Logic FL2000 Chip sind geeignet, bitte die (auch nicht mehr ganz aktuellen) Hinweise auf der [Osmocom-Wiki](https://osmocom.org/projects/osmo-fl2k/wiki) zu beachten, da dieser Chip nicht mehr hergestellt wird, und daher zunehmend Adapter mit anderen Chips verkauft werden. Bitte dies bei der Beschaffung des Adapter also zu beachten, sonst ist das Ergebnis negativ !

1. ADALM2000: Dieser Treiber erlaubt die Wiedergabe von IQ-Files mit oberen Badngrenzfrequenzen bis zu 2.5 MHz auf dem [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). Dies ist ein im Vergleich zum STEMLAB125-14 kostengünstiges, USB-betriebenes Modul mit 2 ADC- und 2 DAC-Kanälen zu je 12 Bit Auflösung sowie einem GPIO-Port. Es kann als Oszilloskop, Funktionsgenerator oder Logikanalysator betrieben werden, erlaubt aber auch die Wiedergabe von COHIRADIA-IQ-Files. Allerdings gibt es Einschränkungen: Durch die Verwendung von USB2.0 ist die obere Grenzfrequenz mit etwa 2500 kHz limitiert. Dies genügt für LW und MW, erlaubt die Wiedergabe von KW-Aufzeichnungen aber nur mit einem Trick: Durch Einstellen eines geeigneten Wertes im Feld 'LO-Offset' (z.B. -4000kHz für das 49m-Band) kann das Signal ins Mittelwellenband des Radios heruntergemischt und abgehört werden. Dieser Treiber ist noch nicht sehr ausgiebig getestet und muss daher noch als Beta-Version eingestuft werden. Erste Tests ergaben für MW und LW brauchbare Wiedergabe mit besserer Dynamik als das fl2k. Allerdings treten bei bestimmten Aufnahmen leichte Störgeräusche auf, die möglicherweise durch schlechtere Filterung/Interpolation als beim STEMLAB entstehen.

Sowohl (2) als auch (3) punkten zwar durch deutlich geringere Kosten als ein STEMLAB, erfordern aber deutlich mehr Rechenleistung auf dem PC, da sie nicht wie das STEMLAB über ein FPGA für die nötige Umcodierung der komplexen Basisbanddaten verfügen. Der ADALM2000 und das fl2k stellen daher keine gleichwertigen Alternativen zum STEMLAB dar, dessen Leistung nach wie vor unübertroffen bleibt. 




<!-- comment -->