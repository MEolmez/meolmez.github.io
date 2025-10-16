---
layout: post
title:  "Arduino Low Power Consumption DS18B20 Temperature Probe With Display"
date:   2021-01-20 16:16:01 -0600
categories: arduino 
---

I wanted to make a waterproof temperature probe with a low current consumption. 

First part is the DS18B20 probe with the waterproof casing.

Second part is 4 digit display with the TM1637 chip. I find these kind of displays very useful , even though they only have 4 digits sometimes that is all you need.

I wanted this project to use very little current, so i used an arduino pro mini 3.3v. 

For further reducing the current consumption i set the displays brightness to lowest and used a sleep mode so arduino only wakes up at 2 second intervals, takes the measurement, updates the display, and sleeps again.

This way the entire setup uses 6ma. Its possible to further reduce this values by using the internal pull up resistor for DS18B20 and removing the onboard power led from the arduino.


Code is <a href="https://github.com/MEolmez/arduino-ds18b20-temperature-probe-with-display">HERE</a>


![usefulimage]({{https://meolmez.github.io}}/assets/tempProbe.jpg)




