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

<img src="https://github.com/nickwhimsy/eenick.github.io/blob/3b6dcc4a2d16cec37abf62329265e4ad5d283c77/assets/img/RFID_Interrogator/FilterBode.png" alt="Band Pass Bode Plot">
