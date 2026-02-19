---
title: Getting Started
weight: 1
menu:
  main:
    weight: 15
---

Ermöglicht wird COHIRADIA durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.

Für die Wiedergabe benötigt man grundsätzlich folgende Elemente:

* einen Steuercomputer (kann auch ein kleiner Single board Computer wie ein Raspberry Pi sein)
* einen Signalwandler ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1352,1420)) 
* ein Koppelgerät ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1420,1480)) 
* geeignete Software ([Beispiel](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1490,1562)) 
* ein Archiv mit digitalisierten Breitband-AM-Signalen

Für jedes dieser Elemente gibt es mehrere mögliche Realisierungsmöglichkeiten, je nach Anforderung und Budget. Während die Software vom COHIRADIA-Team als Open-source-Code selbst geschrieben wird, werden für einen Teil der Hardware (insbesondere Computer und Signalwandler) kommerzielle Produkte eingesetzt. Ein anderer Teil der Hardware (z.B. die Koppelgeräte) kann von handwerklich/elektronisch geschickten Anwender:innen selbst gefertigt werden. Abbildung 1 gibt einen schematischen Überblick unter Einbeziehung einiger aktuell getesteter Komponenten. 

**Entscheidungshilfe:** Um schnell zu einer Entscheidung für ein zu Ihnen passendes System zu kommen, benutzen Sie bitte die 'Auswahlhilfe' links in der Navigationsleiste. Genauere Beschreibungen der Elemente finen Sie unter 'Koppelgerät', 'Signalwandler' und 'Computer'


{{% imgproc blockbild-buildingblocks_de_v1 Fit "1200x1000 webp" %}}
*Abbildung 1:* Schematischer Überblick über die benötigten Elemente mit exemplarischer Abbildung aktuell eingesetzter komponenten. Das Datenarchiv ist nicht dargestellt, es befindet sich in der Regel auf einem lokalen Speichermedium am Steuercomputer.
{{% /imgproc %}}

Wenn gewünscht, so ist eine breitbandige Aufzeichnung von AM-Signalen direkt von einer Antenne relativ einfach mit etlichen kommerziellen SDRs möglich. Die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang oder geeignete schnelle Digital-Analogwandler mit entsprechender Firmware-Unterstützung. 


