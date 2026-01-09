
[Computer](https://www.radiomuseum.org/cohiradia/L2Technik_L3Computer.html) |
[Signalwandler](https://www.radiomuseum.org/cohiradia/L2Technik_L3Signalwandler.html) |
[Koppelgerät](https://www.radiomuseum.org/cohiradia/L2Technik_L3Koppelgeraet.html) |
[Software](https://www.radiomuseum.org/cohiradia/L2Technik_L3Software.html) |
[Installation](https://www.radiomuseum.org/cohiradia/L2Technik_L3Installation.html) |
[Detailinfo](https://www.radiomuseum.org/cohiradia/L2Technik_L3Detailinfo.html) |
[Komplementäre Projekte](https://www.radiomuseum.org/cohiradia/L2Technik_L3Komplementaere_Projekte.html) |



## Technische Lösung

Ermöglicht wird COHIRADIA durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.

Für die Wiedergabe benötigt man grundsätzlich folgende Elemente:

* einen Steuercomputer (kann auch ein kleiner Single board Computer wie ein Raspberry Pi sein)
* geeignete Software 
* einen Signalwandler ([siehe z.B.](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=489.506)) 
* ein Koppelgerät

* ein Archiv mit digitalisierten Breitband-AM-Signalen

Für jedes dieser Elemente gibt es mehrere mögliche Realisierungsmöglichkeiten, je nach Anforderung und Budget. Während die Software vom COHIRADIA-team selbst geschrieben wird und grundsätzlich open-source ist, werden für einen Teil der Hardware (insbesondere Computer und Signalwandler) kommerzielle Produkte eingesetzt. Ein anderer Teil der Hardware (z.B. die Koppelgeräte) kann von handwerklich/elektronisch geschickten Anwender:innen selbst gefertigt werden. Abbildung 1 gibt einen schematischen Überblick unter Einbeziehung einiger aktuell getesteter Komponenten. 
<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/Blockbild_buildingblocks_de_v1.png" /> 
Abbildung 1: Schematischer Überblick über die benötigten Elemente mit exemplarischer Abbildung aktuell eingesetzter komponenten. Das Datenarchiv ist nicht dargestellt, es befindet sich in der Regel auf einem lokalen Speichermedium am Steuercomputer.

Wenn gewünscht, so ist eine breitbandige Aufzeichnung von AM-Signalen direkt von einer Antenne relativ einfach mit etlichen kommerziellen SDRs möglich. Die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang oder geeignete schnelle Digital-Analogwandler mit entsprechender Firmware-Unterstützung. 


Danach evt Bild des Signalflussplans oder auch erst auf 'Detailinformation'
