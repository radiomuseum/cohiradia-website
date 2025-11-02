---
title:  Hardware-Plattform STEMLAB125-14 oder STEMLAB125-10
---
## Variante 2 für die händische Installation von Betriebssystem und COHIRADIA-Software (komplizierter, eher für IT-Geübte)** 

Diese Variante ist bisherigen Nutzern der COHIRADIA-Tools bestens bekannt, hat aber seit der Einführung von OS2.00 durch RedPitaya leider Komplikationen dazubekommen. Wir empfehlen diese Variante daher nicht mehr als erste Wahl, sie ist nur hier noch der Vollständigkeit halber aufgeführt.

**ACHTUNG ! BEVOR SIE MIT DIESER METHODE BEGINNEN**: 

**Inzwischen wird das STEMLAB mit einer SDKarte ausgeliefert, die eine neuere Version des Betriebssystems beinhaltet, zuletzt OS2.00. Alle bisherigen COHIRADIA-Softwareversionen wurden unter Version 1.04 entwickelt, V2.00 ist aktuell nicht mit unserer Software kompatibel. Für COHIRADIA muss immer die Version 1.04-28 verwendet werden.** 

Sollte beim Kauf eines neuen STEMLAB also die Version 2.00 vorkonfiguriert sein, so muss eine eigene SD-Karte mit Version 1.04-28 angefertigt werden. Den Link auf die entsprechende Image-Datei sowie die nötigen Anleitungen finden Sie auf dieser [Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html). Wir bemühen uns, in Zukunft unsere Software auch für V2.00 umzurüsten.

Nach dem Einschieben der korrekt konfigurierte SD-Karte in den dafür vorgesehenen Slot muss man das STEMLAB mit dem Internet verbinden und ein Installationsskript aufrufen, das freundlicherweise von Ueli Kurmann erstellt wurde. Die Verbindung kann entweder per Ethernet-Kabel oder per WLAN-Dongle über einen gängigen Router erfolgen. Dann müssen die Schritte 5 - 7 von Variante 1 unternommen werden:

1. Auf dem PC einen Webbrowser (z.B. Mozilla Firefox) starten. Auf dem Webbrowser im Adressfeld
   
   `http://rp-######.local`
   
   eingeben, wobei ###### für die MAC-Adresse steht (z.B. rp-f03e25.local). Die MAC-Adresse ist auf dem Ethernet-Stecker jedes STEMLAB aufgedruckt.
 
3. Warten bis die STEMLAB-Apps im Webbrowser geladen werden (das kann manchmal etwas dauern). Man sieht eine Reihe von Icons, mit denen man verschiedene Funktionen auf dem STEMLAB aufrufen kann. Für COHIRADIA ist lediglich das Icon 'System' relevant.

4. Danach den Folder „System“ durch Anklicken öffnen und dort die App „Network Manager“ aufrufen. In diesem Manager kann nun die vom Router vergebene IP Adresse ausgelesen werden.                           

&nbsp;

5. Unter Windows ein Eingabeaufforderungs-Fenster öffnen und sich per ssh auf dem STEMLAB125-15 mit der vom Router vergebenen IP-Adresse einloggen, Username und Passwort sind ‚root‘ und ‚root‘.  (Port = port22). Typischer Aufruf: 

    `ssh root@###.###.###.###, 	Password: root`

   ###.###.###.### ist die IP-Adresse.

6. Nachdem sich Ubuntu mit dem Kommandozeilen-Prompt gemeldet hat, am besten gleich ein Systemupdate mit `apt update` durchführen danach mit `apt upgrade` die Pakete installieren.

7. Nach dem Upgrade den folgenden Befehl in einer Zeile eingeben:

    `curl --silent --cookie "SCHLUESSEL=1" https://cohiradia.radiomuseum.org/install.sh |bash`
   
    Damit führt das STEMLAB das Installationsskript aus und legt ein Directory mit den nötigen Shell-Scripts, dem Serverprogramm und dem Bit-File für das FPGA an. 

8. Nach erfolgreicher Installation das STEMLAB ordnungsgemäß herunterfahren mit dem Befehl:
`halt`
Wenn die Konsole meldet, dass die Verbindung geschlossen wurde und die rote blinkende Heartbeat-LED am STEMLAB erloschen ist, kann das Netzteil des Geräts wieder abgesteckt werden

<!-- comment -->
