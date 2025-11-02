---
title:  Hardware-Plattform STEMLAB125-14 oder STEMLAB125-10
---
## Benötigte Hardware

Da die Software zunächst speziell für das STEMLAB 125-14 entwickelt wurde, sind alle folgenden Beschreibungen auf dieses Gerät abgestimmt. Alternativ wurden COHIRADIA-Aufnahmen auch bereits auf dem deutlich kostengünstigeren  STEMLAB 125-10 wiedergegeben, ohne dass ein subjekiv empfundener Qualitätsverlst festgestellt wurde. Diese Variante wurde noch nicht umfassend getestet, ist aber bei guter Aussteuerung höchstwahrscheinlich für AM-Wiedergabezwecke ebenfalls ausreichend. Daher wird für die Typenbezeichnung im Folgenden STEMLAB 125-XX geschrieben, XX = 14 (uneingeschränkt empfohlen) oder XX = 10 (nicht umfassend getestet). Für Aufzeichnungszwecke empfehlen wir jedenfalls das STEMLAB 125-14.

1.	RedPitaya STEMLAB125-XX auch Grundpaket bestehend aus:
   
      * STEMLAB125-XX Hauptgerät
      * STEMLAB-Steckernetzteil
      * LAN-Kabel
      * SD-Karte mit typ. 16GB

2. Optional: Gehäuse für das STEMLAB

3. AM-Radio mit externem Eingang für ‚Antenne‘ und ‚Erde‘

4.	Steckeradapter und Koax-Kabel zum Koppeln zwischen SMA-Ausgang des Stemlab und Hf-Trenntransformator

5.	PC mit ausreichend Plattenspeicher für die Datenfiles.

6.	Hf-Trenntransformator (z.B. ein Balun) mit geeignetem Übersetzungsverhältnis vom 50&Omega;-Ausgang des STEMLAB auf das Radio. Üblicherweise funktioniert eine Impedanztransformation 1:9 bis 1:16 (Windungsverhältnis 1:3 bzw. 1:4) für typische Röhrengeräte. An sich kann jeder für den jeweiligen Frequenzbereich geeignete Balun verwendet werden, wenn Primär und Sekundärseite vollständig getrennt sind (keine gemainsame Masse !). Der Autor verwendet mittlerweile einen Ringkern FT114, Material 43 mit 15:60 Windungen, CuL 0.25 (Induktivität 120uH : 2mH), STEMLAB : Radio. 

##	Installation der Server-Software auf dem STEMLAB125-XX

Bevor das STEMLAB125-XX mit COHIRADIA in Betrieb genommen werden kann, muss die SD-Karte mit Betriebssystem und Serversoftware vorbereitet werden.
Das STEMLAB wird typischerweise mit einer SDKarte ausgeliefert, die das Betriebssystem (eine UBUNTU-Version) beinhaltet. Diese allein ermöglicht aber noch nicht die Kommunikation mit der COHIRADIA-Software auf dem PC. 

**ACHTUNG: Inzwischen wird das STEMLAB mit einer SDKarte ausgeliefert, die eine neuere Version des Betriebssystems beinhaltet, zuletzt OS2.00. Alle bisherigen COHIRADIA-Softwareversionen wurden unter Version 1.04 entwickelt, V2.00 ist aktuell nicht mit unserer Software kompatibel. Daher bitte unbedingt eine neue SD-Karte wie folgt erstellen:** 

1. Stecken Sie eine neue SD-Karte (8 GB sind ausreichend, größere Karten funktionieren natürlich ebenso) in den SD-Karten-Slot Ihres PCs (wenn vorhanden) oder in einen mit Ihrem PC verbundenen SD-Kartenleser. Sie können ggf. auch die mitgelieferte Karte überschreiben, aber die möchte man meist sicherheitshalber eher als Original aufbewahren.

2. Laden Sie das [Image-File cohiradia_STEMLAB125_v1.0.img](https://cohiradia.radiomuseum.org/download/software/cohiradia_STEMLAB125_v1.0.img) vom COHIRADIA-Softwarearchiv herunter und speichern Sie es in irgendeinem Verzeichnis.

3. schreiben Sie das Image mit einer geeigneten Software auf die SD-Karte. Unter Windows eigen sich z.B. [Win32Diskimager](https://win32diskimager.org/) oder der [Balena Etcher](https://etcher.balena.io/#download-etcher). Unter LINUX geht es direkt auf der Kommandozeile: 
Zuerst mit  `lsblk -f` die gemounteten SD-Karten-Partitionen auslesen. Diese werden z.B. als sdb1, sdb2 o.ä. gelistet. Dann die SD-Devices unmounten und das Schreiben starten
`sudo umount /dev/YOURSDDEVICE*`. YOURSDDEVICE ist dann was Ihr lsblk listet, in meinem Beispiel sbd.

Danach:

`sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync`

**ACHTUNG: dd ist mit viel Vorsicht zu benutzen. Wenn Sie das falsche Ziel angeben, kann es passieren, dass wichtige Systemdatenträger gelöscht werden. Also bitte dreimal kontrollieren, was man tut !** 

Danach sollte eine betriebsbereite Karte vorliegen. Werfen Sie sie aus und stecken Sie sie in den SD-Karten-Slot des STEMLAB.

4. Nach dem Einschieben der korrekt konfigurierte SD-Karte in den dafür vorgesehenen Slot muss man die IP-Adresse des STEMLAB ermitteln. Dafür gibt es ebenfalls unterschiedliche Möglichkeiten. Am einfachsten ist es, das STEMLAB per Ethernet-Kabel mit dem PC zu verbinden und danach die Versorgungsspannung einzuschalten. Das STEMLAB bootet und man sieht diverse LEDs flackern, bis das Blinken der roten 'Heartbeat'-LED beginnt. **ACHTUNG: Unter Windows kann es leicht passieren, dass die Verbindung über Ethernet nicht funktioniert, wenn das WLAN eingeschaltet ist. Falls die folgenden Schritte also nicht funktionieren, bitte einfach mal das WLAN am PC deaktivieren**

5. Danach einen Webbrowser (z.B. Mozilla Firefox) starten. Auf dem Webbrowser im Adressfeld

    `http://rp-######.local`

eingeben, wobei ###### für die MAC-Adresse steht (z.B. rp-f03e25.local). Die MAC-Adresse ist auf dem Ethernet-Stecker jedes STEMLAB aufgedruckt.

6. Warten bis die STEMLAB-Apps im Webbrowser geladen werden (das kann manchmal etwas dauern). <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> Der Anblick sollte etwa wie in der nebenstehenden Abbildung sein. Man sieht eine Reihe von Icons, mit denen man verschiedene Funktionen auf dem STEMLAB aufrufen kann. Für COHIRADIA ist lediglich das Icon 'System' relevant.

7. Danach den Folder „System“ durch Anklicken öffnen und dort die App „Network Manager“ aufrufen. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In diesem Manager kann nun die vom Router vergebene IP Adresse ausgelesen werden.                           

&nbsp;

&nbsp;

<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;

Diese Adresse benötigen Sie für den Betrieb der COHIRADIA-Apps, denn sie muss bei der ersten Verwendung eingetragen werden.

[Diese alternative Methode](https://redpitaya.readthedocs.io/en/latest/developerGuide/software/console/console/console.html) wird auf der Red-Pitaya-Doku-Page beschrieben, sie funktioniert über ein Terminal und eine zusätzliche USB-Konsolenverbindung. Empfohlen nur für IT-Geübte.


Danach ist das System für den Gebrauch im Sinne von COHIRADIA konfiguriert.


## Zusammenbau Der Hardware

1.	Das STEMLAB vom Router trennen und über das LAN-Kabel direkt mit der LAN-Buchse des PC verbinden. **) 

2.	SMA-Ausgangsbuchse ‚OUT1‘ über ein 50&Omega;-Koaxkabel mit der niederohmigen Seite des Hf-Trenntrafos /Baluns verbinden. 

3. Antenneneingang des AM-Radios mit der hochohmigen Seite des Hf-Trenntrafos/Baluns verbinden.

4.	Steckernetzteil  des STEMLAB am Mikro-USB-Port für ‚Power‘ anschließen. Alternativ kann das STEMLAB auch über ein geeignetes Mikro-USB-Kabel direkt von einem USB-Port des PC aus versorgt werden.

Siehe dazu auch das [Video-Tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4). Dieses bezieht sich zwar noch auf die Verwendung der allerersten RFCorder-Version 1.0 (nicht mehr unterstützt), sinngemäß können aber natürlich alle höheren Versionen verwendet werden.

**) <font size="2"> Alternativ zum LAN-Kabel kann laut Hersteller auch eine WLAN-Verbindung eingerichtet werden, wenn ein WLAN-Dongle mitgekauft wurde. Diese Option hat der Autor selbst jedoch noch nicht ausprobiert.

Als zweite Alternative kann das STEMLAB wahrscheinlich auch am Router verbleiben, allerdings müsste dann als IP-Adresse die vom Router zugewiesene benutzt werden. Dieser Modus wird vermutlich in der Praxis selten verwendet, da das zu bespielende Radio wahrscheinlich nicht gleich neben dem Router steht. Auch diese Betriebsart wurde vom Autor nicht getestet.</font>

## Wiedergabe-App vorbereiten

Für das Abspielen von Archivaufnahmen gibt es mittlerweile mehrere Software-Versionen, die von der [Software-Seite](https://www.radiomuseum.org/cohiradia/software.html) herunterladbar sind. Dabei ist zu beachten, dass der RFCorder erst ab Version 2.0 auch wav-Files abspielen kann, die erste Version kann nur das ursprünglich verwendete dat-Format erkennen. Dafür gibt es nur beim RFCorder v1.2 eine Aufnahmefunktion. Der COHIWizard 1.0 bietet neben der vollen Funktionalität des RFCorders 2.0 viele nützliche Hilfsfunktionen für fortgeschrittene COHIRADIA-Nutzer*innen. Generelle Vorgangsweise:

1. Das ZIP-File der gewünschten Software-Variante auf den PC herunterladen.

2. Das File auf ein lokales Directory (ich nenne es ~\LOCAL) entpacken. Dort werden nun das exe-File sowie einige Hilfsdateien und Icons sowie die Bedienungsanleitung als pdf angelegt.

3. Nun müssen nur noch die gewünschten AM-Breitband-Datenfiles (z.B. RM2006clip_fcorr_i16_C_lo1100_r1250_c0.dat ...) vom [Archiv](https://www.radiomuseum.org/cohiradia/#recording) heruntergeladen werden. Es empfiehlt sich, diese Files in separate Directories zu speichern.

In allen zip-Files sind auch die jeweiligen Bedienungsanleitungen enthalten. Das [Video-Tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4) ist zwar bezüglich einiger Inhalte (z.B. Benutzung von RFCorder Version 1.0) nicht mehr ganz up to date, kann aber grundsätzlich als Ergänzung zur Bedienungsanleitung hilfreich sein.


Eine genaue Zusammenfassung aller bisher getesteten Komponenten und eine Übersicht über alternative Hardware findet sich im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).


**APPENDIX: Variante 2 für die händische Installation von Betriebssystem und COHIRADIA-Software (komplizierter, eher für IT-Geübte)** 

Unter [folgendem Link](https://www.radiomuseum.org/cohiradia/SDKARTE_method2.html) kann noch eine alternative Installationsmethode gefunden werden, die aber nicht mehr als erste Wahl empfohlen wird.

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
