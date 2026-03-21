---
title: SNR Definition
linkTitle: SNR Definition
date: 2026-02-19
weight: 1
description: >
---

The definition of the basic SNR of a digitizer corresponds to that in the [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf). Theoretically, with N-bit resolution without oversampling and filtering, it is:

```SNR_q = 6.02*N + 1.76 dB.``` 

If we include the typical oversampling values when playing an MW band (BW = 1250 kHz) and the maximum signal power allowed at full modulation, we obtain under ideal conditions:

   ```SNR_eff = 6.02*N + 1.76 + 10*np.log10(OS) - 10*np.log10(M)```

where OS is the oversampling factor and M is the number of carrier frequencies in the spectrum.

As discussed in the [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf), this definition of SNR is not universal. It is actually defined as the ratio of useful signal power to noise power in the useful frequency band. However, the useful signal is actually the audio signal contained in the sidebands. Therefore, instead of the carrier amplitude, one would have to divide the signal power integrated over the AM sideband (4.5 kHz wide for MW) by the noise power present in the same band. The sideband power depends on several details of the modulation (modulation depth, spectral shaping of the sidebands, audio spectrum, etc.) and is therefore not so easy to determine. When applying this definition, the calculated SNR is typically 25-30 dB lower than when referenced to the carrier peak. Due to these complications, the simpler definition described above is used for characterizing the signal converters.

Example evaluations can be found in the [Test Report](/en/docs/documentation/testberichte/snr_messungen/)