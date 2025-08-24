---
layout: default
title: Designs
---

<style>
.study-section {
  margin-bottom: 2em;
}

.study-section h2 {
  border-bottom: 2px solid #444;
  padding-bottom: 0.25em;
  margin-top: 2em;
  color: #66ccff;
}

.study-tile {
  display: block;
  background-color: #1e1e1e;
  color: white !important;
  padding: 1em 1.5em;
  margin: 0.75em 0;
  border-radius: 6px;
  text-decoration: none;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4);
  transition: transform 0.15s ease, box-shadow 0.15s ease, background-color 0.2s ease;
}

.study-tile:hover {
  background-color: #2a2a2a;
  transform: translateY(-3px);
  box-shadow: 0 8px 16px rgba(200, 200, 200, 0.6);
}

.study-tile h3 {
  margin: 0;
  font-size: 1.1em;
  color: white;
}

details {
  margin-bottom: 1.5em;
  background: #121212;
  border-radius: 8px;
  padding: 0.5em 1em;
  box-shadow: 0 2px 6px rgba(0,0,0,0.4);
}

summary {
  cursor: pointer;
  font-size: 1.2em;
  font-weight: bold;
  color: #66ccff;
  outline: none;
  list-style: none;
}

summary::-webkit-details-marker {
  display: none; /* hide default arrow */
}

/* Optional custom arrow indicator */
summary::after {
  content: " ▼";
  font-size: 0.9em;
  transition: transform 0.2s;
}

details[open] summary::after {
  transform: rotate(-180deg);
}

</style>




# 📘 Study Projects

<br><br>

---
<br>

### 🔌 Power Electronics

<details class="study-section">
  <summary>🔌 Power Electronics</summary>
  <a href="Buck_3V3-5V_in_1V_out_10W.html" class="study-tile"><h3>10W Buck 3.3-5V to 1V</h3></a>
  <a href="Boost_20V-30V_in_40V_out_600W.html" class="study-tile"><h3>600W Boost 20-30V to 40V</h3></a>
  <a href="BuckBoost_30V-60V_in_(-45)V_out_300W.html" class="study-tile"><h3>300W Buck-Boost 30-60V to 40V</h3></a>
</details>

---
<br>

### ⌨  Embedded Systems

<div class="study-section">
  <a href="RTC_Clock.html" class="study-tile"><h3>RTC CLock</h3></a>
  <a href="I2C_Tempurature_Sensor.html" class="study-tile"><h3>I2C Temperature Sensor</h3></a>
  <a href="SPI_OLED.html" class="study-tile"><h3>SPI OLED</h3></a>
</div>

---
<br>

### 📟 FPGA

<div class="study-section">
  <a href="Traffic_Light_Controller_FSM.html" class="study-tile"><h3>FSM Traffic Light Controller</h3></a>
  <a href="8_bit_ALU.html" class="study-tile"><h3>8-bit ALU</h3></a>
  <a href="Buzzer_Note_Generator.html" class="study-tile"><h3>Buzzer Note Generator</h3></a>
</div>

---
<br>

### 📡 Miscellaneous

<div class="study-section">
  <a href="study.html" class="study-tile"><h3>N/A</h3></a>
  <a href="study.html" class="study-tile"><h3>N/A</h3></a>
  <a href="study.html" class="study-tile"><h3>LTspice Thermal Simulation</h3></a>
</div>
