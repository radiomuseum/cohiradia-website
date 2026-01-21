---
title: Signalwandler
linkTitle: Signalwandler
date: 2026-01-01
weight: 2
description: >
  Das ist das 'SDR', also bisher STEMLAB, fl2k und ADALM2000.
---

## Allgemeines

Der Signalwandler hat die Aufgabe, einen digitalen Datenstrom vom Steuercomputer zu übernehmen und in das analoge Antennensignal für den Empfänger umzuwandeln. Grob vereinfacht kann man das als Digital-Analog_wandler ansehen, 
die meisten verwendbaren Geräte sind aber komplexer. Aufgrund des Gerätetreiber-Konzepts der offiziellen COHIRADIA-Software ist es grundsätzlich möglich, unterschiedliche Hardwareprodukte für die Signalwandlung zu verwenden. 

## Unterstützte Hardware

Bislang wurden drei Geräte getestet und dafür Softwaretreiber integriert:

1. [STEMLAB125-14 von Red Pitaya](https://redpitaya.com/stemlab-125-14-gen2/?srsltid=AfmBOoqpGfok05eVHWlfTpikYPgMxxi98fzhOZlGDNTpoSf0ceoIQGoq): Dies ist das generische 'Arbeitstier', für das der COHIWizard ursprünglich geschrieben wurde. Es ermöglicht Wiedergabe und Recording über eine TCP-Verbindung (LAN-Schnittstelle). Mit 14 Bit Auflösung und 125MSamples/s bietet diese Lösung sehr hohe Daten- und Signalqualität für beliebige AM-Bänder bis max. 60 MHz und ist von allen Produkte bisher am besten getestet. Allerdings ist dieses Gerät mit ca. 500€ vergleichsweise teuer. Es kann aber auch multifunktional als kleine Signalgenerierungs- und Analyseplattform (Signalgenrator, Oszilloskop, simpler Netzweranalysator) bis 60MHz im Labor eingesetzt werden.

1. [OSMO fl2k](https://osmocom.org/projects/osmo-fl2k/wiki): Dabei handelt es sich um einen sehr kostengünstigen (ca 25 - 30 €) USB zu VGA-Adapter, der von verschiedenen Usergruppen als 
schneller 8-Bit DAC verwendet wird und auch bei einigen Hochfrequenz-Projekten eingesetzt wurde 
(siehe [fl2k-COHIRADIA-Projekt](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). 
Mit seinen nur 8 Bit Auflösung ist dieses billige Gerät natürlich kein vollwertiger Ersatz für das STEMLAB, aber es genügt für viele Wiedergabe-Standardanwendungen durchaus,
wie [Beispiele](https://youtu.be/4jC2XtWUFI8) zeigen. **ACHTUNG**: Nur Adapter mit dem Fresco Logic FL2000 Chip sind geeignet, bitte die (auch nicht mehr ganz aktuellen) Hinweise auf 
der [Osmocom-Wiki](https://osmocom.org/projects/osmo-fl2k/wiki) zu beachten, da dieser Chip nicht mehr hergestellt wird, und daher zunehmend Adapter mit anderen Chips verkauft werden. 
Bitte dies bei der Beschaffung des Adapter also zu beachten, sonst ist das Ergebnis negativ !

1. [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html): Diese Hardware erlaubt die Wiedergabe von COHIRADIA-IQ-Files mit oberen Bandgrenzfrequenzen bis zu 2.5 MHz. Der ADALM2000 ist ein im Vergleich zum STEMLAB125-14 kostengünstigeres (ca 200 - 250 €), USB-betriebenes Modul mit 2 ADC- und 2 DAC-Kanälen zu je 12 Bit Auflösung sowie einem GPIO-Port. Es kann wie das STEMLAB alternativ als kleines- PC-gekoppeltes Oszilloskop, Funktionsgenerator oder Logikanalysator betrieben werden. 
Allerdings gibt es Einschränkungen: Durch die Verwendung von USB2.0 ist die obere Grenzfrequenz mit etwa 2500 kHz limitiert. 
Dies genügt für LW und MW, erlaubt die Wiedergabe von KW-Aufzeichnungen aber nur mit einem Trick: Durch Einstellen eines geeigneten Wertes im Feld 'LO-Offset' (z.B. -4000kHz für das 49m-Band) 
kann das Signal ins Mittelwellenband des Radios heruntergemischt und abgehört werden. Dieser Treiber ist noch nicht sehr ausgiebig getestet und muss daher noch als Beta-Version eingestuft werden. 
Erste Tests ergaben für MW und LW brauchbare Wiedergabe mit besserer Dynamik als das fl2k. Allerdings treten bei bestimmten Aufnahmen leichte Störgeräusche auf, die möglicherweise durch 
schlechtere Filterung/Interpolation als beim STEMLAB entstehen.

Sowohl (2) als auch (3) erfordern deutlich mehr Rechenleistung auf dem PC, da sie nicht wie das STEMLAB über ein FPGA für die nötige Umcodierung der komplexen Basisbanddaten verfügen. Der ADALM2000 und das fl2k stellen daher keine gleichwertigen Alternativen zum STEMLAB dar, dessen Leistung nach wie vor unübertroffen bleibt. 
