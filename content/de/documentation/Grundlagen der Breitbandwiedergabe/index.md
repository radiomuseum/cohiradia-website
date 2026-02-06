---
title: Grundlagen der Breitbandwiedergabe
linkTitle: Grundlagen der Breitbandwiedergabe
date: 2026-01-01
weight: 7
description: >
   Hier kann man technische Details wie unseren Bericht 2023 ablegen, damit wir auch eine fundierte ingenieurswissenschaftliche Basis bereitstellen. 
---

# Aufzeichnung und Wiedergabe von 'natürlichen' Breitbandspektren

TODO TODO TODO
BLA BLA BLA .............

Hier muss noch ordentlich gearbeitet werden !

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_1.png" />

*Abbildung 1: Sender und deren Signale im gesamten MW-Spektrum* 

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