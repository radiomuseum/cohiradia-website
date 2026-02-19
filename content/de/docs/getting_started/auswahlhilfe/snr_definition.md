---
title: SNR-Definition
linkTitle: SNR-Definition
date: 2026-02-19
weight: 1
description: >
---

Die Definition der Grund-SNR eines Digitizers entspricht der im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf). Sie beträgt theoretisch bei N bit Auflösung ohne Obersampling und Filterung: 

```SNR_q = 6.02*N + 1.76 dB.``` 

Rechnet man die typischen Oversampling-Werte bei Abspielen eines MW-Bandes (BW = 1250 kHz) und die maximal bei Vollaussteuerung zulässige Signalleistung mit ein, so erhält man unter idealen Bedingungen: 

   ```SNR_eff = 6.02*N + 1.76 + 10*np.log10(OS) - 10*np.log10(M)```

wobei OS der Oversampling-Faktor und M die Anzahl der Trägerfrequenzen im Spektrum sind.

Wie im [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf) diskutiert, ist diese Definition der SNR nicht universell. An sich wird sie ja als Verhältnis aus Nutzsignalleistung und Rauschleistung im Nutzfrequenzband definiert. Das Nutzsignal ist aber eigentlich das in den Seitenbändern enthaltene Audiosignal. Somit müsste man anstelle der Trägeramplitude die über das AM-Seitenband (bei MW 4.5 kHz breit) integrierte Signalleistung durch die im gleichen Band vorhandene Rauschleistung dividieren. Die Seitenbandleistung hängt aber von mehreren Details der Modulation
(Modulationsgrad, spektrale Formung der Seitenbänder, Audiospektrum…) ab und ist daher nicht so eindeutig zu bestimmen. Wenn man diese Definition anwendet, ist die berechnete SNR typischerweise um 25 - 30 dB geringer als wenn man auf den Trägerpeak bezieht. Aufgrund der genannten Komplikationen wird für die Charakterisierung der Signalwandler die oben beschriebene einfachere Definition verwendet.

Beispielhafte Auswertungen finden sich im [Testbericht](/de/docs/documentation/testberichte/snr_messungen/)