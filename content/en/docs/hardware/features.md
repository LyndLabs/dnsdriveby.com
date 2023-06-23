---
title: "Features"
description: "Get started with the DNS Driveby"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "get-started"
weight: 20
toc: true
---
## Wardriving Hardware
This kit uses the ubiquitous [D1 Mini]() form-factor for the WiFi chip, and a standard UART GPS module, the [NEO-6M]().  They are connected together through SoftwareSerial on pins `D3` & `D4`. 

## Deep Sleep Mode
The deep-sleep mode works by connecting a sensitive motion sensor to the `reset` pin on the ESP8266.  

To prevent "false resets" while the payload is running, we use a transistor (connected to `D0`) to prevent it from grounding while the device is active!

## Battery Meter
This battery meter works by using a simple [voltage divider circuit]() connected to the only analog pin `A0`.

The values `360K` & `100K` allow us to map the LiPo battery's voltage range of `4.2v - 3v` to `.9v - .6v` (since the Analog pin reads values `0-1v`).

However, you only need the `100K` ohm resistor since the D1 mini has a [built-in resistor]()!


## Screen
While DNS Driveby doesn't support graphics in the software **yet**, some [other projects]() do!  

I recommend using a 4 pin [SSD1306]() or [SH1106]() screen, but be careful to check that the pinout matches.