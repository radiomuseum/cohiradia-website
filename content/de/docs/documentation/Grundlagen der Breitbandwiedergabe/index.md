---
title: Grundlagen der Breitbandwiedergabe
linkTitle: Grundlagen der Breitbandwiedergabe
date: 2026-01-01
weight: 4
description: >
---

## Aufzeichnung und Wiedergabe von 'natürlichen' Breitbandspektren

**Wenn Sie ein Video zum Thema bevorzugen so sehen Sie sich einfach dieses hier an:**


{{< video_ext_v2 url="https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4" width="50%" align="left" showframe_time="1311" playstart="1230" playstop="1311" caption="Video zur Aufzeichnungstechnologie">}}

**Wenn Sie Text bevorzugen, lesen Sie bitte hier weiter:**

Grundsätzlich sind eine Vielzahl von Sendern gleichzeitig im elektromagnetischen Spektrum vorhanden. Im Mittelwellenband können das bei einem 9kHz-Kanalraster knapp 130 Stationen sein. Jeder Station ist eine Trägerfrequenz zugeordnet. Im Gegensatz zu Audiosignalen, bei denen nur eine Schallquelle auf ein (Mono) oder zwei (Stereo) Kanälen aufgenommen wird, sind in einem Band also viele Audiosignale gleichzeitig präsent, indem sie auf ihre jeweiligen Trägerfrequenzen aufmoduliert werden. Das ist in Abb. 1 schematisch dargestellt: Jeder Sender, der auf der Radioskala (links oben) eingestellt werden kann, entspricht einer Spitze im gesamten MW-Spektrum, hier zwischen 500 und 1700 kHz (unten). Der Rundfunkempfänger wählt dabei genau diejenige 'Spitze' aus, die dem eingestellten Sender entspricht (rechts oben), und demoduliert das Signal. So ist nur ein Kanal hörbar, obwohl natürlich weiterhin alle gleichzeitig am Antenneneingang anliegen.


<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_1.png"
  style="max-width: 100%; height: auto;"
/>


*Abb. 1: Sender und deren Signale im gesamten MW-Spektrum* 

Will man dem Radio nun ein adäquates Antennensignal anbieten, das in der Vergangenheit einmal existiert hat, so muss man also in jener Vergangenheit das Gesamtspektrum in seiner vollen Breite aufgezeichnet haben. Das bedeutet anstatt 2x 20 kHz für Audio eine Bandbreite von mindestens 1200 kHz. Derart breitbandige Aufnahmen können heutzutage mit speziellen Signalwandlern, sogenannten software-defined Radios (SDR) durchgeführt werden.

Die gesamte Pipeline der Aufzeichnung ist in Abb.2 dargestellt: Zunächst werden die AM-Signale über möglichst rauscharme Breitbandantennen, optional Breitband-Vorverstärker ("Anlagen") empfangen, mit SDRs digitalisiert und auf Festplatten gespeichert ("Aufzeichnung"). Danach werden die Aufzeichnungen hinsichtlich Qualität bewertet und ggf. resampled. Wenn sie als für das Archiv geeignet eingestuft werden, werden die einzelnen Sender im Band nach Möglichkeit identifiziert und annotiert. Danach werden sie auf den COHIRADIA-Server hochgeladen. Von dort kann sie jede interessierte Person herunterladen. 

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_pipeline_1.png" style="max-width: 80%; height: auto;"/>

*Abbildung 2: Aufzeichnung und Bearbeitung von Breitband-Antennensignalen für das Archiv* 

Will man diese Signale wiedergeben, benötigt man geeignete neben wiedergabefähigen Signalwandlern auch Software, die die Signale an diese senden. Solche Software wird laufend von Mitgliedern des COHIRADIA-Teams programmiert, getestet und weiterentwickelt. Abb.3 zeigt schematisch die Software-Entwicklungs-Pipeline. Alternative Projekte wurden auch außerhalb COHIRADIA von Radioliebhabern mit z.B. GNU-Radio ins Leben gerufen. 

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/breitbandaufzeichnung_pipeline_2.png" style="max-width: 80%; height: auto;"/>

*Abbildung 3: Bereitstellung von Software für das Abspielen auf analogen Radios.*

## Künstliche Generierung von Breitbandspektren (Synthese im Sinne der Jukebox)

Wie bereits im vorangegangenen Kapitel beschrieben, besteht das von einem AM-Sender ausgesendete elektromagnetische Signal aus einer sinusförmigen Trägerschwingung mit der nominellen Sendefrequenz f<sub>T</sub> und dem Nutzsignal, das dieser Trägerschwingung als Amplitudenschwankung aufgeprägt wird (siehe Abb. 4 A). Will man ein solches Signal künstlich erzeigen, hat man grundsätzlich zwei Möglichkeiten: 

1. Modulation eines analogen Signalgenerators mit einem Audiosignal
2. digitale Synthese auf einem Computer aus digitalen Audioquellen (z.B. wav, mp3, o.ä.) und anschließende Digital-Analog-Wandlung /DAC).
   
Will man ein ganzes Spektrum mit vielen nebeneinander existierenden Sendern erzeugen, muss man Einzelsignale zusammensetzen. Im Fall 1 (analog) muss man mehrere einzelne nach (1) generierte Signale mit unterschiedlichen Trägerfrequenzen zusammenaddieren, siehe Abb. 4 B. Im Fall 2 (digital) werden die Signale der Einzelsender aus den jeweiligen Audiodateien berechnet und anschließend addiert. Diese Summensignale werden im Gleichen Datenformat wie direkt aufgezeichnete Antennensignale gespeichert und bereitgestellt (siehe Abb. 4 C). Bei der Wiedergabe folgt wieder eine DA-Wandlung über den Signalwandler . 

<img src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/spektrumsgenerierung_de.png" style="max-width: 90%; height: auto;"/>

*Abbildung 4: A: Prinzip der Amplitudenmodulation. B: Generierung eines Spektrums durch Zusammenschaltung analoger Modulatoren. C: Generierung eines Spektrums durch digitale Synthese.* 



<!-- comment -->