---
title: "Jumper Pads"
description: "Get started with the DNS Driveby"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "get-started"
weight: 100

toc: true
---

{{< alert icon="⛔️" text="Most of these advanced features are experimental!" />}}

On the back of your PCB, you'll notice jumper pads that can be used to re-route pins, or short connections using a little solder.  **Don't touch these unless you know what you're doing!**

|Jumper|Name|Description|
|----|----|----|---|
|**JP1**|GPS Low-Power|Disconnects GPS from power in Sleep Mode|
|**JP2**|GPS RX Switch|Switches `GPS RX` pin to `D3` or `TX`*|
|**JP3**|GPS TX Switch|Switches `GPS TX` pin to `D4` or `RX`*|
|**JP4**|LiPo Meter Passthrough|Measures battery with a single resistor|
|**JP5**|LiPo Switch Bypass|Acts as a permanent switch|

**`RX` and `TX` refer to ESP8266 pins*

## Default Connections
*chart here*


## Jumper Descriptions
#### JP1
This experimental feature disconnects the GPS from power when the ESP8266 enters deep-sleep.  

The GPS is connected directly to the 5V line by default, and its not recommended to re-route this deep-sleep mode until tested further.

#### JP2 & JP3
The ESP8266 is finicky when talking to the GPS, which uses [Serial]().  

The GPS is connected to `D3` & `D4` by default, which requires SoftwareSerial to communicate - but you re-route the pins to connect directly to the ESP8266 `RX` & `TX` pins which use a reliable Hardware Serial connection.

[*See known bugs for more info.*]()

#### JP4
The [Battery Meter]() feature uses 2 resistors to measure voltage on analog pin `A0`.

Since the D1 Mini has a [built-in pulldown resistor]() on pin `A0` already, the `360K ohm` resistor is redundant, and can be bypassed by just shorting the connection.

It's still included to support other boards which might not have an internal resistor.

#### JP5
Shorting this jumper will connect the LiPo battery directly to the ESP8266, if you don't have a physical switch.  If you're powering via USB, you won't need this feature.