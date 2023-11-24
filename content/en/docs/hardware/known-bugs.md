---
title: "Known Issues"
description: "Known DNS Driveby Issues"
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
{{< alert icon="⚠️" context="warning" text="This page documents hardware issues, which you can help point out on our GitHub!" />}}

Please reach out to [support@lyndlabs.io]() for support & replacements!

## Resources:
Please [create a Github Issue]() on the official Hardware Repo to help track new problems!
For replacement kits & support, reach out to [support@lyndlabs.io]() or join our [Discord](https://discord.gg/PewDxbUfam).

## Kit Specific Issues:
#### v1.2
- **GPS**: The ESP8266 only has 1 native Serial Port, so we added jumper pads to toggle between `UART` and pins `D3  / D4`.  The `UART` lines are swapped, so `v1.2` kits ship with the jumper pads cut, and wired to `D3 / D4`. 
- **LiPo**: Terminal pinout has "reversed" polarity (see Sony / [Adafruit Standard](https://forums.adafruit.com/viewtopic.php?p=776952&sid=aeaa63c8b753bc16bb6dbd94a9a2c87c#p776952))
- **Screen**: Polarity reversed from standard screens

#### v1.3
-  **Counterfeit Modules:** A large batch of failed & counterfeit GPS Modules were shipped to me in early August, and a handful of customers were affected by this lack of QA.  Please contact for support & replacements!


## GPS Serial Communcation
The [NEO-6M GPS Module]() uses UART to communicate over a Serial connection.  However, the ESP8266 only has a single UART bus, which is used for uploading code via USB / providing a Serial readout.  There are two things that can be done, both of which kinda suck:

1. **Software Serial** - Using pins `D3` & `D4`, you can *emulate* a Serial connection in software. However, this isn't recommended if you intend to perform WiFi recon, since SoftwareSerial relies on interrupts that crash the ESP8266.

2. **Built-in UART** - This isn't optimal, since having a free USB Serial readout is nice - but ensures reliable communication.  You can use the [jumpers]() to toggle this option. 

## SD Card Prevents Boot
This issue has been fixed in `v1.3` PCB's!

Previously, having an SD Card plugged into the kit would prevent the ESP8266 from booting, since the SPI pins are shared with the internal flash memory.  I suspect it was attempt to boot from the SD Card.

This issue is solved by adding a pull-down resistor to pin `D8`, which is used for `CS`.







<!-- 
{{< alert icon="⛔️" text="Most of these advanced features are experimental!" />}}

On the back of your PCB, you'll notice jumper pads that can be used to re-route pins, or short connections using a little solder.  **Don't touch these unless you know what you're doing!**

|Jumper|Name|Description|
|----|----|----|---|
|**JP1**|GPS Low-Power|Disconnects GPS from power in Sleep Mode|
|**JP2**|GPS RX Switch|Switches `GPS RX` pin to `D3` or `TX`*|
|**JP3**|GPS TX Switch|Switches `GPS TX` pin to `D4` or `RX`*|
|**JP4**|LiPo Meter Passthrough|Measure battery with a single resistor|
|**JP5**|LiPo Switch Bypass|Acts as a permanent switch|

**`RX` and `TX` refer to ESP8266 pins*
### JP1

`D3`__`RX`→`TX`
### JP2 & JP3
`D3` __ `GPS TX`→`RX`  
`D4` __ `GPS RX`→`TX`
### JP4
### JP5
Don't have a physical switch?  Shorting this jumper lets you bypass the need for one, by grounding the LiPo connector.  If you're powering via USB, you won't need this feature at all. -->