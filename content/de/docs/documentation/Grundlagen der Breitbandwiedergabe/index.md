---
title: Grundlagen der Breitbandwiedergabe
linkTitle: Grundlagen der Breitbandwiedergabe
date: 2026-01-01
weight: 4
description: >
---

## Aufzeichnung und Wiedergabe von 'natürlichen' Breitbandspektren

Grundsätzlich sind eine Vielzahl von Sendern gleichzeitig im elektromagnetischen Spektrum vorhanden. Im Mittelwellenband können das bei einem 9kHz-Kanalraster knapp 130 Stationen sein. Jeder Station ist eine Trägerfrequenz zugeordnet. Im Gegensatz zu Audiosignalen, bei denen nur eine Schallquelle auf ein (mono) oder zwei (Stereo) Kanälen aufgenommen wird, sind in einem Band also viele Audiosignale gleichzeitig präsent, indem sie auf ihre jeweiligen Trägerfrequenzen aufmoduliert werden. Das ist in Abb. 1 schematisch dargestellt: Jeder Sender, der auf der Radioskala (links oben) eingestellt werden kann, entspricht einer Spitze im gesamten MW-Spektrum, hier zwischen 500 und 1700 kHz (unten). Der Rundfunkempfänger wählt dabei genau diejenige 'Spitze' aus, die dem eingestellten Sender entspricht (rechts oben), und demoduliert das Signal. So ist nur ein Kanal hörbar, obwohl natürlich weiterhin alle gleichzeitig am Antenneneingang anliegen.


<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_1.png"
  style="max-width: 90%; height: auto;"
/>


*Abb. 1: Sender und deren Signale im gesamten MW-Spektrum* 

Will man nun dem Radio nun ein adäquates Antennensignal anbieten, das in der Vergangenheit einmal existiert hat, so muss man also in jener Vergangenheit das Gesamtspektrum in seiner vollen Breite aufgezeichnet haben. Das bedeutet anstatt 2x 20 kHz für Audio eine Bandbreite von mindestens 1200 kHz. Derart breitbandige Aufnahmen können heutzutage mit speziellen Signalwandlern, sogenannten software-defined Radios (SDR) durchgeführt werden.

TODO TODO

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_pipeline_1.png" />

*Abbildung 2: Aufzeichnung und Bearbeitung von Breitband-Antennensignalen für das Archiv* 

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_pipeline_2.png" />

*Abbildung 3: Bereitstellung von Software für das Abspielen auf analogen Radios.*

# künstliche Generierung von Breitbandspektren (Synthese im Sinne der Jukebox)

Das von einem AM-Sender ausgesendete elektromagnetische Signal besteht aus einer sinusförmigen Trägerschwingung mit der nominellen Sendefrequenz f_T und dem Nutzsignal, das dieser Trägerschwingung als Amplitudenschwankung aufgeprägt wird (siehe Abb. 1 A). Will man ein solches Signal künstlich erzeigen, hat man grundsätzlich zwei Möglichkeiten: 

1. Modulation eines analogen Signalgenerators mit einem Audiosignal
2. digitale Synthese auf einem Computer aus digitalen Audioquellen (z.B. wav, mp3, o.ä.) und anschließende Digital-Analog-Wandlung /DAC).
   
Will man ein ganzes Spektrum mit vielen nebeneinander existierenden Sendern erzeugen, muss man Einzelsignale zusammensetzen. Im Fall 1 (analog) muss man mehrere einzelne nach (1) generierte Signale mit unterschiedlichen Trägerfrequenzen zusammenaddieren, siehe Abb. 1 B. Im Fall 2 (digital) werden die Signale der Einzelsender aus den jeweiligen Audiodateien berechnet und anschließend addiert. Danach folgt wieder eine DA-Wandlung (siehe Abb. 1 C). 

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/spektrumsgenerierung_de.png" />

*Abbildung 4: A: Prinzip der Amplitudenmodulation. B: Generierung eines Spektrums durch Zusammenschaltung analoger Modulatoren. C: Generierung eines Spektrums durch digitale Synthese.* 



<!-- comment -->