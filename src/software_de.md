---
title: Cohiradia Software
---
# Auswahlhilfe:

Wenn Sie lediglich ein einfaches, leicht bedienbares Wiedergabewerkzeug benötigen, können Sie den älteren **RFCorder** benutzen. Dieser Player ermöglicht Wiedergabe von Aufnahmen auf dem STEMLAB 125 und einfaches Resampling. Er wird allerdings nicht weiterentwickelt und wird daher keine zukünftige Unterstützung für alternative Hardware bieten. Wenn Sie ein laufend gewartetes Universalwerkzeug mit vielen Zusatzfunktionen bevorzugen, empfiehlt sich der <strong>COHIWizard</strong>. Er bietet alle Funktionen des RFCorders (Wiedergabe, Aufnahme) und darüber hinaus nützliche Werkzeuge etwa zur Inspektion der Spektren, zur Kommentierung der eigenen Aufnahme und zum erweiterten Resampling. Allerdings benötigt er etwas mehr Speicherplatz und für bestimmte Funktionen (z.B. Resampling) einiges an CPU-Leistung. Unter Windows ist für beide Versionen eine ausführbare Version (exe) verfügbar. Der COHIWizard ist darüber hinaus ab v1.2 als offener Python-Quellcode auf [Github](https://github.com/hermy-sf/COHIWizard) sowohl für [Windows](#windows) als auch für [Linux](#linux) verfügbar. Wer den COHIWizard unter Python ausführen möchte, findet die Installationsanleitung auf dem GITHUB-Repository in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

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
* Es gibt einen einfachen Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit können auch alle Aufzeichnungen aus externen Archiven verwendet werden. Dieser hat aber nicht die volle Funktionalität des Resamplers im COHIWizard.

Für [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) und Bugreports bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.



<a id="linux"></a>
# LINUX
Die Python-Version wurde unter Debian 10 erfolgreich gestartet, aber noch nicht ausführlich getestet- Mit dem Player konnten Hf-Signale erfolgreich abgespielt werden und mit dem Synthesizer konnten erfolgreich korrekte SDR-wav-Dateien erstellt werden. Auch eine Annotation mit dem Annotator wurde an einer Aufzeichnung exemplarisch durchgeführt. Umfangreichere Tests werden in der Zukunft durchgeführt werden.

Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard). Genauere Hinweise finden sich in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

Wenn Sie ein lokales git verwenden, können Sie auch auf den Branch cohiwizard_v1.3 zugreifen der der aktuelle Entwicklungsbranch für Version 1.3. 

<a id="experimentelle Versionen"></a>

# Experimentelle Versionen

Coming soon: Beta-Version 2.0 mit Unterstützung eines USB-VGA-Dongles als alternative Wiedergabe-Hardware. Release geplant bis Ende März 2025.

Wenn Sie ein lokales git und die Source-Codes verwenden, können Sie jetzt bereits auf den Branch cohiwizard_v2.0 zugreifen der der aktuelle Entwicklungsbranch für Version 2.0 ist und als experimentell eingestuft werden muss.
