---
title: Cohiradia Software
---
## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="800" height="400" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

Es gibt nun eine [neue Version des RFCorders](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip), die ab sofort heruntergeladen werden kann. Die Beschreibung ist im zip-File mit eingepackt. Das Programm kann derzeit im Gegensatz zu Version v1.2 zwar Aufnahmen lediglich abspielen, dafür gibt es eine Reihe nützlicher neuer Features:

* Man kann nun auch wav-Dateien abspielen. Das ist sinnvoll, da alle externen Archive von Breitbanddateien dieses Format anbieten. Weiters werden alle neuen Aufnahmen im Archiv nun ausschließlich mit wav-Header generiert. Dies erlaubt es, die Files auch mit gängiger SDR-Software wie SDRUno oder SDR# auf dem PC wiederzugeben und Metadaten können so viel kompakter an den RFCorder übergeben und dargestellt werden.
* Man kann nun mit einem Rollbalken auf der Zeitleiste hin und herspringen, also sehr einfach unterschiedliche Stellen in der Aufnahme aufsuchen.
* Die laufende Zeit wird korrekt angezeigt, entsprechend der tatsächlichen Zeit (UTC) zum Zeitpunkt der Aufnahme. Dies funktioniert natürlich nur bei wav-Dateien, nicht bei *.dat.
* Es gibt einen logarithmischen Signalstärkeanzeiger. Falls das Signal zu schwach ist (Balken wird gelb), kann man mit dem Regler ‚Gain‘ in Grenzen (logarithmisch) nachverstärken.
* Der Play-Button ist nun ein ‚Play/Pause‘ Button.
* Es gibt eine Endlosabspiel-Taste.
* Es gibt einen einfachen Resampler, der es erlaubt, nicht aus COHIRADIA stammende Aufnahmen auf eine der für das STEMLAB nötigen Samplingraten zu resampeln. Damit wird die Kompatibilität mit kommerziellen SDR-Formaten bedeutend erhöht.

Ich empfehle allen Nutzer:innen, die lediglich Dateien auf ihren Radios wiedergeben möchten (keine eigenen Aufnahmen), nur noch diese Programmversion zu benutzen, da die alten Versionen in Zukunft nicht mehr gewartet werden. Eine Variante mit Recording-Funktion ist in Vorbereitung.

Da es sich um eine sehr starke Änderung gegenüber der Vorgängerversion handelt, kann es durchaus sein, dass noch der eine oder andere kleine Bug vorhanden ist. Für entsprechende [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) bin ich dankbar, denn sie helfen dabei, Probleme rasch zu beseitigen.


## RFCorder Version 1.2 (April 2022)
<!-- comment -->
<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder1.2_Screenshot.png" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/cohiradia_V1.2.zip)

RFCorder v1.2 ist die erste voll funktionsfähige Software für die Aufnahme von Breitbandaufzeichnungen mittels des STEMLAB125-14 und deren analoge Wiedergabe auf angeschlossenen Rundfunkempfängern. Das einzige unterstützte Fileformat sind bei dieser Version Rohfiles mit 32-byte Complex-Format mit der Extension '.dat'. Die Filenamen müssen der alten COHIRDIA Namenskonvention entsprechen (siehe Jahresbericht 2023) und daher auch in diesem Format aus dem Archiv heruntergeladen werden.

Das Abspielen von wav-Dateien, wie sie die meisten SDRs benutzen, ist nur bedingt möglich, nämlich wenn man sie entsprechend umbenennt (dat statt wav und Umschreiben des Namens gemäß Namenskonvenion) und wenn die Samplingrate einer der vom STEMLAB unterstützten Raten entspricht. Andere Formate als 2 channels int16 werden nicht unterstützt.

Ein spezielles Feature ist die Möglichkeit, das Frequenzband während des Abspielens im Spektrum zu verschieben, also z.B. ein Langwellenband im Mittelwellenbereich eines Radios abzuspielen. Dazu muss ein Offset zur Bandmittenfrequenz angegeben werden.
Bei Aufnahmen ermöglicht das Programm den automatischen Start einer Aufnahme mittels eines Timers. 


