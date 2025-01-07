---
title: Cohiradia Software
---
# Auswahlhilfe:

Im Wesentlichen gibt es zwei verschiedene Arten von Software, einen einfachen Player für die grundlegendsten Bedürfnisse (Wiedergabe von Aufnahmen und einfaches Resampling) und ein fortschrittlicheres Universalwerkzeug für die Wiedergabe, Aufnahme und zusätzliche Funktionen wie die Inspektion der Spektren, die Kommentierung der eigenen Aufnahme und das erweiterte Resampling. Wenn Sie nur ein einfaches, leicht zu bedienendes Wiedergabewerkzeug benötigen, dann entscheiden Sie sich für den **RFCorder**, am besten in der Version 2.0. Wenn Sie die volle Funktionalität mit vielen nützlichen Funktionen für die Nachbearbeitung von Aufnahmen haben möchten, dann entscheiden Sie sich für den <strong>COHIWizard</strong>. Der COHIWizard enthält alle Funktionen des RFCorders und wird häufiger aktualisiert. Unter Windows ist für beide Versionen eine ausführbare Version (exe) verfügbar. Der COHIWizard ist darüber hinaus ab v1.2 als offener Python-Quellcode auf [Github](https://github.com/hermy-sf/COHIWizard) sowohl für [Windows](#Windows-10/11) als auch für [Linux](#LINUX) verfügbar. Wer den COHIWizard unter Python ausführen möchte, findet die Installationsanleitung auf dem GITHUB-Repository in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

# Windows-10/11

Die exe-Versionen können als Zip-Datei heruntergeladen werden und enthalten auch ein Benutzerhandbuch. 

## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

<p style='text-align: justify;'>RFCorder v2.0 dient zur Wiedergabe von Breitbandaufzeichnungen auf analogen Rundfunkempfängern mittels des STEMLAB125-14. Die Beschreibung ist im downloadbaren zip-File mit eingepackt. Diese Version erlaubt zwar derzeit im Gegensatz zur Vorgänger-Version v1.2 keine eigenen Aufzeichnungen, dafür gibt es eine Reihe nützlicher neuer Features:</p>

* Man kann neben Aufzeichnungen im ursprünglich für COHIRADIA verwendeten Rohdatenformat (*.dat) nun auch solche im wav-Format abspielen. Das ist sinnvoll, da alle namhaften SDRs dieses Format verwenden und daher alle externen Archive von Breitbanddateien wav-Dateien beinhalten. Daher werden alle neuen Aufnahmen im Archiv mittlerweile ausschließlich mit wav-Header generiert. Damit können die Files auch mit gängiger SDR-Software wie SDRUno oder SDR# auf dem PC wiederzugeben und Metadaten können viel kompakter an den RFCorder übergeben und dargestellt werden.
* Man kann nun mit einem Rollbalken auf der Zeitleiste hin und herspringen, also sehr einfach unterschiedliche Stellen in der Aufnahme aufsuchen.
* Die laufende Zeit wird korrekt angezeigt, entsprechend der tatsächlichen Zeit (UTC) zum Zeitpunkt der Aufnahme. Dies funktioniert natürlich nur bei wav-Dateien, nicht bei *.dat.
* Es gibt einen logarithmischen Signalstärkeanzeiger. Falls das Signal zu schwach ist (Balken wird gelb), kann man mit dem Regler ‚Gain‘ in Grenzen (logarithmisch) nachverstärken.
* Der Play-Button ist nun ein ‚Play/Pause‘ Button.
* Es gibt eine Endlosabspiel-Taste.
* Es gibt einen einfachen Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit wird die Kompatibilität mit kommerziellen SDR-Formaten bedeutend erhöht.

Wir empfehlen allen Nutzer:innen, die lediglich Dateien auf ihren Radios wiedergeben möchten (keine eigenen Aufnahmen), nur noch diese Programmversion zu benutzen, da die alten Versionen in Zukunft nicht mehr gewartet werden. 

Da es sich um eine sehr starke Änderung gegenüber der Vorgängerversion handelt, kann es durchaus sein, dass noch der eine oder andere kleine Bug vorhanden ist. Für entsprechende [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.

## COHIWizard 1.2.9 (Juni 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard1.2.9_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.2.9c.zip)

<p style='text-align: justify;'> Der COHIWizard ist ein umfangreiches Programm, das neben der vollen Funktionalität des RFCorders2.0 auch viele Zusatzfunktionen bereitstellt. Diese umfassen:

* die Möglichkeit, eigene Aufnahmen wie mit dem RFCorder v1.2 zu erstellen, inklusive des automatischen Startens einer Aufnahme mittels eines Timers.
* ein einfaches Spektralanalyse-Fenster für die Bandspektren, der eine rasche statische Beurteilung von Aufnahmen ermöglicht.
* einen im Vergleich zum RFCorder 2.0 stark erweiterten Resampler für das Umcodieren von Aufnahmen, deren Samplingrate nicht STEMLAB-kompatibel sind. Im Gegensatz zum RFCorder2.0 können ganz beliebige Bereiche des Spektrums ausgeschnitten werden. Auch ganze Serien zusammengehörender wav-Files können nun auf einmal resampelt werden.
* ein Annotationstool, das dabei unterstützen kann, die Metadaten-Files halbautomatisch zu generieren. Mit enthalten ist hier auch ein Generator für die yaml-Files, die zwecks Annotation auf dem COHIRADIA-Server erzeugt werden müssen.

Letzteres Feature funktioniert allerdings derzeit erst für Europa und USA sowie Neuseeland, da die Referenztabellen für andere Zonen noch nicht eingebaut wurde.</p>

COHIWizard 1.2.9 ist das letzte Upgrade auf die Erstversion COHIWizard 1.0. Letztere wird zwar im Folgenden auch noch zum Download bereitgestellt (für User, die diese Variante noch betreiben), wird allerdings wegen des geringeren Funktionsumfanges nicht mehr empfohlen. V1.2.9  und beinhaltet schließlich viele Bugfixes und neue Features wie:
  
* erweitertes Konfigurationsmenü
* scrollbare Oberfläche für Anpassung an niedrige Bildschirmauflösungen
* Player: volle Aufnahmefunktion inklusive Aufnahmetimer wie beim RFCorder 1.2
* Resampler: deutliche Beschleunigung einiger Signalverarbeitungsschritte sowie Check auf Datei-Konsistenzen bei Listenabarbeitung
* Annotator: einige Bugfixes sowie die Möglichkeit, auch im nicht ganzzahligen kHz-Raster zu annotieren

</p>

# Vorgänger-Versionen 
## COHIWizard 1.0 (Jänner 2024, erste stabile Version)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1.0_resampler_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0b.zip)



## RFCorder Version 1.2 (April 2022)
<!-- comment -->
<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder1.2_Screenshot.png" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/cohiradia_V1.2.zip)

<p style='text-align: justify;'>RFCorder v1.2 ist die erste voll funktionsfähige Software für die Aufnahme von Breitbandaufzeichnungen mittels des STEMLAB125-14 und deren analoge Wiedergabe auf angeschlossenen Rundfunkempfängern. Diese Version wird nicht mehr empfohlen und wird in Zukunft nicht weiter gewartet. Das einzige unterstützte Fileformat sind bei dieser Version Rohfiles mit 32-byte Complex-Format mit der Extension '.dat'. Die Filenamen müssen der alten COHIRDIA Namenskonvention entsprechen (siehe [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf)) und daher auch in diesem Format aus dem Archiv heruntergeladen werden.</p>

<p style='text-align: justify;'>Das Abspielen von wav-Dateien, wie sie die meisten SDRs benutzen, ist nur bedingt möglich, nämlich wenn man sie entsprechend umbenennt (dat statt wav und Umschreiben des Namens gemäß Namenskonvenion) und wenn die Samplingrate einer der vom STEMLAB unterstützten Raten entspricht. Andere Formate als 2 channels int16 werden nicht unterstützt.

Ein spezielles Feature ist die Möglichkeit, das Frequenzband während des Abspielens im Spektrum zu verschieben, also z.B. ein Langwellenband im Mittelwellenbereich eines Radios abzuspielen. Dazu muss ein Offset zur Bandmittenfrequenz angegeben werden.
Bei Aufnahmen ermöglicht das Programm den automatischen Start einer Aufnahme mittels eines Timers.</p>

# LINUX

Die Python-Version wurde unter Debian 10 erfolgreich gestartet, aber noch nicht ausführlich getestet- Mit dem Player konnten Hf-Signale erfolgreich abgespielt werden und mit dem Synthesizer konnten erfolgreich korrekte SDR-wav-Dateien erstellt werden. Auch eine Annotation mit dem Annotator wurde an einer Aufzeichnung exemplarisch durchgeführt. Umfangreichere Tests werden in der Zukunft durchgeführt werden.

Für die Installation klonen Sie bitte das Repository von [Github](https://github.com/hermy-sf/COHIWizard). Genauere Hinweise finden sich in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

Wenn Sie ein lokales git verwenden, können Sie auch auf den Branch cohiwizard_v1.3 zugreifen, der der aktuelle Entwicklungsbranch ist und als experimentell eingestuft werden muss.

