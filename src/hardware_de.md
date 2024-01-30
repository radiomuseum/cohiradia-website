---
title:  Hardware-Plattform STEMLAB125-14
---
## Benötigte Hardware

(1)	RedPitaya STEMLAB125-14 Grundpaket bestehend aus:
* STEMLAB125-14 Hauptgerät
* STEMLAB-Steckernetzteil 
* LAN-Kabel
* SD-Karte mit typ. 16GB
  
(2) Optional: Gehäuse für das STEMLAB

(3)	AM-Radio mit externem Eingang für ‚Antenne‘ und ‚Erde‘

(4)	Steckeradapter und Koax-Kabel zum Koppeln zwischen SMA-Ausgang des Stemlab und Hf-Trenntransformator

(5)	PC mit ausreichend Plattenspeicher für die Datenfiles.

(6)	Hf-Trenntransformator (z.B. ein Balun) mit geeignetem Übersetzungsverhältnis vom 50-Ausgang des STEMLAB auf das Radio. Üblicherweise funktioniert eine Impedanztransformation 1:9 bis 1:16 (Windungsverhältnis 1:3 bzw. 1:4) für typische Röhrengeräte. An sich kann jeder für den jeweiligen Frequenzbereich geeignete Balun verwendet werden, wenn Primär und Sekundärseite vollständig getrennt sind (keine gemainsame Masse !). Der Autor verwendet mittlerweile einen Ringkern **CHANGE mit Windungszahlverhältnis **CHANGE, Induktivität auf der niederohmigen Seite **CHANGE64H, Induktivität auf der hochohmigen Seite (Radio): ca **CHANGE mH. 

##	Installation der Server-Software auf dem STEMLAB125-14

Normalerweise wird beim Kauf eines STEMLAB125-14 eine SD-Karte mit dem Betriebssystem (Ubuntu) mitgeliefert. Diese muss man nun in den SD-Kartenslot des STEMLAB einschieben. Sollte man nicht über diese SD-Karte verfügen, muss man sich selbst eine erstellen, die Anleitung dazu sowie die  benötigte  Image-Datei findet sich auf der 
[Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html)
Danach kann man das STEMLAB mit dem Internet verbinden und ein Installationsskript aufrufen, das freundlicherweise von Ueli Kurmann erstellt wurde. Die Verbindung kann entweder per Ethernet-Kabel oder per WLAN-Dongle über einen gängigen Router erfolgen. Dann müssen folgende Schritte unternommen werden:

(1)	Auf dem PC einen Webbrowser (z.B. Mozilla Firefox) starten. Auf dem Webbrowser im Adressfeld ht<span>tp://</span>rp-######.local' eingeben, wobei ###### für die MAC-Adresse steht (z.B. rp-f03e25.local). Die MAC-Adresse ist auf dem Ethernet-Stecker jedes STEMLAB aufgedruckt.
 
(2)	Warten bis die STEMLAB-Apps im Webbrowser geladen werden (das kann manchmal etwas dauern). <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> Der Anblick sollte etwa wie in der nebenstehenden Abbildung sein. Man sieht eine Reihe von Icons, mit denen man verschiedene Funktionen auf dem STEMLAB aufrufen kann. Für COHIRADIA ist lediglich das Icon 'System' relevant.

(3) Danach den Folder „System“ durch Anklicken öffnen und dort die App „Network Manager“ aufrufen. <img align="right" width="200" height="200" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2_sm.png" /> <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> In diesem Manager kann nun die vom Router vergebene IP Adresse ausgelesen werden.                           

&nbsp;

&nbsp;

&nbsp;

&nbsp;

(4)	Unter Windows ein Eingabeaufforderungs-Fenster öffnen und sich per ssh auf dem STEMLAB125-15 mit der vom Router vergebenen IP-Adresse einloggen, Username und Passwort sind ‚root‘ und ‚root‘.  (Port = port22). Typischer Aufruf: 

ssh root@###.###.###.###, 	Password: root

###.###.###.### ist die IP-Adresse.

(5)	Nachdem sich Ubuntu mit dem Kommandozeilen-Prompt gemeldet hat, am besten gleich ein Systemupdate mit apt update durchführen danach mit apt upgrade die Pakete installieren.

(6)	Nach dem Upgrade den folgenden Befehl in einer Zeile eingeben:
curl --silent --cookie "SCHLUESSEL=1" https://cohiradia.radiomuseum.org/install.sh |bash
Damit führt das STEMLAB das Installationsskript aus und legt ein Directory mit den nötigen Shell-Scripts, dem Serverprogramm und dem Bit-File für das FPGA an. 
(7)	Nach erfolgreicher Installation das STEMLAB ordnungsgemäß herunterfahren mit dem Befehl:
halt
Wenn die Konsole meldet, dass die Verbindung geschlossen wurde und die rote blinkende Heartbeat-LED am STEMLAB erloschen ist kann das Netzteil des Geräts wieder abgesteckt werden

Danach ist das System für den Gebrauch im Sinne von COHIRADIA bereit.





Eine genaue Zusammenfassung aller bisher getesteten Komponenten und eine Übersicht über alternative Hardware findet sich im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).

<!-- comment -->
