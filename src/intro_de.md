---
title: Cohiradia
card1:
  name: Aufnahmen
  desc: "Download von Aufnahmen."
  link: "#recording"
card2:
  name: "Report 2023"
  desc: "Der Jahresbericht 2023."
  link: "https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf"
card3:
  name: Dokumentationen
  desc: "Download der Dokumentationen."
  link: "https://www.radiomuseum.org/cohiradia/documentation.html"
card4:
  name: Software
  desc: "Download von Software."
  link: "https://www.radiomuseum.org/cohiradia/software.html"
banner: https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/intropage_zierband2.png
---

## Einführung

<div style="float: left; margin-right: 15px;">
  <iframe width="320" height="180" src="https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4"
          frameborder="0" allowfullscreen></iframe>
</div>

Stellen Sie sich vor, Sie könnten auf Ihrem historischen Radioempfänger jederzeit alle Sender des Mittelwellenbandes an einem Tag im Jahr 2006 durchstimmen und anhören, so als ob alle enthaltenen Stationen gerade jetzt senden würden. 
Klarerweise sollte die Wiedergabe nicht auf einer künstlichen Montage, sondern auf einer authentischen historischen Aufzeichnung beruhen. Das entspricht wohl dem Wunsch vieler Sammler, deren schöne und wertvolle Geräte aufgrund der rasch fortschreitenden endgültigen Abschaltung von AM-Sendern zunehmend ‚stumm‘ bleiben werden. Genau diesen Wunsch erfüllt das Projekt COHIRADIA, wie dieses [Demo-Video](https://cohiradia.radiomuseum.org/download/COHIRADIA_Demovideo_v1.mp4) zeigt.



COHIRADIA steht als Akronym für **CO**nservation of **HI**storical **RA**diofrequency bands by **DI**gital **A**rchiving (Konservierung historischer Radiofrequenzbänder durch digitale Archivierung).



## Ziele
COHIRADIA verfolgt im Wesentlichen zwei Ziele:

1) interessierten Rundfunkfreunden und Sammlern die Möglichkeit zu geben, auf historischen Radioempfängern Original‐Radiosignale abzuspielen, die in der Vergangenheit aufgezeichnet worden sind. Diese Signale sollen nicht nur einen einzelnen Sender beinhalten, sondern ein ganzes Frequenzband (z.B. Mittelwelle) mit allen darin enthaltenen Rundfunkstationen auf den korrekten, zum Aufnahmezeitpunkt bestehenden Trägerfrequenzen. Damit können alle Sender auf dem Radioempfänger wieder durchgestimmt werden.

2) aktuelle Rundfunkbänder insbesondere im AM-Bereich an verschiedenen Stellen weltweit aufzuzeichnen, um die noch existierende Landschaft aktiver Sender rechtzeitig in Archivdateien abzubilden, bevor die Technologie endgültig ausgestorben ist.

## Technische Lösung
Ermöglicht wird dies durch die Aufzeichnung und Wiedergabe digitalisierter Hochfrequenzsignale mittels Software-defined Radios (SDRs). Breitbandige Aufzeichnung direkt von einer Antenne ist mittlerweile relativ einfach mit mehreren auf dem Markt befindliche SDRs möglich, die Wiedergabe erfordert allerdings SDRs mit Transmit-Ausgang. COHIRADIA stellt dafür eine Plattform bereit, die auf dem STEMLAB125‐14 von RedPitaya beruht. Dieses bietet mit 14 Bit ADC-Auflösung und 125MS/s Samplingrate eine ausgezeichnete Aufnahme- und Wiedergabequalität. Auch das deutlich billigere STEMLAB125-10 wurde bereits versuchsweise für Playback eingesetzt, allerdings nicht umfassend getestet. Alternative TX-fähige SDRS mit ähnlichen oder besseren Leistungsdaten existieren ebenfalls. 

Die Aufzeichnungen können von jeder Person abgespielt werden die ebenfalls über ein STEMLAB125‐14 oder ein geeignetes TX-fähiges SDR verfügt. Die Verwendung eines einheitlichen Datenformats garantiert dabei die Austauschbarkeit zwischen verschiedenen Plattformen.

Um in möglichst kurzer Zeit ein reichhaltiges Archiv aufzubauen, werden InteressentInnen eingeladen, eigene Aufzeichnungen zu machen und die Daten dem Radiomuseum zur Verfügung zu stellen bzw. über das erfolgreiche Abspielen von Dateien auf historischen Radio-Geräten zu berichten. Auch kreative Ideen für anderweitige Anwendungen (Aktivitäten, Museen, ...) sind sehr willkommen.

Bei Interesse sind genauere Details zur verwendeten Technik, Software und den Qualitätskriterien im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf) nachzulesen.

Die ältesten bisher existierenden Aufzeichnungen auf MW und KW wurden vom Initiator in den Jahren 2006 – 2009 analog auf einem Videorecorder erstellt und 2021 digitalisiert. Alle weiteren Aufnahmen, besonders ab 2015 wurden direkt digital von verschiedenen an COHIRADIA mitwirkenden Radioamateuern produziert, schwerpunktmäßig auf Lang‐, Mittel- und Kurzwelle bis 30 MHz. Auf den älteren Aufnahmen finden sich noch viele Europäische Sender, die mittlerweile abgeschaltet worden sind.

Für das Abspielen der Datenfiles sowie für die Erstellung eigener Aufnahmen auf dem STEMLAB125-14 wurde Software in Python erstellt und ist für Windows10 als exe-Programm sowie für LINUX als offener Source-Code unter GITHub verfügbar. Nähere Informationen hierzu finden sich auf der 'Software'-Seite.

* [Beschreibungen für die Installation der nötigen Hard- und Software](https://www.radiomuseum.org/cohiradia/hardware.html) 
* [Verfügbare Software‐Installationspakete](https://www.radiomuseum.org/cohiradia/software.html)
* [Datenfiles aus archivierten Aufnahmen](https://www.radiomuseum.org/cohiradia/#recording)

## Kontakt
Der Projektkoortinator von COHIRADIA ist Hermann Scharfetter. Als Mitglied des rmorg können Sie über sein [Profil](/dsp_profile.cfm?Member_Id=3642), als Gast per [email](mailto:hermann.scharfetter@gmail.com) gerne mit ihm in Kontakt treten um z.B. Fragen zu stellen, eigene Aufnahmen für das Archiv vorzuschlagen oder das Projekt gemeinsam mit ihm weiterzuentwickeln.

## COHI Jukebox

<p style='text-align: justify;'>Leider gibt es gerade aus der Frühzeit des Rundfunks bis herauf in die 80er Jahre praktisch keine Original-Aufzeichnungen von Hf-Breitbandsignalen im Sinne von COHIRADIA.
Nun wäre es aber wünschenswert, gerade auf z.B. Radiogeräten der 20 - 50er Jahre Signale wiedergeben zu können, die zumindest von den Inhalten her zu diesen Geräten 'passen'. Die Rubrik 

* [COHI Jukebox](https://www.radiomuseum.org/dsp_cohiradia.cfm?synthetic)

versucht sich diesem Thema zu nähern, indem sie synthetische AM-Bänder im Bereich der Lang- und Mittelwelle zur Verfügung stellt, die auf einer Vielzahl von üblichen Trägerfrequenzen Inhalte und Musik der damaligen Zeit aufmoduliert haben. </p>


## Weitere Archive
Neben COHIRADIA sind noch folgende Archive bekannt, die ebenfalls interessantes Breitbandmaterial beinhalten:

* [My DX Travel Logs](https://www.donmooredxer.com)  
  Viele lateinamerikanische Aufzeichnungen und ein paar LW-Aufnahmen auf denen auch europäische Sender auftauchen. 
* [The Radio Spectrum Archive](https://spectrumarchive.org)  
  Aufzeichnungen aus USA, z.T digitalisierte Analog-Aufnahmen mit Videorecordern bis zurück nach 1986
* [Perseus WAV Files by Günter Lorenz](http://pira.fmlist.org/perseus/)  
   Europäisches Archiv mit eher kurzen Sequenzen ab 2009

## Interessante Links auf andere Projekte:
Im Kontext mit COHIRADIA gibt es inzwischen einige Aktivitäten, bei denen Aufzeichnungen aus unserem Archiv eingesetzt werden:

* [Radiobastler.de Projekt mit fl2k](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&postID=297313&highlight=fl2k#post297313)
  
  Hier wird ein fl2k USB-VGA Konverter vorgestellt, der auch als als [kostengünstige Alternativ-Hardware](https://osmocom.org/projects/osmo-fl2k/wiki) mit hoher Datenrate für die Abspielung von Hf-Breitbandsignalen benutzt werden kann. Obwohl die Auflösung der verbauten DACs mit 8-Bit nicht sehr hoch ist, konnte damit ein im Forum von [www.radio-bastler.de](https://www.radio-bastler.de) vorgestelltes interessantes Projekt unter Verwendung von GNU-Radio zum Abspielen von COHIRADIA-Aufzeichnungen realisiert werden. Ein toller Link für LINUX-affine Radiofreunde !
  
Die folgenden beiden Videos zeigen sehr schön die Anwendung des fl2k-Systems an zwei alten Empfängern durch Gerald Gauert, der u.a. die Ausstellung [100 Jahre Rundfunk](https://www.youtube.com/watch?v=qlJWguweo4U) im Museumshof Chörau betreut:
* [Beispielvideo Anwendung fl2k A](https://youtu.be/RRBtvOd3pog)
* [Beispielvideo Anwendung fl2k B](https://youtu.be/4jC2XtWUFI8)

