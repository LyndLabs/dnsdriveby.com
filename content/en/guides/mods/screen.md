---
title: "Screen"
description: "Adding a screen to your wardriving kit!"
# lead: "Adding a screen to your wardriving kit!"
date: 2022-08-27T08:48:57+00:00
lastmod: 2022-08-27T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    # parent: "get-started"
weight: 10
toc: true
---
Adding a screen to your kit makes it easy to monitor WarDriving stats at a glance - and also gives it personality!

### Components
- [SH1106]()
- [Breadboard Wires]()  

At the moment, the software only supports the I2C version of the [SH1106]().  There are plans to support the SSD1306 in the future.  SPI based screens are not supported due to lack of pins on the ESP8266. 

### Pinout
The I2C screen has an address of `0x3C`.  

|Screen|ESP8266 Pin|D1 Mini Pin|
|----|----|----|
|SDA|IO4|D2|
|SCK|IO5|D1|

|Screen Pin|ESP32-S2 Pin|S2 Mini Pin|
|----|----|----|
|SDA|IO33||
|SCK|IO35||



### Software
The screen is supported by default in software.  You don't need to do anything to enable it!  If you're interested in developing your own interfaces, check out our [UI developer docs]().

