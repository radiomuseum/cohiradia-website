---
title: Coupling Device
linkTitle: Coupling Device
date: 2026-01-01
weight: 20
description: >
   RF isolation transformer, possibly multi-channel transformer, or also a small transmitter, either as a loop or electrically.
---

## General and Safety Information

**ATTENTION**: Old, and especially vintage, radio receivers were neither designed to meet the requirements of modern safety regulations nor designed to be directly connected to modern low voltage digital equipment. The result is that special care needs to be taken when connecting them to modern digital peripherals. You are therefore connecting these receivers at your own risk, so pay special attention to the following information.

**Electric shock hazard:** We are speaking here of tube/valve radios often with wooden cases and little more than a piece of hard cardboard to serve as a rear guard against high voltages and high temperatures. Additionally, the antenna input of many old tube receivers cannot be guaranteed to be safe to touch because of the possibility of degeneration of internal components, especially capacitors. With so-called AC/DC devices, the chassis is known to be connected to one of the conductors of the mains plug and is therefore connected to either the neutral or the phase conductor after plugging in, depending on the plug orientation. It can therefore assume a voltage of 230V against ground in Europe or 120/230V elsewhere. Normally the inputs for ground and antenna are separated from the chassis and thus galvanically coupled to internal parts by capacitors, but these comparatively high capacitances can cause noticeable currents at mains frequency. For example, 10nF at 230V and 50Hz results in about 0.72 mA current. This is clearly noticeable when touched. Consequently, high voltages up to, and including, the mains voltage may be present at the unloaded inputs. Exercise appropriate caution.

With some models, directly connecting the ground socket to the protective conductor contact of a socket can even trip the residual current circuit breaker, which indicates significantly larger capacitances or even defective coupling elements. With other devices, parasitic capacitances between the mains and the tube circuit can also lead to high AC voltages of well over 100V with respect to ground.

As discussed in detail in [other articles](https://www.radiomuseum.org/forum/radios_mit_gefaehrlicher_stromversorgung.html?language_id=1) on RM, such radios should not be carelessly connected to the mains; an isolation transformer would be optimal. Many old capacitors in devices up to the 1950s sometimes even have simple insulation deficiencies; paper-aluminum roll capacitors with tar sealing, for example, all need to be replaced today, and even the subsequent WIMA "malt candies" had reached the end of their life by the 1980s. 

**Therefore, if in doubt, subject your tube receiver to a thorough inspection and, if necessary, professional restoration.**

Due to this situation, **it is expressly advised against connecting the output of the signal converter (STEMLAB, fl2k dongle, …) directly to the antenna input.** This can not only damage or destroy the signal converter, but can also be dangerous for people handling it to touch corresponding conductive parts. An RF isolation transformer with a suitable transformation ratio from the 50Ω output of the STEMLAB to the radio provides an acceptable remedy. Usually, an impedance transformation of 1:9 to 1:16 (turns ratio 1:3 or 1:4) works for typical tube devices.

For radio devices that have either ferrite antennas or loop antennas, purely inductive coupling via a transmit loop and a suitable driver stage at low transmit power (compliance with interference radiation regulations!) is possible. Due to the contactless signal transmission, this variant is at least safe for the transmit side. **Please note, however, that when operating such a small transmitter, the regulations of the respective national regulatory authority for radio traffic must be observed in any case.** In Germany, for example, one can refer to the "General allocation of frequencies for inductive devices" (Vfg. 109/2021, amended 91/2023). Permissible at 10m distance on, e.g., medium wave is -15dBµA/m at 10 kHz bandwidth and broadband -5dBµA/m (knowledge as of February 2026).

## Coupling through RF Transformers

Here it must be noted that the transformer has sufficient insulation strength between the (driver-side) primary and (radio-side) secondary. Toroidal core transformers are suitable, where the secondary side is made of plastic-insulated wire whose insulation reliably withstands the mains voltage. This insulation strategy is recommended because many common ferrite cores have a certain electrical conductivity, and therefore, with damaged insulation, there is no sufficient galvanic isolation. The wire can be thin for good magnetic coupling, since no significant currents are transmitted. The primary side, in contrast to the secondary side, can consist of enameled copper wire (typically 0.3-0.5mm diameter).

Care must be taken that the two windings **are completely galvanically separated and do not share a common ground**. These details should be particularly noted if commercially available baluns or ununs from amateur radio technology are to be used.


Ferrites suitable in general are those corresponding to the Amidon-listed materials 77 (LW, MW) and 43 (also works well for SW bands). A convenient size is, e.g., FT114 or FT140.

Successful application was found, e.g., with transformers with FT114/43 toroidal core and a turns ratio of 15:60 on a Minerva375A and on a Hornyphon W248U. But FT114/43 with 15:30 also works reasonably well. LW, MW, and also SW at 49m were successfully coupled in with these. F. Wolf reports on a FT240/77 toroidal core, turns ratio 10:30, which was successfully used on a LOEWE Opta-Kantate with an amplitude-modulated signal generator RF1 from HEATHKIT and a CD player. The result was rated as very satisfactory.

Almost any type of ferrite pot core can also be used since a split plastic bobbin allows for the electrical separation and insulation of primary and secondary windings. In this case, enameled copper wire will suffice for both windings.

Figure 1 shows a balun used by C.P. Gallenmiller, where both windings consist of plastic-insulated stranded wire with 0.75 mm² cross-section. This was obtained from a standard mains connection cable 3x0.75. The turns ratio is 1:3. An FT82-27 toroidal core was used as the core.


{{% imgproc Balun_1 Fit "400x400 webp" %}}
*Figure 1:* Safety-correctly constructed balun. The housing is galvanically isolated from the antenna-side winding. The cover has been removed for the photo. (Photo C.P. Gallenmiller)
{{% /imgproc %}}

**Note**: G. Gauert reports that with some old devices, the antenna contributes significantly to the resonator capacitance, and therefore the mere coupling of the signal converter via a transformer can lead to undesirable damping and frequency shifts of the tuning circuit. Significant signal interference can also be the result. H. Scharfetter was able to confirm these findings with an Atwater Kent 10 from 1924. In such cases, it is recommended to connect a series of a 220pF capacitor and a resistor (470 - 2200 Ω) between the transformer output and the antenna input of the radio. This measure can usually remedy or at least significantly mitigate the problem.

## Inductive Coupling

This requires a transmit coil, which is oriented so that its axis lies as close as possible on the axis of the receiver's receiving coil for optimal coupling. This coil is best made in the form of a not too small loop with typically one to a few turns. This coil must be driven by a suitable driver amplifier.

Fig. 2 shows an arrangement implemented by H. Scharfetter with a collapsible diamond-shaped loop made of brass rods, specially built for mobile use.

{{% imgproc rahmenantenne_tx Fit "600x600 webp" %}}
*Figure 2:* Collapsible loop antenna with one turn. The receiver is a transistor radio with ferrite antenna. Power is supplied here via a 9V battery.
{{% /imgproc %}}


This loop is powered by a small battery-operated video amplifier of type AD811. The circuit corresponds to that in Fig. 3.5A in the 
<a href="https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_engl.pdf#page=23" target="_blank" rel="noopener noreferrer">
  Report 2023
</a>.

The gain can be reduced to a maximum of 5 if necessary to avoid overdriving. Since the AD811 can only deliver a maximum of 100mA output current, but the loop impedance at 500 kHz is only about j2.5 Ω, a 4:1 transformer (24:6 turns, 670µH:40µH) is connected as an impedance converter between the amplifier output and the loop terminals. This way, the AD811 'sees' together with the 50Ω resistor connected in the output path about 50 + j40Ω, which keeps the current at 5V output amplitude just under 80mA. In addition, the power dissipation in the AD811 is reliably kept below 1W, a value that should not be exceeded while maintaining safety margins (and depending on the housing). In the specific case, the AD811 is powered either by a 9V block battery or a small 12V rechargeable battery. This arrangement works over a distance of 3-4m, e.g., for typical portable radios with ferrite antenna. Fig. 3 shows a prototype built by H. Scharfetter with a collapsible and detachable square loop.


{{% imgproc rahmenantenne_balun Fit "600x600 webp" %}}
*Figure 3:* Coupling of the loop antenna to the driver amplifier (AD811) through a balun. (Note: The PCB under the toroidal core only serves as a carrier for the SMA connector; the 'transistor' below the center of the toroidal core is defective and non-functional.)
{{% /imgproc %}}

Of course, other amplifiers can also be used in this context, provided they are suitable for the frequency range and can drive sufficient current.

The selection of turns number, loop geometry, and amplifier depends on the application case. Normally, one wants to supply devices at a distance of a few meters with sufficient signal without causing interference in the wider environment. As calculations in 
<a href="/pdf/Berechnungen_Loop_Antenne_TX_fuer_Webpage_v2_reduced_ENGLISH.pdf" target="_blank" rel="noopener noreferrer">
  this document
</a> show, it is advantageous to use small numbers of turns and large-area loops instead. This is due to the fact that the axial magnetic field strength at a certain distance <i>z</i> increases proportionally to the number of turns for a given loop current, but the inductance and thus the load impedance for the amplifier increases approximately with the square of the number of turns. At a given signal voltage at the amplifier output, the current and the field decrease with the number of turns.

Since the coil represents an inductive load, the current and thus the field strength decreases inversely proportionally to the applied voltage in non-resonant operation. However, this does not pose a problem for the broadband nature of signal transmission, since the induction law at constant field in the receiver coil causes an induction voltage that increases linearly with frequency and therefore compensates for the effect again.

Two specific applications on very old radios can be seen in the following two examples:
Fig. 4 shows direct coupling into the tuning coil of a Loewe OE333 from 1927 in the context of "Season's greetings 2025" (click to go to the video):

{{< video_ext url="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/Seasons_greetings_20251220.mp4" width="30%" align="left" showframe_time="0" caption="Fig. 4: Coupling of the loop antenna to a basket coil of the Loewe OE333" >}}


Fig. 5 links to an example video by G. Gauert, in which a honeycomb coil with 75 turns is used in conjunction with an LM7171 as a driver amplifier.

{{< video_ext url="https://youtu.be/4jC2XtWUFI8" width="30%" align="left" showframe_time="0" caption="Fig. 5: Coupling of a basket coil to a transistor portable radio with ferrite antenna">}}