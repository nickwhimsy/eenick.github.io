---
layout: default
title: Projects
---

# Design objective and goal

The design for the reader was determined by certain needs. The need to ensure that the tags can be read from a distance, targeting 3 feet, and be cost-effective enough to undercut the cost of competitors by a few hundred dollars. The first aspect of meeting these requirements is to ensure that the design meets legal requirements for being sold. In the case of this project, the market was the US, which has requirements shown in Table 1.


<div align="center">
  
Table 1: Design Parameters

| Parameter | Value |
|:----------:|:----------:|
| Operating Frequency | 902 MHz - 928 MHz | 
| Channel Spacing | 500 KHz | 
| Max Transmitted Power | +30 dBm | 
| Data Rate | 26.7 Kbps - 128 Kbps | 
| Reader Modulation | DSB/SSB/PR-ASK | 

</div>

On top of these requirements, the device should be functional in a variety of environments and should perform on par with more established brands.

## Theory

The fundamental purpose of RFID is to receive and send data. To do this over the air, it is most effective to utilize higher frequency bandwidths to prevent data loss from interference sources. However, processing frequencies at that speed is difficult, and as such, it becomes favorable to demodulate the frequency, so the data waveform can be analyzed at lower frequencies. For this, amplitude modulation is used. However, the receiving data can also include many unwanted interference signals from the environment or other electromagnetic sources, and so the signal needs to be filtered. The signal may also be weak, and as such it must also be amplified. Figure 1 shows the general processing of a signal from the antenna to the microcontroller.




From left to right, the weak signal enters the antenna and is filtered so only the desired range of frequencies is passed through, and then amplified. Here it goes into a mixer, with an oscillator, to then demodulate the signal, in order to leave only the peaks that contain the data. That signal is then processed through the Analog to digital converter, and is output as a digital signal, in this case, Serial Protocol Interface, or SPI.

One of the first decisions to be made was the frequency range that needed to be isolated. Since the goal was UHF, and the market was in the US, the range was 902MHz - 928MHz, per the FCC standards. In order to isolate a range, a bandpass filter is used, getting a frequency response as shown in Figure 2.




In order to isolate the correct range, a Chebyshev filter design was used for its steep roll-off properties, better isolating the passband portion of the filter. Figure 3 shows an example of a Chebyshev filter.



To ensure that the filter has the correct capacitor values we can use a few useful equations. First, knowing that our bandwidth is 902-928MHz, allows us to utilize the following equation:

$$
BW = \frac{f_0}{Q}
$$

where BW is the bandwidth, f0, is the center frequency and Q is the quality factor, which for RFID is typically 10-20. Solving for fowill then give the center frequency.

$$
f_0 = \frac{1}{2 \pi \sqrt{LC}}
$$

With this information, we can calculate values for the inductor and capacitor by utilizing the angular frequency, 0=2fo, and using the following equations.

$$
L = \frac{1}{\omega_0^2 C}
$$

$$
C = \frac{1}{\omega_0^2 L}
$$


The signal integrity of the filter, however, depends on much more than just the capacitors and inductors used for the design. One important consideration is the material that the signal passes through. Since the intent is to utilize Ultra High Frequency (UHF) RFID, the material must have a low dielectric constant and low loss tangent. For this reason, a PCB material such as Rogers 4003C would be much more effective than a standard FR-4 material. Table 2 shows a comparison of the two materials.

<div align="center">

### Table 2: Rogers 4003C vs FR4

|  | Rogers 4003C | FR-4 |
|:----------:|:----------:|:---------:|
| Dielectric Constant  | 3.3-3.5 | 4.5 |
| Loss Tangent | 0.0027 | 0.02 - 0.03 |
| Impedance Stablility  | Excellent | Moderate |

</div>

Signal integrity is at the core of the design, as it is important to minimize loss and reflections along the path of the signal. Another important consideration in this regard is ensuring that the traces follow a set of important rules in order to ensure that reflections and loss are minimized.


One aspect of this is ensuring that the traces maintain an impedance that is consistent across the circuit. To ensure that the signal was well shielded as well, we chose a coplanar waveguide as shown in Figure 4.


<div align="center">

<img src="https://github.com/nickwhimsy/eenick.github.io/blob/3b6dcc4a2d16cec37abf62329265e4ad5d283c77/assets/img/RFID_Interrogator/CoplanarWaveguide.png" alt="Coplanar Waveguide">

Figure 4: Coplanar Waveguide. (Altium Designer)

</div>


The target impedance for RFID antenna is 50, which means our traces need a characteristic impedance, Z0, that is the same. The impedance of a copper trace is defined by the cross-sectional area, and as the thickness can be defined at the standard 1OZ or .035mm, the width is the parameter that needs to be defined. This can be done via the equation:

$$
Z_0 = \frac{60}{\sqrt{\varepsilon_\text{eff}}} \ln\left( 1 + \frac{4h}{w + 2g} \right)
$$



<div align="center">

<img src="https://github.com/nickwhimsy/eenick.github.io/blob/3b6dcc4a2d16cec37abf62329265e4ad5d283c77/assets/img/RFID_Interrogator/FilterBode.png" alt="Band Pass Bode Plot">

Figure 12: Bandpass filter frequency response.

</div>

