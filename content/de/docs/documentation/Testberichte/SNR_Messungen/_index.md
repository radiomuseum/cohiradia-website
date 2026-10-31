---
title: SNR_Messungen
linkTitle: SNR_Messungen
date: 2026-02-07
weight: 1
description: >
  SNR Messungen an Signalwandlern durch W. BArteczek, C. P. Gallenmiller und H. Scharfetter
---

## Theoretisch erwartete Werte

Für einen N-Bit-Wanler errechnet sich die theoretische SNR zu:

```SNR_q = 6.02*N + 1.76 (dB)```

Diese Rechnung bezieht die Nutz-Signalleistung auf die Rauschleistung im gesamten abgetasteten Band.

Für das OSMO-fl2k ergeben sich mit N = 8 theoretisch knapp 50dB SNR bei Vollaussteuerung. Da die Abtastrate typischerweise mit 10MS/s gewählt wird, bezieht sich das gemäß Nyquist-Theorem auf eine nutzbare Bandbreite von max. 5MHz. Die MW-Aufzeichnungen besizten eine Bandbreite von 1.25MHz, daher liegt 4-faches Oversampling vor, was einen SNR-Gewinn von 6dB ermöglicht. Daher sind bei optimaler Aussteuerung mit dem fl2k-System im MW-Band effektiv knapp 56 dB zu erwarten. 
 
Für das STEMLAB ergeben sich 86dB Grund-SNR. Bei deutlich höherem Oversampling von 100 (die Abtastrate ist 125MS/s) ergit das einen SNR-Gewinn von 20dB. Daher müsste die SNR effektiv 106dB betragen
 
## Messungen mit SDR (H. Scharfetter):

Der Signalwandler wurde über einen regelbaren Abschwächer an den Eingang A eines RSPdx von SDRplay angekoppelt. Dann worde über den COHIWizard ein Testsignal eingespielt, das per Synthesizer-Funktion erzeugt worden war. Die Abspielamplitude am COHIWizard und das gain des SDRdx wurden so eingestellt, dass gerade keine merklichen Intermodulationsprodukte im Spektrum sichtbar wurden.

Dargestellt wurden zwei Spektren:
1. Spektrum über die Gesamtbandbreite BW = 1250 kHz, FFT mit 65536 Punkten, RBW 19 kHz
2. ein 20 kHz breiter Ausschnitt mit BW = 24kHz, FFT mit 512 Punkten, RBW = 28.85 Hz

Da der Noise floor des Spektrometers mit ca -125 dB nicht wesentlich unter dem des gemessenen Spektrums liegt, ist bei der verwendeten Signaldynamik eine genaue SNR-Bestimmung nur aus dem 20 kHz breiten Ausschnitt mit brauchbarer Genauigkeit möglich. Das breite Spektrum dient nur der Untersuchung evt. auftretender Spurs.

Um die RBW des Anzeigefensters zu berücksichtigen, ergibt sich die effektive SNR als:

    SNR_eff = Peak (dB) - noise floor (dB) - 10log(span/RBW)


### Messung 1: Modulierter Einzelträger

Beim Testsignal handelte es sich um Musik (ABBA, "Sugar candy kisses"), die auf einen Träger von 999kHz mit Modulationsgrad 0.8 und Audiobandbreite 4.5 kHz aufmoduliert worden war. Die Gesamtbandbreite der Aufzeichnung betrug 1250 kHz (500 -1750 kHz). Dieses Band besitzt eine rohe SNR von mehr als 130 dB (getestet mit SDRUno), definiert als dB-Differenz zwischen Träger-Amplitude und noise-floor.

### Messung 2: Synthetisches Spektrum mit 29 Einzelträgern

Für den Test wurden 29 Träger mit Musik der 20er- und 30er-Jahre mittels des COHIWizard-Synthesizers moduliert (Quelle: Sammlung von C.P. Gallenmiler). Die Gesamtbandbreite der Aufzeichnung betrug wieder 1250 kHz (500 -1750 kHz).

Wenn K unkorrelierte Träger im selben Band existieren, ist die Energie eines einzelnen Peaks um den Faktor K reduzieren, damit das Gesamtsignal den DAC nicht übersteuert. Bei 29 Trägern bedutet das eine erforderliche Absenkung um mindestens 14.6dB. Tatsächlich musste um mindestens 25 abgesenkt werden, da bei diesem Spektrum die Sender nicht ideal dekorreliert waren.  


## Messergebnis

**Single tone:**

* STEMLAB:  SNR_eff = 75.8 dB, peak-Pegel der Träger -30 dB
* fl2k: SNR_eff = 57.8 dB, peak-Pegel  der Träger -35 dB


<img 
  src="/images/Spektrum_PC_single_tone_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Abb. 1: Spektrometer-Ausgabe für fl2k

<img 
  src="/images/Spektrum_PC_single_tone_SL_RP_xrspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Abb. 2: Spektrometer-Ausgabe für STEMLAB

<!-- <a href="/pdf/Berechnungen_Loop_Antenne_TX_fuer_Webpage_v2_reduced.pdf" target="_blank" rel="noopener noreferrer">
  diesem pdf
</a>. -->

Beim fl2k sind gewisse Intermodulationspekas im breiten Spektrum sichtbar und konnten nie ganz zum Verschwinden gebracht werden.

Beim STEMLAB ist zu beachten, dass die Messung aufgrund des Noise-floor des Spektrometers kaum noch bessere Werte abzulesen gestattet, die tatsächlichen Werte sind vermutlich deutlich besser.


**29 Träger:**

* STEMLAB:  SNR_eff = 47.8 dB, peak-Pegel der Träger -58 dB
* fl2k: SNR_eff = 35.8 dB, peak-Pegel  der Träger -60 dB

<img 
  src="/images/Spektrum_PC_A2_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Abb. 3: Spektrometer-Ausgabe für fl2k

<img 
  src="/images/Spektrum_PC_A2_SL_RP_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Abb. 4: Spektrometer-Ausgabe für STEMLAB

Beim STEMLAB ist zu beachten, dass die Messung aufgrund des Noise-floor des Spektrometers kaum noch bessere Werte abzulesen gestattet, die tatsächlichen Werte sind vermutlich deutlich besser.




## Fazit:

Die Single-Ton-Messungen bestätigen die theoretische SNR des fl2k (57.8 dB vs 56 dB) innerhalb der zu erwartenden Messfehler. Beim STEMLAB konnte der theoretische Wert von 106 dB nicht nachgewiesen werden, da der Dynamikbereich des verwendeten Spektrometers (SDR) nicht ausreicht, um den Rauschpegel des Signals über den des Spektrometers zu heben. Der Messwert von 75.8 dB ist somit wahrscheinlich deutlich zu niedrig, illustriert zumindest aber die deutlich bessere Perfomance des STEMLAB.

Bei den 29 Tragern musste die Signalamplitude deutlich reduziert werden, um Übersteuerung zu verhindern. Dort wurden mit dem fl2k immerhin noch 35.8 dB SNR gemessen, beim STEMLAB ergab sich wieder ein durch den Noise-floor des Spektrometers verfälschter Wert von 47.8 dB. Auch hier ist das STEMLAB natürlich überlegen. 

Dennoch kann man feststellen, dass der Unterschied zumindest beim Abhören nicht wirklich störend in Erscheinung tritt, und das fl2k daher eine sehr brauchbare Lösung für die meisten Abspiel-Anwendungen darstellt, sofern man nicht auf hohe Abtastraten angewiesen ist (z.B. KW-Spektren).

## Messungen mit Stand-Alone Spektralanalysatoren (W. Barteczek, C.P. Gallenmiller):

W. Barteczek hat Messungen mit einem Spektralanalysator der Type HP 8591E (9 kHz- 1,8 GHz) an einem Dongle der Marke DeLock 62783 durchgeführt. Die Spektrumaufnahmen erfolgten mit nachgeschaltetem 17dB 2N5109-Verstärker und 2MHz Tiefpass hinter dem DeLock 62783. Als Testsignal kam die auf einem PC per COHIWizard abgespielte Aufnahme 'Echoes of Bygone Radio Broadcasts: from 20's to 50's, Vol.1' aus der COHI-Jukebox zum Einsatz, die 12 Carrier beinhaltet. Die Einstellung des COHIWizard war: Keine AGC/AVC, Pegelsteller bei -22dB. Abb 5. zeigt das Ergebnis bei einer Span von 500 kHz und einer RBW von 1 kHz. 

<img 
  src="/images/WB_fl2k_Spektrum_bei_optimaler_Aussteuerung.jpg"
  style="max-width: 90%; height: auto;"
/>

Abb. 5: Spektrometer-Ausgabe für fl2k

Bild 6 zeigt das Ergebnis für die Untersuchung der Intermodulationsprodukte. Hier war ein Intermodulationsabstand IM3 von -40dB erreichbar. Die Oberwellenunterdrückung lag bei etwa -30dB.


<img 
  src="/images/WB_fl2k_DeLock62783_IM3_-40dB_OW_-30dB.jpg"
  style="max-width: 90%; height: auto;"
/>

Abb. 6: Spektrometer-Ausgabe mit Span 1000kHz und Beobachtung der Intermodulationsprodukte.

C.P. Gallenmiller hat zusätzlich zu den bereits oben vorgestellten Evaluierungen noch Vergleiche zwischen COHIWizard und COHI-Player mini 
auf einem LINUX-PC durchgeführt. Die Tests wurden für 3 verschiedene Signale angestellt: 
1) RM2006B_part1 aus dem COHIRADIA-Archiv 
2) synthetisches AM2 mit 29 Trägern wie unter Paragraph 1. 

Die Einstellungen der Meßgeräte sind jeweils gleich. Zunächst in Abb. 7 der Vergleich von RM2006_part1 und AM1 für STEMLAB und COHI-Player mini:

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image004_STL_mini_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 7a: Spektrum RM2006B_part1 mit STEMLAB und COHI Player mini auf LINUX-PC.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image001_STL_mini_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 7b: Spektrum AM2 mit STEMLAB und COHI Player mini auf LINUX-PC.

Abbildungen 8 a und b zeigen die Situation für den COHIWizard und fl2k für die selben beiden Quelldateien.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image016_fl2k_Wiz_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 8a: Spektrum RM2006B_part1 mit STEMLAB und COHIWizard auf LINUX-PC.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image001_STL_mini_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 8b: Spektrum AM2 mit STEMLAB und COHI COHIWizard auf LINUX-PC.

Besonders interessant ist ein Vergleich zwischen COHIWizard und der aktuell auf radio-bastler.de verfügbaren GNU Radio-Abspielsoftware für fl2k. Beide wurden sowohl auf einem Linux-PC als auch auf dem RaspberryPi 5 angestellt, wobei zwischen PC und Raspberry Pi keine relevanten Unterschiede festgestellt wurden. Daher werden die Ergebnisse nur für einen Raspberry Pi dargestellt. Die Tests wurden für 3 verschiedene Signale angestellt: 
1) RM2006B_part1 aus dem COHIRADIA-Archiv 
2) synthetisches AM2 mit 29 Trägern wie unter Paragraph 1 
3) synthetisches Spektrum mit 14 Trägern mit Radiosendungen aus den 70er-Jahren, Kurzbezeichnung 'Europa 1'

Bild 9a - c zeigt die Ergebnisse für den COHIWizard.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image016_fl2k_Wiz_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 9a: Spektrum RM2006B_part1 mit fl2k und COHIWizard auf Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image014_fl2k_Wiz_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 9b: Spektrum AM2 mit fl2k und COHIWizard auf Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image018_fl2k_Wiz_Europa1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 9c: Spektrum Europa 1 mit fl2k und COHIWizard auf Raspberry Pi 5.

Bild 10a - c zeigt die Ergebnisse für die GNU Radio Variante.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image007_fl2k_GNUraspi_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 10a: Spektrum RM2006B_part1 mit fl2k und GNU Radio auf Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image009_fl2k_GNUraspi_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 10b: Spektrum AM2 mit fl2k und GNU Radio auf Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image012_fl2k_GNUraspi_Europa1.png"
  style="max-width: 90%; height: auto;"
/>

Abb. 10c: Spektrum Europa 1 mit fl2k und GNU Radio auf Raspberry Pi 5.

Wie schon zu erwarten war, ist die Tonqualität beim STEMLab, unabhängig vom Programm mit Abstand am besten. Es tritt weder Übersteuerung noch Kreuzmodulation auf. Beim FL2K gibt es einen Qualitätsunterschiede zwischen GNU Radio und dem COHIWizard. Die GNU Radio Variante liefert einen deutlich kräftigeren Ton, der im Fall eines realen MW-Spektrums eigentlich auch gut brauchbar ist. Bei den synthetischen Spektren (AM2) schneidet das fl2k mit GNU Radio deutlich schlechter ab, da es viele Übersteuerungen und Kreuzmodulationen gibt, aber das Ergebnis erinnert an die Tonqualität bei einer realen MW-Übertragung mit Störgeräuschen und Mehrfachempfang. Beim Spektrum Europa1 mit weniger und teilweise weiter auseinander liegenden Trägern ist die Situation deutlich besser, obwohl auch noch nicht optimal. Die Wiedergabe mit COHIWizard bei FL2K Stream ist leiser, da der Ausgangspegel um ca. 30db unter dem beim GNU Radio liegt. Dafür gibt es praktisch keine Kreuzmodulationen (keine Übersteuerung), also eine deutlich sauberere Wiedergabe.

Die folgenden 3 Audiobeispiele geben Bandscans durch ein synthetisches Spektrum mit 29 Trägern, das C.P. Gallenmiller mit einem Telefunken 8001W aus dem Jahr 1939 aufgenommen hat.

STEMLab mit COHIWizard:

<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 STEMLab_c.mp3" type="audio/mpeg">
  Ihr Browser unterstützt das Audio-Element nicht.
</audio>

fl2k mit COHIWizard:

<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 FL2K + COHIWizard_c.mp3" type="audio/mpeg">
  Ihr Browser unterstützt das Audio-Element nicht.
</audio>

fl2k mit GNU Radio, Version pts5 von [radiobastler.de](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&postID=297313&highlight=fl2k#post297313):


<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 FL2K + GNURadio pts5.mp3" type="audio/mpeg">
  Ihr Browser unterstützt das Audio-Element nicht.
</audio>
