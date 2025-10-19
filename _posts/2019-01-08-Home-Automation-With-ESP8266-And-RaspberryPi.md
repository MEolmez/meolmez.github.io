---
layout: post
title:  "Home Automation with ESP8266 and Raspberry Pi"
date:   2016-11-11 16:16:01 -0600
categories: arduino 
---




Home Automation with ESP8266 and Raspberry Pi


In this guide , we will look at how we can measure temperature of different rooms , send them to Raspberry Pi , and view that from anywhere.

As hardware we will use Raspberry Pi , ESP8266 , arduino pro mini , DHT11 temp sensor , nRF24L01+ and for software we will use Domoticz and Mysensors.

1-) First , we need to assign a static ip to Pi following the instructions here -> https://www.modmypi.com/blog/how-to-give-your-raspberry-pi-a-static-ip-address-update

Then to install domoticz; This is the software we will use to display our readings in a webpage. 

curl -sSL install.domoticz.com | sudo bash

command will install domoticz on pi.


2-) For translating the messages from arduinos to something domoticz will accept , we need a MQTT broker. Mosquitto is a popular one.
we can install it by 
sudo apt-get install mosquitto mosquitto-clients
commands on pi.

3-) Now we will setup ESP8266 as a gateway between nrf radio nodes and pi. The code is here -> https://www.mysensors.org/build/esp8266_gateway , but we will need to change a couple of things. 

We change this lines so domoticz accepts our readings
// Set this node's subscribe and publish topic prefix
#define MY_MQTT_PUBLISH_TOPIC_PREFIX "domoticz/in/MyMQTT"
#define MY_MQTT_SUBSCRIBE_TOPIC_PREFIX "domoticz/out/MyMQTT"

We will assign gateway a static ip so things dont broke when router resets.
// Enable MY_IP_ADDRESS here if you want a static ip address (no DHCP)
#define MY_IP_ADDRESS 192,168,1,26

This is the ip of the pi
// MQTT broker ip address.
#define MY_CONTROLLER_IP_ADDRESS 192, 168, 1, 24

And of course we change the wireless network ssid and password.

Then we connect the radio module to esp8266 as shown in here -> https://www.mysensors.org/build/connect_radio

4-) Now to the Temperature sensor node. Connection diagram and code is here -> https://www.mysensors.org/build/humidity
