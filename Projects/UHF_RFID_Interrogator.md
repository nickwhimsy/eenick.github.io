---
layout: default
title: Projects
---

# Design objective and goal

The design for the reader was determined by certain needs. The need to ensure that the tags can be read from a distance, targeting 3 feet, and be cost-effective enough to undercut the cost of competitors by a few hundred dollars. The first aspect of meeting these requirements is to ensure that the design meets legal requirements for being sold. In the case of this project, the market was the US, which has requirements shown in Table 1.

Table 1: Design Parameters

| Parameter | Value |
|:----------:|:----------:|
| Operating Frequency  | 902 MHz - 928 MHz  | 
| Channel Spacing  | 500 KHz  | 
| Max Transmitted Power  | +30 dBm | 
| Data Rate | 26.7 Kbps - 128 Kbps | 
| Reader Modulation  | DSB/SSB/PR-ASK  | 


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




<img src="https://github.com/nickwhimsy/eenick.github.io/blob/3b6dcc4a2d16cec37abf62329265e4ad5d283c77/assets/img/RFID_Interrogator/FilterBode.png" alt="Band Pass Bode Plot">
