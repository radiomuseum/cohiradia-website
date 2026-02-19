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

[Testbericht](/de/docs/documentation/testberichte/snr_messungen/)