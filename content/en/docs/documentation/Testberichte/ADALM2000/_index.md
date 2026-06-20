---
title: Test-Reports concerning the ADALM2000
linkTitle: Test-Reports concerning the ADALM2000
date: 2026-06-16
weight: 1
description: >

---

## Field Report on the Use of the ADALM2000

T. Nickel reported on the operation of an ADALM2000 on a Windows PC running COHIWizard version 2.2.4. He was able to successfully play back some recordings, but noticed additional noise and AVC malfunctions with certain synthetic recordings. 

Following an analysis of the issues, several changes were made that now result in improved playback quality starting with version 2.2.5. Anyone still using older versions of COHIWizard with an ADALM2000 should therefore download and install the latest version.

### Identified Issues

**Computing Power**

As with FL2K, the upconversion of the IQ baseband data to the target frequency range must be performed on the PC, which requires significant computing power. As a result, older computers with low processing power may cause packet delays and periodic interruptions in the playback stream.

In version 2.2.5, data processing was optimized, resulting in slightly better performance. However, problems were still observed, for example on older laptops such as a Toshiba R700 with an Intel i7 processor, 2.6 GHz, and 8 GB of RAM.

**Aliasing Signals at the DAC Output**

Unfortunately, the ADALM2000 does not have passive anti-aliasing filters at the output of its DAC. As a result, when upsampling the original band to the AD9963’s sampling rate during LW and MW playback, aliasing signals appear in the transmitted spectrum.

Although these components lie above the nominal upper end of the reproduced frequency bands, they can cause interference in connected receivers. This often results in a significantly worse signal-to-noise ratio (SNR) than one would expect from a 12-bit DAC. Unfortunately, there are currently no known methods for activating the AD9963’s internal interpolation filter.

This problem occurred particularly in COHIWizard versions up to 2.2.4, since the sampling rate was set very close to twice the Nyquist frequency in those versions. To suppress the images in the spectrum, T. Nickel inserted a 7th-order low-pass filter with steep rolloff between the output of the ADALM2000 and the receiver; see Fig. 1.

<img 
  src="../../../../../de/docs/documentation/testberichte/adalm2000/1,7MHz-Filter_V2.JPG"
  style="max-width: 50%; height: auto;"
/>

**Fig. 1:** Anti-aliasing low-pass filter by T. Nickel

After this problem became known, an option to reduce the oversampling rate of the ADALM2000 was therefore implemented in version 2.2.5 of the COHIWizard. As a result, the effective sampling rate during upconversion is higher than in previous versions. The alias signals are thus shifted to higher frequencies, allowing for the use of less sophisticated output filters.

**Conclusion: In any case, it is recommended to install an external low-pass or band-pass filter between the ADALM2000 output and the connected receivers.** For applications in the medium-wave (MW) band, the filter’s upper cutoff frequency should be around 1.7 to 1.8 MHz, i.e., at the upper end of the medium-wave broadcast band. For longwave (LW), a filter with a cutoff frequency of approximately 300 kHz should be used.

H. Scharfetter achieved good results for MW using an 8th-order passive Butterworth bandpass filter. The filter parameters were calculated using the [Chebyshev Bandpass Filter Designer](http://www.changpuak.ch/electronics/chebyshev_bandpass.php) (Version 11.01.2014) for a Chebyshev low-pass filter with center frequency = 1.1 MHz, bandwidth = 1.2 MHz, order = 4, impedance = 50 ohms, passband ripple = 1%, and “first element” = “shunt.” The resulting filter parameters are:

Element 1, Orientation: shunt 
C = 5568 pF, L = 3759 nH
Element 2, Orientation: series 
C = 2965 pF, L = 7058 nH
Element 3, Orientation: shunt 
C = 7510 pF, L = 2787 nH
Element 4, Orientation: series 
C = 4000 pF, L = 5233 nH

For implementation, the closest values from the E12 series were used. Note: The “Order = 4” setting in the calculator does not refer to the actual filter order, but rather to the number of LC pairs.

Both filters shown must be terminated with 50 ohms to ensure correct frequency response. This must be taken into account when connecting to a radio via an isolation transformer, since there is usually no well-defined termination there to begin with.

**AVC Overdrive**
In some synthesized recordings with a high crest factor, it has been observed that heavy noise and heavy audio distortions occur when the COHIWizard’s AVC (automatic volume control) is enabled. The cause is not fully understood, but it appears to originate within the ADALM2000 itself. Disabling AVC and manually lowering the volume helps resolve this issue. Starting with version 2.2.5, the AVC threshold is automatically lowered when the signal has a high crest factor, so this error should normally no longer occur.


### Specific Technical Solution for the Aliasing Problem: Adjusting the Oversampling Factor

If interference—such as heavy noise—continues to occur during playback of certain recordings, it may be necessary to manually adjust a parameter in the *config_wizard.yaml* file.

The ADALM2000 operates at a fixed sampling rate of 75 MS/s. For a bandwidth of, say, 1.8 MHz, a sampling rate of at least 3.6 MS/s would theoretically be required to satisfy the Nyquist criterion. To minimize computational load and data transfer rates, this sampling rate should be set as low as possible. The software therefore automatically determines the smallest integer divisor by which the internal sampling rate of 75 MS/s can be divided without violating the Nyquist criterion. This divisor is referred to as the *oversampling ratio* (OSR).

In this example, this results in a sampling rate of 3.75 MS/s, corresponding to an OSR value of 20. The signal is thus effectively oversampled by a factor of 20. However, the first alias component of a band limited to 1.8 MHz then appears as early as 1.95 MHz—only 150 kHz above the band end.

Fig. 3 shows an example with a band limit at 1.4 MHz, where the spectrum of a synthetic recording is plotted up to 10 MHz.

<img 
  src="../../../../../de/docs/documentation/testberichte/adalm2000/log_ADALM2000_OSR1_0.PNG"
  style="max-width: 70%; height: auto;"
/>

**Fig. 3:** Spectrum of a recording (band end 1.4 MHz) with all aliases up to 10 MHz.

The lower limit of the first alias component is therefore:

3.75 - 1.4 = 2.35 (MHz)

A very steep-slope filter would also be required to sufficiently suppress these alias signals. For this reason, a so-called *relaxation factor* (*relaxfactor_OSR*) was introduced, which reduces the OSR to a correspondingly smaller integer value.

This factor can be set in the *config_wizard.yaml* file:

```yaml
relaxfactor_OSR: 1.2
```

By default, this factor is set to 1.2, resulting in an OSR value of 16.7. The value is then truncated to the next lower integer value, 16. This then yields a base sampling rate of 4.6875 MS/s.

For the example above:

4.6875 − 1.4 = 3.2875 (MHz)

The first alias therefore starts at just under 3.3 MHz, as shown in Fig. 4. This provides a little more margin for attenuating the unwanted signal components after the low-pass filter.

<img 
  src="../../../../../de/docs/documentation/testberichte/adalm2000/log_ADALM2000_OSR1_2.PNG"
  style="max-width: 70%; height: auto;"
/>

**Fig. 4:** Spectrum of a recording (bandwidth 1.4 MHz) showing all aliases up to 10 MHz. Here, OSR was set to 16 (relaxfactor_OSR = 1.2)

The higher the value of *relaxfactor_OSR* selected, the lower the oversampling and the further the aliases are shifted toward higher frequencies, which naturally makes it easier to filter them out. At the same time, however, the computational effort for upsampling and the required data transfer rate increase. Therefore, values significantly greater than 1.5 are not recommended for average PC performance. On a PC with an AMD Ryzen Pro 4650G running at 3.7 GHz and 16 GB of RAM, uninterrupted transmission was possible under Windows 11 up to a value of 1.6.

Examples for 1.5 and 2.0 are shown in Fig. 5.

<img 
  src="../../../../../de/docs/documentation/testberichte/adalm2000/log_ADALM2000_OSR1_5.PNG"
  style="max-width: 70%; height: auto;"
/>
<img 
  src="../../../../../de/docs/documentation/testberichte/adalm2000/log_ADALM2000_OSR2_0.PNG"
  style="max-width: 70%; height: auto;"
/>

**Fig. 5:** Spectra of a recording (bandwidth 1.4 MHz) showing all aliases up to 10 MHz at OSR = 13 (top) and 10 (bottom) (corresponding to relaxfactor_OSR = 1.5 and 2.0, respectively). Note the increasing shift of the aliases toward higher frequencies. 

**WARNING:** Normally, the *config_wizard.yaml* file should not be modified. This is where the COHIWizard stores important settings, as well as, for example, the most recently used file paths and the STEMLAB’s IP address. Uncontrolled changes may cause the COHIWizard to malfunction. Therefore, always make a backup copy of this file before making any changes so that you can restore it if something goes wrong. In an emergency, you can also delete it; a new version will then be created upon restart. However, your previous settings will be lost.

**Note:** On low-performance computers, signal dropouts or interruptions may still occur even at a value of 1.2. In this case, the smallest permissible value is:

```yaml
relaxfactor_OSR: 1.0
```

However, a very steep-slope output filter is then required to sufficiently suppress the alias components.

The COHIRADIA team would like to express its sincere thanks to T. Nickel for his active support in analyzing this issue.

---