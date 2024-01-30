---
title:  Hardware-Plattform STEMLAB125-14
---
## Benötigte Hardware

(1)	RedPitaya STEMLAB125-14 Grundpaket bestehend aus:
* STEMLAB125-14 Hauptgerät
* STEMLAB-Steckernetzteil 
* LAN-Kabel
* SD-Karte mit typ. 16GB 
(1) Optional: Gehäuse für das STEMLAB
(3)	AM-Radio mit externem Eingang für ‚Antenne‘ und ‚Erde‘
(4)	Steckeradapter und Koax-Kabel zum Koppeln zwischen SMA-Ausgang des Stemlab und Hf-Trenntransformator
(5)	PC mit ausreichend Plattenspeicher für die Datenfiles.
(6)	Hf-Trenntransformator (z.B. ein Balun) mit geeignetem Übersetzungsverhältnis vom 50-Ausgang des STEMLAB auf das Radio. Üblicherweise funktioniert eine Impedanztransformation 1:9 bis 1:16 (Windungsverhältnis 1:3 bzw. 1:4) für typische Röhrengeräte. An sich kann jeder für den jeweiligen Frequenzbereich geeignete Balun verwendet werden, wenn Primär und Sekundärseite vollständig getrennt sind (keine gemainsame Masse !) Der Autor verwendet in seinem Video-Tutorial einen Schalenkerntrafo mit Windungszahlverhältnis 1:4, Induktivität auf der niederohmigen Seite 64H, Induktivität auf der hochohmigen Seite (Radio): ca 1 mH. 

##	INSTALLATION DER SOFTWARE AUF DEM STEMLAB125-14

Normalerweise wird beim Kauf eines STEMLAB125-14 eine SD-Karte mit dem Betriebssystem (Ubuntu) mitgeliefert. Diese muss man nun in den SD-Kartenslot des STEMLAB einschieben. Sollte man nicht über diese SD-Karte verfügen, muss man sich selbst eine erstellen, die Anleitung dazu sowie die  benötigte  Image-Datei findet sich auf der 
[Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html)
Danach kann man das STEMLAB mit dem Internet verbinden und ein Installationsskript aufrufen, das freundlicherweise von Ueli Kurmann erstellt wurde. Die Verbindung kann entweder per Ethernet-Kabel oder per WLAN-Dongle über einen gängigen Router erfolgen. Dann müssen folgende Schritte unternommen werden:

(1)	Auf dem PC einen Webbrowser (z.B. Mozilla Firefox) starten. Auf dem Webbrowser im Adressfeld http://rp-######.local eingeben, wobei ###### für die MAC-Adresse steht (z.B. rp-f03e25.local). Die MAC-Adresse ist auf dem Ethernet-Stecker jedes STEMLAB aufgedruckt.
 
(2)	Warten bis die STEMLAB-Apps im Webbrowser geladen werden (das kann manchmal etwas dauern). Der Anblick sollte etwa wie in der nebenstehenden Abbildung sein.


Eine genaue Zusammenfassung aller bisher getesteten Komponenten und eine Übersicht über alternative Hardware findet sich im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).

<!-- comment -->
