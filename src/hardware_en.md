---
title:  Hardware-Platform STEMLAB125-14
---
## Required Hardware

1. basic RedPitaya STEMLAB125-14 package consisting of:
   
      * STEMLAB125-14 main unit
      * STEMLAB plug-in power supply unit
      * LAN cable
      * SD card with typ. 16GB

2. optional: housing for the STEMLAB

3. AM radio with external input for 'antenna' and 'earth ground'

4. plug adapter and coax cable for coupling between SMA output of the Stemlab and RF isolating transformer

5. PC with sufficient disk space for the data files.

6. RF isolating transformer (e.g. a balun) with a suitable transformation ratio from the 50 output of the STEMLAB to the radio. Usually an impedance transformation 1:9 to 1:16 (turns ratio 1:3 or 1:4) works for typical tube devices. In principle, any balun suitable for the respective frequency range can be used if the primary and secondary sides are completely separated (no common ground!). The author now uses a toroidal core FT114, material 43 with 15:60 turns, CuL 0.25 (inductance 120uH : 2mH), STEMLAB : Radio. 

##	Installation of the server software on the STEMLAB125-14

Normally, an SD card with the operating system (Ubuntu) is supplied with the purchase of a STEMLAB125-14. This must now be inserted into the SD card slot of the STEMLAB. If you do not have this SD card, you have to create one yourself, the instructions for this and the required image file can be found on the 
[Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html)
You can then connect STEMLAB to the Internet and call up an installation script kindly created by Ueli Kurmann. The connection can be made either by Ethernet cable or by a WLAN dongle via a standard router. The following steps must then be taken:

1. start a web browser (e.g. Mozilla Firefox) on the PC. On the web browser in the address field
   
   `http://rp-######.local`
   
   where ###### stands for the MAC address (e.g. rp-f03e25.local). The MAC address is printed on the Ethernet connector of each STEMLAB.
 
3. wait until the STEMLAB apps are loaded in the web browser (this can sometimes take a while) <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> The view should be similar to the adjacent image. You can see a series of icons with which you can call up various functions on the STEMLAB. Only the 'System' icon is relevant for COHIRADIA.

4. Danach den Folder „System“ durch Anklicken öffnen und dort die App „Network Manager“ aufrufen. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In diesem Manager kann nun die vom Router vergebene IP Adresse ausgelesen werden.                           

&nbsp;

<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;

4. Unter Windows ein Eingabeaufforderungs-Fenster öffnen und sich per ssh auf dem STEMLAB125-15 mit der vom Router vergebenen IP-Adresse einloggen, Username und Passwort sind ‚root‘ und ‚root‘.  (Port = port22). Typischer Aufruf: 

    `ssh root@###.###.###.###, 	Password: root`

   ###.###.###.### ist die IP-Adresse.

5. Nachdem sich Ubuntu mit dem Kommandozeilen-Prompt gemeldet hat, am besten gleich ein Systemupdate mit apt update durchführen danach mit apt upgrade die Pakete installieren.

6. Nach dem Upgrade den folgenden Befehl in einer Zeile eingeben:

    `curl --silent --cookie "SCHLUESSEL=1" ht<span>tps://</span>cohiradia.radiomuseum.org/install.sh |bash`
   
    Damit führt das STEMLAB das Installationsskript aus und legt ein Directory mit den nötigen Shell-Scripts, dem Serverprogramm und dem Bit-File für das FPGA an. 

8. Nach erfolgreicher Installation das STEMLAB ordnungsgemäß herunterfahren mit dem Befehl:
`halt`
Wenn die Konsole meldet, dass die Verbindung geschlossen wurde und die rote blinkende Heartbeat-LED am STEMLAB erloschen ist kann das Netzteil des Geräts wieder abgesteckt werden

Danach ist das System für den Gebrauch im Sinne von COHIRADIA konfiguriert.


## Zusammenbau Der Hardware

1.	Das STEMLAB vom Router trennen und über das LAN-Kabel direkt mit der LAN-Buchse des PC verbinden. **) 

2.	SMA-Ausgangsbuchse ‚OUT1‘ über ein 50-Koaxkabel mit der niederohmigen Seite des Hf-Trenntrafos /Baluns verbinden. 

3. Antenneneingang des AM-Radios mit der hochohmigen Seite des Hf-Trenntrafos/Baluns verbinden.

4.	Steckernetzteil  des STEMLAB am Mikro-USB-Port für ‚Power‘ anschließen. Alternativ kann das STEMLAB auch über ein geeignetes Mikro-USB-Kabel direkt von einem USB-Port des PC aus versorgt werden.

Siehe dazu auch das [Video-Tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4). Dieses bezieht sich zwar noch auf die Verwendung der allerersten RFCorder-Version 1.0 (nicht mehr unterstützt), sinngemäß können aber natürlich alle höheren Versionen verwendet werden.

**) Alternativ zum LAN-Kabel kann laut Hersteller auch eine WLAN-Verbindung eingerichtet werden, wenn ein WLAN-Dongle mitgekauft wurde. Diese Option hat der Autor selbst jedoch noch nicht ausprobiert. 

Als zweite Alternative kann das STEMLAB wahrscheinlich auch am Router verbleiben, allerdings müsste dann als IP-Adresse die vom Router zugewiesene benutzt werden. Dieser Modus wird vermutlich in der Praxis selten verwendet, da das zu bespielende Radio wahrscheinlich nicht gleich neben dem Router steht. Auch diese Betriebsart wurde vom Autor nicht getestet.

## Wiedergabe-App vorbereiten

Für das Abspielen von Archivaufnahmen gibt es mittlerweile mehrere Software-Versionen, die von der [Software-Seite](https://www.radiomuseum.org/cohiradia/software.html) herunterladbar sind. Dabei ist zu beachten, dass der RFCorder erst ab Version 2.0 auch wav-Files abspielen kann, die erste Version kann nur das ursprünglich verwendete dat-Format erkennen. Dafür gibt es nur beim RFCorder v1.2 eine Aufnahmefunktion. Der COHIWizard 1.0 bietet neben der vollen Funktionalität des RFCorders 2.0 viele nützliche Hilfsfunktionen für fortgeschrittene COHIRADIA-Nutzer*innen. Generelle Vorgangsweise:

1. Das ZIP-File der gewünschten Software-Variante auf den PC herunterladen.

2. Das File auf ein lokales Directory (ich nenne es ~\LOCAL) entpacken. Dort werden nun das exe-File sowie einige Hilfsdateien und Icons sowie die Bedienungsanleitung als pdf angelegt.

3. Nun müssen nur noch die gewünschten AM-Breitband-Datenfiles (z.B. RM2006clip_fcorr_i16_C_lo1100_r1250_c0.dat ...) vom [Archiv](https://www.radiomuseum.org/cohiradia/#recording) heruntergeladen werden. Es empfiehlt sich, diese Files in separate Directories zu speichern.

In allen zip-Files sind auch die jeweiligen Bedienungsanleitungen enthalten. Das [Video-Tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4) ist zwar bezüglich einiger Inhalte (z.B. Benutzung von RFCorder Version 1.0) nicht mehr ganz up to date, kann aber grundsätzlich als Ergänzung zur Bedienungsanleitung hilfreich sein.


Eine genaue Zusammenfassung aller bisher getesteten Komponenten und eine Übersicht über alternative Hardware findet sich im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).

<!-- comment -->
