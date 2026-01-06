---
layout: post
title:  "RC Crawler"
date:   2025-11-20 17:16:01 -0600
categories: [DIY]
tags: [DIY, radio, RC]
image:
  path: /assets/RoverEvo.jpg
  alt: rc

---

Apparently as a kid I broke up all my RC cars to look inside and learn how they work, I failed. And one point my parents stopped buying me RC cars. I waited a loooong time, but I learned how they worked! 
And of course I had to make one myself. My first attemp was a KNEX car. I love KNEX! I fell in love with them when they were giving very small kits of it with newsletters when I was very little. When I had a job and had the money to buy them they were not available in my country, so I bought a set from Amazon US, thinking no way it would arrive, and it did!  It was a lot of fun to build, I just love gears. But it was not exactly what I had in mind, so it got disassembled.

<img src="/assets/KnexCar.jpg" style="max-width:700px; max-height: 550px;" alt="KnexEvo">

My second attempt used those generic yellow geared motors with an esp8266 and DRV8833 driver. But I did not want a normal RC car, I wanted it to be driveable in many different surfaces, and wheels that come with the motors did not have much grip.
So I moved to wheels from KNEX. Alas, the KNEX wheels did not cut it either, I kind of placed that project on back burner.
Some time later I found the perfect wheels from banggood. Ordered immediately. They were 12 cm high, perfect off-road wheels. But of course I could not drive them with those yellow motors, so the search for the motor begun.

I wanted this vehicle to be slow but powerful, I needed geared motors. They were pretty expensive which led me to second hand market and scrap yards. After couple of months I found my motors, 12v 150 RPM metal geared motors from a scrap yard. I needed 4, but I bought 5 and made a hand crank powered emergency lamp from one of them.

Those motors were powerful alright, and consequently poor DRV8833 had no hope of driving them. I ordered a pair of BTS7960B, saw them on a James Bruton video.
For power, I used my 3s4p battery pack I made from 18650 cells I salvaged from flea market find laptop batteries. It was starting to take shape!
At first I was using Blynk. After another break from the project I found out they removed the app and changed focus. This gave me the push I needed to make the car truly RC.

<img src="/assets/RoverEvo.jpg" style="max-width:700px; max-height: 550px;" alt="RoverEvo">

Next addition was NRF24L01+, with it I changed from esp8266 to Arduino Uno. Code side of things were easy with Blynk, and NRF24L01+ pushed me to learn more and more of Arduino environment. I had to build a remote controller too.
<img src="/assets/rcTransmitter.jpg" style="max-width:700px; max-height: 550px;" alt="transmitter">

Finally it was working like expected. It had good range too. Also I changed the big BTS7960B drivers to much more space efficient VNH2SP30 Dual Motor Shield. 
The more I used the car the more I hated the Joystick module. It made fine control impossible, even though it was a potentiometer based joystick it was acting like an on/off stick, you either stopped or got full throttle. Of course I had to change it.

I got the idea to use hall effect based joystick modules people use to change ps5 controller joysticks. Ordered some from Temu, figuring out the pins took some digging, but after calibrating the values they give in the sofware they worked like charm! At the start I forgot that they were 3.3v devices and connected them straight to 5v, thankfuly they did not fail.