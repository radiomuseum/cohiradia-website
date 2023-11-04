---
title: Cohiradia
card1:
  name: Aufnahmen
  desc: "Download von Aufnahmen."
card2:
  name: "Report 2023"
  desc: "Der Jahresbericht 2023."
card3:
  name: Dokumentationen
  desc: "Download der Dokumentationen."
card4:
  name: Software
  desc: "Download von Software."
---
## Einführung
Stellen Sie sich vor, Sie könnten auf Ihrem historischen Radioempfänger jederzeit alle Sender des Mittelwellenbandes an einem Tag im Jahr 2006 durchstimmen und anhören, so als ob alle enthaltenen Stationen gerade jetzt senden würden. Klarerweise sollte die Wiedergabe nicht auf einer künstlichen Montage, sondern auf einer authentischen historischen Aufzeichnung beruhen. Das entspricht wohl dem Wunsch vieler Sammler, deren schöne und wertvolle Geräte aufgrund der rasch fortschreitenden endgültigen Abschaltung von AM-Sendern zunehmend ‚stumm‘ bleiben werden. Genau diesen Wunsch erfüllt das Projekt COHIRADIA, wie dieses Demovideo zeigt.

COHIRADIA steht als Akronym für **CO**nservation of **HI**storical **RA**diofrequency bands by **DI**gital Archiving (Konservierung historischer Radiofrequenzbänder durch digitale Archivierung).

## Ziele
COHIRADIA verfolgt im Wesentlichen zwei Ziele:

1) interessierten Rundfunkfreunden und Sammlern die Möglichkeit zu geben, auf historischen Radioempfängern Original‐Radiosignale abzuspielen, die in der Vergangenheit aufgezeichnet worden sind. Diese Signale sollen nicht nur einen einzelnen Sender beinhalten, sondern ein ganzes Frequenzband (z.B. Mittelwelle) mit allen darin enthaltenen Rundfunkstationen auf den korrekten, zum Aufnahmezeitpunkt bestehenden Trägerfrequenzen. Damit können alle Sender auf dem Radioempfänger wieder durchgestimmt werden.

2) aktuelle Rundfunkbänder insbesondere im AM-Bereich an verschiedenen Stellen weltweit aufzuzeichnen, um die noch existierende Landschaft aktiver Sender rechtzeitig in Archivdateien abzubilden, bevor die Technologie endgültig ausgestorben ist.

## Technische Lösung
Ermöglicht wird dies durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Breitbandige Aufzeichnung direkt von einer Antenne ist mittlerweile relativ einfach mit mehreren auf dem Markt befindliche SDRs möglich, die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang. Der Initiator von COHIRADIA benutzt dafür das STEMLAB125‐14 von RedPitaya, das mit 14 Bit ADC-Auflösung aud 125MS/s Samplingrate eine gute Aufnahme- und Wiedergabequalität bietet. Alternative TX-fähige SDRS mit ähnlichen oder besseren Leistungsdaten existieren ebenfalls.

Die Aufzeichnungen können von jeder Person abgespielt werden die ebenfalls über ein STEMLAB125‐14 oder ein geeignetes TX-fähiges SDR verfügt. Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.

Um in möglichst kurzer Zeit ein reichhaltiges Archiv aufzubauen, werden InteressentInnen eingeladen, eigene Aufzeichnungen zu machen und die Daten dem Radiomuseum zur Verfügung zu stellen bzw. über das erfolgreiche Abspielen von Dateien auf historischen Radio-Geräten zu berichten. Auch kreative Ideen für anderweitige Anwendungen (Aktivitäten, Museen, ...) sind sehr willkommen.

Bei Interesse sind genauere Details zur verwendeten Technik, Software und den Qualitätskriterien im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf) nachzulesen.

Die ältesten bisher existierenden Aufzeichnungen auf MW und KW wurden vom Initiator in den Jahren 2006 – 2009 analog auf einem Videorecorder erstellt und 2021 digitalisiert. Alle weiteren Aufnahmen, besonders ab 2015 wurden direkt digital von verschiedenen an COHIRADIA mitwirkenden Radioamateuern produziert, schwerpunktmäßig auf Lang‐, Mittel- und Kurzwelle bis 30 MHz. Auf den älteren Aufnahmen finden sich noch viele Europäische Sender, die mittlerweile abgeschaltet worden sind.

Für das Abspielen der Datenfiles sowie für die Erstellung eigener Aufnahmen auf dem STEMLAB125-14 wurde eine erste Softwareversion in Python erstellt und ist für Windows10 als exe-Programm verfügbar. Für die Sourcen wurde vom Autor bereits ein GITHub-Repository angelegt, eine Freigabe als open‐Source Projekt ist für die nächste Zukunft geplant.

* [Beschreibungen für die Installation der nötigen Hard- und Software](https://cohiradia.radiomuseum.org/download/docs/) 
* [Verfügbare Software‐Installationspakete](https://cohiradia.radiomuseum.org/download/software/)
* [Datenfiles aus archivierten Aufnahmen](https://cohiradia.radiomuseum.org/download/data/)

[Hermann Scharfetter](mailto:hermann.scharfetter@gmail.com) initiierte das Projekt COHIRADIA und ist die treibende Kraft dahinter. Über sein [Profil](/dsp_profile.cfm?Member_Id=3642) können sie gerne mit ihm in Kontakt treten und das Projekt gemeinsam mit ihm weiterentwickeln.

## Weitere Archive
Neben COHIRADIA sind noch folgende Archive bekannt, die ebenfalls interessantes Breitbandmaterial beinhalten:

* [My DX Travel Logs](https://www.donmooredxer.com)  
  Viele lateinamerikanische Aufzeichnungen und ein paar LW-Aufnahmen auf denen auch europäische Sender auftauchen. 
* [The Radio Spectrum Archive](https://spectrumarchive.org)  
  Aufzeichnungen aus USA, z.T digitalisierte Analog-Aufnahmen mit Videorecordern bis zurück nach 1986
* [Perseus WAV Files by Günter Lorenz](http://pira.fmlist.org/perseus/)  
   Europäisches Archiv mit eher kurzen Sequenzen ab 2009