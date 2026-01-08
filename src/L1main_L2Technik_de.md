
[Computer](https://www.radiomuseum.org/cohiradia/L2Technik_L3Computer.html) |
[Signalwandler](https://www.radiomuseum.org/cohiradia/L2Technik_L3Signalwandler.html) |
[Koppelgerät](https://www.radiomuseum.org/cohiradia/L2Technik_L3Koppelgeraet.html) |
[Software](https://www.radiomuseum.org/cohiradia/L2Technik_L3Software.html) |
[Installation](https://www.radiomuseum.org/cohiradia/L2Technik_L3Installation.html) |
[Detailinfo](https://www.radiomuseum.org/cohiradia/L2Technik_L3Detailinfo.html) |
[Komplementäre Projekte](https://www.radiomuseum.org/cohiradia/L2Technik_L3Komplementaere_Projekte.html) |


## Technische Lösung

Ermöglicht wird COHIRADIA durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Dafür benötigt man grundsätzlich folgende Elemente:

* einen Steuercomputer mit geeigneter Software (kann auch ein kleiner Single board Computer wie ein Raspberry Pi sein)
* einen Signalwandler
* ein Koppelgerät
* ein Archiv mit digitalisierten Breitband-AM-Signalen


<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/Blockbild_buildingblocks_de_v1.png" /> 

Breitbandige Aufzeichnung direkt von einer Antenne ist mittlerweile relativ einfach mit mehreren auf dem Markt befindliche SDRs möglich, die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang. COHIRADIA stellt dafür eine Plattform bereit, die auf dem STEMLAB125‐14 von RedPitaya beruht. Dieses bietet mit 14 Bit ADC-Auflösung und 125MS/s Samplingrate eine ausgezeichnete Aufnahme- und Wiedergabequalität. Auch das deutlich billigere STEMLAB125-10 wurde bereits versuchsweise für Playback eingesetzt, allerdings nicht umfassend getestet. Alternative TX-fähige SDRS mit ähnlichen oder besseren Leistungsdaten existieren ebenfalls.

Die Aufzeichnungen können von jeder Person abgespielt werden die ebenfalls über ein STEMLAB125‐14 oder ein geeignetes TX-fähiges SDR verfügt. Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.
Danach evt Bild des Signalflussplans oder auch erst auf 'Detailinformation'
