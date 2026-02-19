---
title: SNR_Messungen
linkTitle: SNR_Messungen
date: 2026-02-07
weight: 1
description: >
  SNR Messungen an Signalwandlern durch CPG, WB, HS
---

## Theoretisch erwartete Werte

Für einen N-Bit-Wanler errechnet sich die theoretische SNR zu:

```SNR_q = 6.02*N + 1.76 (dB)```

Diese Rechnung bezieht die Nutz-Signalleistung auf die Rauschleistung im gesamten abgetasteten Band.

Für das OSMO-fl2k ergeben sich mit N = 8 theoretisch knapp 50dB SNR bei Vollaussteuerung. Da die Abtastrate typischerweise mit 10MS/s gewählt wird, bezieht sich das gemäß Nyquist-Theorem auf eine nutzbare Bandbreite von max. 5MHz. Die MW-Aufzeichnungen besizten eine Bandbreite von 1.25MHz, daher liegt 4-faches Oversampling vor, was einen SNR-Gewinn von 6dB ermöglicht. Daher sind bei optimaler Aussteuerung mit dem fl2k-System im MW-Band effektiv knapp 56 dB zu erwarten. 
 
Für das STEMLAB ergeben sich 86dB Grund-SNR. Bei deutlich höherem Oversampling von 100 (die Abtastrate ist 125MS/s) ergit das einen SNR-Gewinn von 20dB. Daher müsste die SNR effektiv 106dB betragen
 
## Messungen:

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
