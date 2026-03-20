---
title: SNR Measurements
linkTitle: SNR Measurements
date: 2026-02-07
weight: 1
description: >
  SNR measurements on signal converters by W. Barteczek, C. P. Gallenmiller, and H. Scharfetter
---

## Theoretically Expected Values

For an N-bit converter, the theoretical SNR is calculated as:

```SNR_q = 6.02*N + 1.76 (dB)```

This calculation relates the useful signal power to the noise power in the entire sampled band.

For the OSMO-fl2k with N = 8, theoretically just under 50dB SNR at full modulation is expected. Since the sampling rate is typically chosen at 10MS/s, this refers according to the Nyquist theorem to a usable bandwidth of max. 5MHz. The MW recordings have a bandwidth of 1.25MHz, therefore 4x oversampling is present, which enables an SNR gain of 6dB. Therefore, with optimal modulation, effectively just under 56 dB can be expected with the fl2k system in the MW band.

For the STEMLAB, 86dB base SNR results. With significantly higher oversampling of 100 (the sampling rate is 125MS/s), this gives an SNR gain of 20dB. Therefore, the SNR should effectively be 106dB.

## Measurements with SDR (H. Scharfetter):

The signal converter was coupled to input A of an RSPdx from SDRplay via an adjustable attenuator. Then a test signal generated using the synthesizer function was played via the COHIWizard. The playback amplitude on the COHIWizard and the gain of the SDRdx were set so that no noticeable intermodulation products became visible in the spectrum.

Two spectra were displayed:
1. Spectrum over the total bandwidth BW = 1250 kHz, FFT with 65536 points, RBW 19 kHz
2. A 20 kHz wide section with BW = 24kHz, FFT with 512 points, RBW = 28.85 Hz

Since the noise floor of the spectrometer at about -125 dB is not significantly below that of the measured spectrum, an accurate SNR determination with the signal dynamics used is only possible from the 20 kHz wide section with reasonable accuracy. The wide spectrum only serves to investigate any spurs that may occur.

To account for the RBW of the display window, the effective SNR results as:

    SNR_eff = Peak (dB) - noise floor (dB) - 10log(span/RBW)


### Measurement 1: Modulated Single Carrier

The test signal was music (ABBA, "Sugar Candy Kisses") modulated onto a carrier of 999kHz with modulation degree 0.8 and audio bandwidth 4.5 kHz. The total bandwidth of the recording was 1250 kHz (500-1750 kHz). This band has a raw SNR of more than 130 dB (tested with SDRUno), defined as the dB difference between carrier amplitude and noise floor.

### Measurement 2: Synthetic Spectrum with 29 Single Carriers

For the test, 29 carriers with music from the 20s and 30s were modulated using the COHIWizard synthesizer (source: collection of C.P. Gallenmiller). The total bandwidth of the recording was again 1250 kHz (500-1750 kHz).

When K uncorrelated carriers exist in the same band, the energy of a single peak must be reduced by a factor of K so that the total signal does not overdrive the DAC. With 29 carriers, this means a required reduction of at least 14.6dB. In fact, a reduction of at least 25 was necessary, since the transmitters in this spectrum were not ideally decorrelated.


## Measurement Result

**Single tone:**

* STEMLAB: SNR_eff = 75.8 dB, peak level of carriers -30 dB
* fl2k: SNR_eff = 57.8 dB, peak level of carriers -35 dB


<img 
  src="/images/Spektrum_PC_single_tone_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 1: Spectrometer output for fl2k

<img 
  src="/images/Spektrum_PC_single_tone_SL_RP_xrspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 2: Spectrometer output for STEMLAB

Certain intermodulation peaks are visible in the wide spectrum with the fl2k and could never be completely eliminated.

For the STEMLAB, it should be noted that the measurement, due to the noise floor of the spectrometer, hardly allows better readings to be made; the actual values are probably significantly better.


**29 Carriers:**

* STEMLAB: SNR_eff = 47.8 dB, peak level of carriers -58 dB
* fl2k: SNR_eff = 35.8 dB, peak level of carriers -60 dB

<img 
  src="/images/Spektrum_PC_A2_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 3: Spectrometer output for fl2k

<img 
  src="/images/Spektrum_PC_A2_SL_RP_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 4: Spectrometer output for STEMLAB

For the STEMLAB, it should be noted that the measurement, due to the noise floor of the spectrometer, hardly allows better readings to be made; the actual values are probably significantly better.




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
