---
title: Grundlagen der Breitbandwiedergabe
linkTitle: Grundlagen der Breitbandwiedergabe
date: 2026-01-01
weight: 4
description: >
  Detaillierte Beschreibung der Methoden, die die Breitbandwiedergabe ermöglichen.
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

## Spektren mit Webradio-Streams und lokalen Audiodateien

Die in Abb. 4 C gezeigte digitale Synthese ist nicht auf historische Tonaufnahmen beschränkt. Als Audioquellen für die einzelnen Träger kommen sowohl lokale Audiodateien als auch Webradio-Streams in Frage. Grundsätzlich gibt es zwei Arten der Verarbeitung:

1. **Offline-Synthese (lokale Audiodateien):** Aus beliebigen Audiodateien (z. B. wav oder mp3) wird vorab ein komplettes Spektrum berechnet und – wie ein aufgezeichnetes Antennensignal – als IQ-Datei gespeichert. Jede Audiodatei wird dabei auf einen eigenen Träger mit frei wählbarer Frequenz aufmoduliert. Diese Variante bietet der Synthesizer des [COHIWizard](/de/docs/documentation/software/#cohiwizard). Die entstehende Datei kann anschließend beliebig oft und mit jeder COHIRADIA-Abspielsoftware wiedergegeben werden.

2. **Echtzeit-Synthese (Webradio-Streams und lokale Audiodateien):** Hier werden die Audiodaten laufend gelesen bzw. empfangen und decodiert, in Echtzeit auf ihre jeweiligen Träger aufmoduliert, addiert und ohne Zwischendatei direkt an den Signalwandler übergeben. Bei Live-Inhalten aus dem Internet ist dies der einzig mögliche Weg, da eine Vorabberechnung nicht möglich ist. Auf diese Weise lassen sich aktuelle Radioprogramme – etwa Sender mit Musik aus der Blütezeit des Röhrenradios – auf einem historischen Empfänger hören, so als würden sie auf Mittelwelle ausgestrahlt. Diese Betriebsart bietet der [COHI-Player](/de/docs/documentation/software/#cohi-player) (COHI-Stream). Jeder Träger wird dabei aus einer Stream-Adresse oder einer M3U-Playlist gespeist; eine solche Playlist kann neben Internet-Adressen auch lokale Audiodateien enthalten. So können eigene Audioinhalte ohne vorherige Berechnung einer IQ-Datei direkt als Sender ausgestrahlt werden.

Beide Ansätze lassen sich auch mit einer statischen IQ-Aufzeichnung kombinieren: Der COHI-Player kann zu einer laufenden Aufzeichnung – sei es ein natürliches, von der Antenne aufgezeichnetes Spektrum oder ein offline synthetisiertes – zusätzliche, von Webradio-Streams oder lokalen Audiodateien (über M3U-Playlists) modulierte Träger **hineinmischen** (Betriebsart COHI-Player+Stream). Damit entsteht etwa ein historisches Mittelwellenband, in dem auf einigen freien Frequenzen zusätzlich aktuelle Programme oder eigene Audioinhalte zu hören sind.

Dabei sind einige technische Randbedingungen zu beachten:

* **Frequenzwahl:** Die zusätzlichen Träger sollten auf Frequenzen liegen, die in der Aufzeichnung frei sind, und untereinander ausreichend Abstand haben (im Mittelwellenbereich typischerweise 9 kHz Kanalraster), damit sich die Seitenbänder nicht überlappen. Wichtig ist außerdem, die zugemischten Träger genau auf das 9-kHz-Raster des Wellenplans zu legen, der der IQ-Aufzeichnung zugrunde liegt. Liegt ein zugemischter Träger außerhalb dieses Rasters, entstehen durch Schwebung mit dem Träger der benachbarten Rasterfrequenz hörbare **Pfeifstörungen**. Die Tonhöhe des Pfeiftons entspricht typischerweise der Differenz zwischen der Frequenz des zugemischten Trägers und der benachbarten Rasterfrequenz im IQ-Spektrum – ein Träger auf 1000 kHz neben einem Sender auf der Rasterfrequenz 999 kHz erzeugt also z. B. einen Pfeifton von 1 kHz.
* **Audiobandbreite:** Die Audiobandbreite jedes Trägers wird begrenzt (z. B. auf 4,5 kHz), was der Bandbreite damaliger AM-Sender entspricht und Störungen benachbarter Kanäle vermeidet.
* **Rechenleistung:** Da die Modulation in Echtzeit erfolgt, ist die Zahl gleichzeitiger Träger durch die Rechenleistung begrenzt – beim Raspberry Pi 4 auf einige Dutzend, beim Raspberry Pi 5 entsprechend mehr. Beim fl2k-Dongle, der anders als das STEMLAB keine eigene Signalverarbeitung (FPGA) besitzt, sind die Grenzen enger (siehe [Plattformen und Leistungsfähigkeit](/de/docs/documentation/software/#cohi-player)).
* **Netzwerk:** Für eine unterbrechungsfreie Wiedergabe von Webradio-Streams ist eine stabile Internetverbindung nötig, am besten über LAN-Kabel.
