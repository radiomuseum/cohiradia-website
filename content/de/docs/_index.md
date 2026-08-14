---
title: Technik
linkTitle: Technik
---

Ermöglicht wird COHIRADIA durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.

Für die Wiedergabe benötigt man grundsätzlich folgende Elemente:

* einen Steuercomputer (kann auch ein kleiner Single board Computer wie ein Raspberry Pi sein)
* einen Signalwandler ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1352,1420)) 
* ein Koppelgerät ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1420,1480)) 
* geeignete Software ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1490,1562)) 
* ein [Archiv](../../archiv/index.html) mit digitalisierten Breitband-AM-Signalen

Für jedes dieser Elemente gibt es mehrere mögliche Realisierungsmöglichkeiten, je nach Anforderung und Budget. Wir weisen an dieser Stelle explizit darauf hin, dass über COHIRADIA keine Produkte verkauft werden, sondern dass die Plattform lediglich Informationen und Anleitungen sowie open-source-Software bereitstellt. Letztere wird vom COHIRADIA-Team selbst geschrieben, es gibt aber auch Alternativen von anderen SDR-affinen Gruppen (siehe Links am Ende dieses Kapitels). Für einen Teil der Hardware (insbesondere Computer und Signalwandler) werden kommerzielle Produkte eingesetzt. Es wird darauf hingewiesen, dass COHIRADIA keine kommerziellen Verbindungen zu Herstellern dieser Produkte hat und Marken- sowie Firmennamen lediglich zum Zweck der Information nennt. Ein anderer Teil der Hardware (z.B. die Koppelgeräte) kann von handwerklich/elektronisch geschickten Anwender:innen selbst gefertigt werden. Abbildung 1 gibt einen schematischen Überblick unter Einbeziehung einiger aktuell getesteter Komponenten. 

{{% imgproc blockbild-buildingblocks_de_v1 Fit "1200x1000 webp" %}}
*Abbildung 1:* Schematischer Überblick über die benötigten Elemente mit exemplarischer Abbildung aktuell eingesetzter komponenten. Das Datenarchiv ist nicht dargestellt, es befindet sich in der Regel auf einem lokalen Speichermedium am Steuercomputer.
{{% /imgproc %}}

Wenn gewünscht, so ist eine breitbandige Aufzeichnung von AM-Signalen direkt von einer Antenne relativ einfach mit etlichen kommerziellen SDRs möglich. Die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang oder geeignete schnelle Digital-Analogwandler mit entsprechender Firmware-Unterstützung. 


### Interessante alternative Software-Projekte:

Für das Abspielen von COHIRADIA-Aufzeichnungen kann auch andere Software als der offiziell von COHIRADIA bereitgestellte **COHIWizard** verwendet werden. Für alle, die unter LINUX arbeiten, kommen z.B. die sehr interesanten Codes des GITHUB-Repositories [radiolab81](https://github.com/radiolab81) in Frage. Insbesondere der [COHIRADIA-Streamer](https://github.com/radiolab81/COHIRADIAStreamer) und [AMWavSynth](https://github.com/radiolab81/AMWaveSynth) sind hier erwähnenswert. Die User sollten allerdings etwas IT-affin sein, um diese Tools effektiv einsetzen zu können. Inzwischen wurden auch neue Device-Treiber basierend auf einzelnen Codes dieses Repositories in experimentelle Versionen des COHIWizard eingebaut.

### Interessante alternative Hardware-Lösungen

[radiolab81](https://github.com/radiolab81) biete auch einige gute Ideen für alternative Hardware, die z.T. sehr kostengünstig ist, allerdings auch etwas Bastelgeschick erfordert. Zu erwähnen sind insbesondere [parlioSDR](https://github.com/radiolab81/parlioSDR) und [smisdr](https://github.com/radiolab81/smisdr). 

