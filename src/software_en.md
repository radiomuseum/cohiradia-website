---
title: Cohiradia Software
---


## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

RFCorder v2.0 is used to play back broadband recordings on analog radio receivers using the STEMLAB125-14. The description is included in the downloadable zip file. In contrast to the previous version v1.2, this version does not currently allow you to make your own recordings, but there are a number of useful new features:

* In addition to recordings in the raw data format (*.dat) originally used for COHIRADIA, you can now also play back those in wav format. This is useful because all well-known SDRs use this format and therefore all external archives of broadband files contain wav files. Consequently, all new recordings in the archive are now generated exclusively with wav headers. This means that the files can also be played back on the PC with common SDR software such as SDRUno or SDR# and metadata can be transferred to the RFCorder and displayed much more compactly.
* You can now jump back and forth on the timeline with a scroll bar, making it very easy to find different passages in the recording.
* The current time is displayed correctly, according to the actual time (UTC) at the time of recording. Of course, this only works with wav files, not with *.dat.
* There is a logarithmic signal strength indicator. If the signal is too weak (bar turns yellow), you can use the 'Gain' control to increase the gain within limits (logarithmically).
* The play button is now a 'Play/Pause' button.
* There is an endless play button.
* There is a simple resampler that allows recordings not originating from COHIRADIA to be resampled to one of the sampling rates required for STEMLAB. This significantly increases compatibility with commercial SDR formats.

We recommend that all users who only want to play back files on their radios (not their own recordings) only use this program version, as the old versions will no longer be maintained in the future. A version with recording function is in preparation.

As this is a major change compared to the previous version, it is quite possible that one or two small bugs may still be present. I would be grateful for reporting on such issues [Berichte](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html), as this helps to eliminate problems quickly.

## COHIWizard 1.0 (Jänner 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1.0_resampler_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0b.zip)

Der [COHIWizard](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0.zip) ist ein umfangreiches Programm, das neben der vollen Funktionalität des RFCorders2.0 auch viele Zusatzfunktionen bereitstellt. Diese umfassen:
* ein einfaches Spektralanalyse-Fenster für die Bandspektren, der eine rasche statische Beurteilung von Aufnahmen ermöglicht.
* einen im Vergleich zum RFCorder 2.0 stark erweiterten Resampler für das Umcodieren von Aufnahmen, deren Samplingrate nicht STEMLAB-kompatibel sind. Im Gegensatz zum RFCorder2.0 können nun beliebige Bereiche des Spektrums ausgeschnitten werden. Auch ganze Serien zusammengehörender wav-Files können nun auf einmal resampelt werden.
* ein Annotationstool, das dabei unterstützen kann, die Metadaten-Files halbautomatisch zu generieren. Mit enthalten ist hier auch ein Generator für die yaml-Files, die zwecks Annotation auf dem COHIRADIA-Server erzeugt werden müssen.

Letzteres Feature funktioniert allerdings derzeit erst für Europa und USA sowie Neuseeland, da die Referenztabellen für andere Kontinente noch nicht eingebaut wurde. 

## RFCorder Version 1.2 (April 2022)
<!-- comment -->
<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder1.2_Screenshot.png" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/cohiradia_V1.2.zip)

RFCorder v1.2 ist die erste voll funktionsfähige Software für die Aufnahme von Breitbandaufzeichnungen mittels des STEMLAB125-14 und deren analoge Wiedergabe auf angeschlossenen Rundfunkempfängern. Das einzige unterstützte Fileformat sind bei dieser Version Rohfiles mit 32-byte Complex-Format mit der Extension '.dat'. Die Filenamen müssen der alten COHIRDIA Namenskonvention entsprechen (siehe Jahresbericht 2023) und daher auch in diesem Format aus dem Archiv heruntergeladen werden.

Das Abspielen von wav-Dateien, wie sie die meisten SDRs benutzen, ist nur bedingt möglich, nämlich wenn man sie entsprechend umbenennt (dat statt wav und Umschreiben des Namens gemäß Namenskonvenion) und wenn die Samplingrate einer der vom STEMLAB unterstützten Raten entspricht. Andere Formate als 2 channels int16 werden nicht unterstützt.

Ein spezielles Feature ist die Möglichkeit, das Frequenzband während des Abspielens im Spektrum zu verschieben, also z.B. ein Langwellenband im Mittelwellenbereich eines Radios abzuspielen. Dazu muss ein Offset zur Bandmittenfrequenz angegeben werden.
Bei Aufnahmen ermöglicht das Programm den automatischen Start einer Aufnahme mittels eines Timers. 

---
title: Cohiradia Software
---
## RFCoder Version 2.0 (November 2023)
There is now a new version of the RFCorder called [RFCorder_v2](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip), which can be downloaded from the software directory. The description is included in the zip file. Like version v1, the program can currently only play recordings, but there are a number of useful new features:

* You can now also play IQ-files in wav-format. This is useful as all external archives of broadband files offer this format. Furthermore, all new recordings in the archive are now generated exclusively with wav headers. This allows the files to be played back on the PC with common SDR software such as SDRUno or SDR# and metadata can be transferred to the RFCorder and displayed much more compactly.
* You can now jump back and forth on the timeline with a scroll bar, making it very easy to find different points in the recording.
* The current time is displayed correctly, according to the actual time (UTC) at the time of recording. Of course, this only works with wav files, not with *.dat files.
* There is a logarithmic signal strength indicator. If the signal is too weak (bar turns yellow), you can use the 'Gain' control to increase the gain within limits (logarithmically).
* The play button is now a 'Play/Pause' button.
* There is an endless play button.
* There is a simple resampler that allows you to resample non-COHIRADIA recordings to one of the sampling rates required for STEMLAB. This significantly increases compatibility with commercial SDR formats.

I recommend all users who only want to play back files on their radios (no own recordings) to install this program version, as the old versions will no longer be maintained in the future. A version with recording function is in preparation.

As this is a major change compared to the previous version, it may well be that there exist still small bugs. I would be grateful for any [reports on bugs](https://www.radiomuseum.org/forum/software_for_cohiradia_details_and_problem_solving.html), as they help to eliminate problems quickly.

Have fun with the new tool

Hermann Scharfetter
