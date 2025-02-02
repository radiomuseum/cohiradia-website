---
title: Cohiradia Software
---
# Auswahlhilfe:

Im Wesentlichen gibt es zwei verschiedene Arten von Software, einen einfachen Player für die grundlegendsten Bedürfnisse (Wiedergabe von Aufnahmen und einfaches Resampling) und ein fortschrittlicheres Universalwerkzeug für die Wiedergabe, Aufnahme und zusätzliche Funktionen wie die Inspektion der Spektren, die Kommentierung der eigenen Aufnahme und das erweiterte Resampling. Wenn Sie nur ein einfaches, leicht zu bedienendes Wiedergabewerkzeug benötigen, dann entscheiden Sie sich für den **RFCorder**. Wenn Sie die volle Funktionalität mit vielen nützlichen Funktionen für die Nachbearbeitung von Aufnahmen haben möchten, dann entscheiden Sie sich für den <strong>COHIWizard</strong>. Der COHIWizard enthält alle Funktionen des RFCorders und wird häufiger aktualisiert. Unter Windows ist für beide Versionen eine ausführbare Version (exe) verfügbar. Der COHIWizard ist darüber hinaus ab v1.2 als offener Python-Quellcode auf [Github](https://github.com/hermy-sf/COHIWizard) sowohl für [Windows](#windows) als auch für [Linux](#linux) verfügbar. Wer den COHIWizard unter Python ausführen möchte, findet die Installationsanleitung auf dem GITHUB-Repository in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

<a id="windows"></a>
# Windows-10/11
Die exe-Versionen können als Zip-Datei heruntergeladen werden und enthalten auch ein Benutzerhandbuch. 

## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

<p style='text-align: justify;'>RFCorder v2.0 dient zur Wiedergabe von Breitbandaufzeichnungen auf analogen Rundfunkempfängern mittels des STEMLAB125-14. Die Beschreibung ist im downloadbaren zip-File mit eingepackt. Typische Features:</p>

* Aufzeichnungen können im IQ-Rohdatenformat (*.dat) , und im von den meisten namhaften SDRs verwendeten wav-Format gelesen und wiedergegeben werden.
* Man kann nun mit einem Rollbalken auf der Zeitleiste hin und herspringen, also sehr einfach unterschiedliche Stellen in der Aufnahme aufsuchen.
* Die laufende Zeit wird korrekt angezeigt, entsprechend der tatsächlichen Zeit (UTC) zum Zeitpunkt der Aufnahme. Dies funktioniert natürlich nur bei wav-Dateien, nicht bei *.dat.
* Es gibt einen logarithmischen Signalstärkeanzeiger. Falls das Signal zu schwach ist (Balken wird gelb), kann man mit dem Regler ‚Gain‘ in Grenzen (logarithmisch) nachverstärken.
* Es gibt eine Endlosabspiel-Taste.
* Es gibt einen einfachen Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit können auch alle Aufzeichnungen aus externen Archiven verwendet werden.

Für [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) und Bugreports bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.

## COHIWizard 1.2.9 (Juni 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard1.2.9_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.2.9c.zip)

<p style='text-align: justify;'> Der COHIWizard ist ein umfangreiches Programm, das neben der vollen Funktionalität des RFCorders2.0 auch viele Zusatzfunktionen bereitstellt. Diese umfassen:

* die Möglichkeit, eigene Aufnahmen zu erstellen, inklusive des automatischen Startens einer Aufnahme mittels eines Timers.
* ein einfaches Spektralanalyse-Fenster für die Bandspektren, der eine rasche statische Beurteilung von Aufnahmen ermöglicht.
* einen im Vergleich zum RFCorder 2.0 stark erweiterten Resampler für das Umcodieren von Aufnahmen, deren Samplingrate nicht STEMLAB-kompatibel sind. Im Gegensatz zum RFCorder2.0 können ganz beliebige Bereiche des Spektrums ausgeschnitten werden. Auch ganze Serien zusammengehörender wav-Files können nun auf einmal resampelt werden.
* ein Annotationstool, das dabei unterstützen kann, die Metadaten-Files halbautomatisch zu generieren. Mit enthalten ist hier auch ein Generator für die yaml-Files, die zwecks Annotation auf dem COHIRADIA-Server erzeugt werden müssen.

Letzteres Feature funktioniert allerdings derzeit erst für Europa und USA sowie Neuseeland, da die Referenztabellen für andere Zonen noch nicht eingebaut wurde.</p>

</p>

## COHIWizard 1.3.3 (Jänner 2025, erste stabile Version)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1_3_3_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.3.3.zip)

Diese Version beinhaltet neben einigen kleinen Änderungen (z.B. Einbau eines Monitors für das gerade abgespielet Spektrum) und etlichen Bugfixes ein wesentliches neues Modul: Den <strong>Synthesizer</strong>. Man findet ihn unter einem neuen Tab ganz rechts. Mit diesem Tool ist es möglich, eigene Hf-Bänder mit individuell zusammengestellten Playlisten beliebiger Audios im wav- oder mp3-Format zusammenzumischen. Man kann so z.B. ein Mittelwellenband mit Musik aus den 60er-Jahren und/oder Sprachdokumenten nach eigenem Bedarf zusammenstellen und es genau so abspielen, wie eine der originalen Aufzeichnungen aus dem Archiv. Wie das aussehen kann, zeigt etwa das [Youtube-Video](https://www.youtube.com/watch?v=NR0I252d4oQ). Eine detaillierte Bedienungsanleitung ist auf Englisch verfügbar (im Installations-zip-File enthalten). Zusätzlich existiert ein kleines [Video-Tutorial](https://cohiradia.radiomuseum.org/download/software/Tutorial_synthesizer_v0.mp4) für eine frühe Vorgängerversion, das zwar etliche Features noch nicht enthält, den Einstieg aber evt. erleichtert. Version 1.3.3 ist noch nicht sehr umfassend getestet worden, daher bitte um entsprechende Bug-Reports. Hier ein optischer Vorgeschmack:
<img src="https://cohiradia.radiomuseum.org/download/software/Synthesizer_Screenshot_v0.PNG" width="400" height="200" />

<a id="linux"></a>
# LINUX
Die Python-Version wurde unter Debian 10 erfolgreich gestartet, aber noch nicht ausführlich getestet- Mit dem Player konnten Hf-Signale erfolgreich abgespielt werden und mit dem Synthesizer konnten erfolgreich korrekte SDR-wav-Dateien erstellt werden. Auch eine Annotation mit dem Annotator wurde an einer Aufzeichnung exemplarisch durchgeführt. Umfangreichere Tests werden in der Zukunft durchgeführt werden.

Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard). Genauere Hinweise finden sich in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

Wenn Sie ein lokales git verwenden, können Sie auch auf den Branch cohiwizard_v1.3 zugreifen, der der aktuelle Entwicklungsbranch ist und als experimentell eingestuft werden muss.

