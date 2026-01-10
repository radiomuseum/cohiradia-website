---
title: Cohiradia Software
---
# Auswahlhilfe:

Wenn Sie lediglich ein einfaches, leicht bedienbares Wiedergabewerkzeug benötigen, können Sie den älteren **RFCorder** benutzen. Dieser Player ermöglicht Wiedergabe von Aufnahmen auf dem STEMLAB 125 und einfaches Resampling. Er wird allerdings nicht weiterentwickelt und wird daher keine zukünftige Unterstützung für alternative Hardware bieten. Wenn Sie ein laufend gewartetes Universalwerkzeug mit vielen Zusatzfunktionen bevorzugen, empfiehlt sich der <strong>COHIWizard</strong>. Er bietet alle Funktionen des RFCorders (Wiedergabe, Aufnahme) und darüber hinaus nützliche Werkzeuge etwa zur Inspektion der Spektren, zur Kommentierung der eigenen Aufnahme und zum erweiterten Resampling. Allerdings benötigt er etwas mehr Speicherplatz und für bestimmte Funktionen (z.B. Resampling) einiges an CPU-Leistung. Unter Windows ist für beide Versionen eine ausführbare Version (exe) verfügbar. Der COHIWizard ist darüber hinaus ab v1.2 als offener Python-Quellcode auf [Github](https://github.com/hermy-sf/COHIWizard) sowohl für [Windows](#windows) als auch für [Linux](#linux) verfügbar. Wer den COHIWizard unter Python ausführen möchte, findet die Installationsanleitung auf dem GITHUB-Repository in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md). Wer die neueste Version ausprobieren möchte, sei auf die Rubrik [Experimentelle Version](#experimentelleV) verwiesen.

<a id="windows"></a>
# Windows-10/11
Die exe-Versionen können als Zip-Datei heruntergeladen werden und enthalten auch ein Benutzerhandbuch. 

## COHIWizard 1.2.9 (Juni 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard1.2.9_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.2.9c.zip)

<p style='text-align: justify;'> Der COHIWizard ist ein umfangreiches Programm, das neben der vollen Funktionalität des RFCorders2.0 auch viele Zusatzfunktionen bereitstellt. Wichtigste aktuelle Features:

* Abspielen und Aufzeichnen können im IQ-Format, wobei sowohl das von den meisten namhaften SDRs verwendete erweiterte wav-Format als auch ein Rohdatenformat (*.dat)unterstützt werden.
* Timer für das automatische Starten eigener Aufnahmen.
* Einfaches Navigieren in der Aufnahme mit einem Rollbalken auf der Zeitleiste sowwie >> und <<-Tasten.
* Anzeige der korrekten laufenden Zeit, entsprechend der tatsächlichen Zeit zum Zeitpunkt der Aufnahme (allerdings nur bei wav-Dateien, nicht bei *.dat).
* Logarithmischer Signalstärkeanzeiger. Falls das Signal zu schwach ist (Balken wird gelb), kann man mit dem Regler ‚Gain‘ in Grenzen (logarithmisch) nachverstärken.
* Endlosabspiel-Taste.
* Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit können auch alle Aufzeichnungen aus externen Archiven verwendet werden. Im Gegensatz zum RFCorder2.0 können ganz beliebige Bereiche des Spektrums ausgeschnitten werden. Auch ganze Serien zusammengehörender wav-Files können auf einmal resampelt werden.
* ein einfaches Spektralanalyse-Fenster für die Bandspektren, der eine rasche statische Beurteilung von Aufnahmen ermöglicht.
* ein Annotationstool, das dabei unterstützen kann, die Metadaten-Files zu eigenen Aufzeichnungen halbautomatisch zu generieren. Mit enthalten ist hier auch ein Generator für die yaml-Files, die zwecks Annotation auf dem COHIRADIA-Server erzeugt werden müssen.

Letzteres Feature funktioniert allerdings derzeit erst für Europa und USA sowie Neuseeland, da die Referenztabellen für andere Zonen noch nicht eingebaut wurde.</p>

</p>

## COHIWizard 1.3.3 (Jänner 2025, erste stabile Version)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1_3_3_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.3.3.zip)

Diese Version beinhaltet neben einigen kleinen Änderungen (z.B. Einbau eines Monitors für das gerade abgespielet Spektrum) und etlichen Bugfixes ein wesentliches neues Modul: Den <strong>Synthesizer</strong>. Man findet ihn unter einem neuen Tab ganz rechts. Mit diesem Tool ist es möglich, eigene Hf-Bänder mit individuell zusammengestellten Playlisten beliebiger Audios im wav- oder mp3-Format zusammenzumischen. Man kann so z.B. ein Mittelwellenband mit Musik aus den 60er-Jahren und/oder Sprachdokumenten nach eigenem Bedarf zusammenstellen und es genau so abspielen, wie eine der originalen Aufzeichnungen aus dem Archiv. Wie das aussehen kann, zeigt etwa das [Youtube-Video](https://www.youtube.com/watch?v=NR0I252d4oQ). Eine detaillierte Bedienungsanleitung ist auf Englisch verfügbar (im Installations-zip-File enthalten). Zusätzlich existiert ein kleines [Video-Tutorial](https://cohiradia.radiomuseum.org/download/software/Tutorial_synthesizer_v0.mp4) für eine frühe Vorgängerversion, das zwar etliche Features noch nicht enthält, den Einstieg aber evt. erleichtert. Version 1.3.3 ist noch nicht sehr umfassend getestet worden, daher bitte um entsprechende Bug-Reports. Hier ein optischer Vorgeschmack:

<img src="https://cohiradia.radiomuseum.org/download/software/Synthesizer_Screenshot_v0.PNG" width="400" height="200" />

## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

<p style='text-align: justify;'>RFCorder v2.0 dient zur Wiedergabe von Breitbandaufzeichnungen auf analogen Rundfunkempfängern mittels des STEMLAB125-14. Die Beschreibung ist im downloadbaren zip-File mit eingepackt. Typische Features:</p>

* Aufzeichnungen können im IQ-Rohdatenformat (*.dat) , und im von den meisten namhaften SDRs verwendeten wav-Format gelesen und wiedergegeben werden.
* Man kann mit einem Rollbalken auf der Zeitleiste hin und herspringen, also sehr einfach unterschiedliche Stellen in der Aufnahme aufsuchen.
* Die laufende Zeit wird korrekt angezeigt, entsprechend der tatsächlichen Zeit zum Zeitpunkt der Aufnahme. Dies funktioniert natürlich nur bei wav-Dateien, nicht bei *.dat.
* Es gibt einen logarithmischen Signalstärkeanzeiger. Falls das Signal zu schwach ist (Balken wird gelb), kann man mit dem Regler ‚Gain‘ in Grenzen (logarithmisch) nachverstärken.
* Es gibt eine Endlosabspiel-Taste.
* Es gibt einen einfachen Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit können auch alle Aufzeichnungen aus externen Archiven verwendet werden. Dieser Resampler hat aber nicht die volle Funktionalität des Resamplers im COHIWizard.




<a id="linux"></a>
# LINUX
Die Python-Version wurde unter Debian 10 erfolgreich gestartet, aber noch nicht ausführlich getestet- Mit dem Player konnten Hf-Signale erfolgreich abgespielt werden und mit dem Synthesizer konnten erfolgreich korrekte SDR-wav-Dateien erstellt werden. Auch eine Annotation mit dem Annotator wurde an einer Aufzeichnung exemplarisch durchgeführt. Umfangreichere Tests werden in der Zukunft durchgeführt werden.

Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard). Genauere Hinweise finden sich in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

Wenn Sie ein lokales git verwenden, können Sie auch auf den Branch cohiwizard_v1.3 zugreifen der der aktuelle Entwicklungsbranch für Version 1.3. 

<a id="experimentelleV"></a>

# Neueste experimentelle Version: COHIWizard 2.2.0

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_V2.1.1_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v2.2.1.zip)

Nach Überarbeitung der Player-Architektur gibt es nun eine Version 2 des COHIWizard. Dabei ist der Player-Teil des COHIWizard mit einem Gerätetreiber-System ausgestattet. Damit ist es möglich, nicht nur das STEMLAB als Aufnahme/Wiedergabegerät auszuwählen, sondern auch alternative Hardware. So können in Zukunft weitere SDRs betrieben werden, die mit den Erfordernissen für COHIRADIA kompatibel sind. Weiters wurde in V2.2.x der Synthesizer überarbeitet und mit einem deutlich schnelleren, auf ffmpeg beruhenden Modulator ausgestattet. Damit sind Synthesen eigener Breitbandfiles fast fünfmal schneller möglich als bisher. Dieses Feature hat allerdings eine geringfügig schlechtere SNR als der bisherige 'slow-mode' und ist daher vorläufig als Beta-Modul optional eingebaut. 

Bislang wurden zwei neue Geräte-Treiber als experimentelle Versionen implementiert:

(1) 'fl2k': Dabei handelt es sich um einen  [USB zu VGA-Adapter](https://osmocom.org/projects/osmo-fl2k/wiki), der von verschiedenen Usergruppen als schneller 8-Bit DAC verwendet wird und auch bei einigen Hochfrequenz-Projekten eingesetzt wurde (siehe [fl2k-COHIRADIA-Projekt](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). Mit seinen nur 8 Bit Auflösung ist dieses sehr kostengünstige Gerät natürlich kein vollwertiger Ersatz für das STEMLAB, aber es genügt für viele Wiedergabe-Standardanwendungen durchaus, wie [Beispiele](https://youtu.be/4jC2XtWUFI8) zeigen.

(2) ADALM2000: Dieser Treiber erlaubt die Wiedergabe von IQ-Files mit oberen Badngrenzfrequenzen bis zu 2.5 MHz auf dem [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). Dies ist ein im Vergleich zum STEMLAB125-14 kostengünstiges, USB-betriebenes Modul mit 2 ADC- und 2 DAC-Kanälen zu je 12 Bit Auflösung sowie einem GPIO-Port. Es kann als Oszilloskop, Funktionsgenerator oder Logikanalysator betrieben werden, erlaubt aber auch die Wiedergabe von COHIRADIA-IQ-Files. Allerdings gibt es Einschränkungen: Durch die Verwendung von USB2.0 ist die obere Grenzfrequenz mit etwa 2500 kHz limitiert. Dies genügt für LW und MW, erlaubt die Wiedergabe von KW-Aufzeichnungen aber nur mit einem Trick: Durch Einstellen eines geeigneten Wertes im Feld 'LO-Offset' (z.B. -4000kHz für das 49m-Band) kann das Signal ins Mittelwellenband des Radios heruntergemischt und abgehört werden. Erste Tests ergaben für MW und LW brauchbare Wiedergabe mit deutlich besserer Dynamik als das fl2k. Allerdings treten bei bestimmten Aufnahmen leichte Störgeräusche auf, die möglicherweise durch schlechtere Filterung/Interpolation als beim STEMLAB entstehen.

Sowohl (1) als auch (2) erfordern einen einigermaßen leistungsfähigen PC für die Umcodierung der komplexen Basisbanddaten in das für die Devices nötige Datenformat. Wir empfehlen daher weder das ADALM2000 noch das fl2k als echte Alternativen zum STEMLAB, dessen Leistung aufgrund der Auslagerung rechenintensiver Operationen auf das FPGA nach wie vor unübertroffen bleibt. Wer aber etwa bereits über ein ADALM2000 verfügt, kann dieses nun ansteuern und das Radiosignal am DAC Ausgang 1 (W1) abgreifen. 

Es ist geplant, in Zukunft weitere Treiber zu entwickeln, sofern Bedarf danach besteht. Ein mögliches Target könnte z.B. der [ADALM Pluto](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm-pluto.html) sein.

Sollte sich das neue Tool bewähren, wird es in zukünftigen Releases die alte Variante ablösen. 

Bugreports zu Version 2.2.x sind aufgrund der noch nicht sehr exzessiven Tests willkommen.

Wenn Sie ein lokales GIT und die Source-Codes verwenden, können Sie jetzt bereits auf den Branch [cohiwizard_v2.0](https://github.com/hermy-sf/COHIWizard/tree/cohiwizard_v2.2) zugreifen der der aktuelle Entwicklungsbranch für Version 2 ist und als experimentell eingestuft werden muss. Die stabile Version ist im branch 'main' verfügbar.

Für [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) und Bugreports bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.
