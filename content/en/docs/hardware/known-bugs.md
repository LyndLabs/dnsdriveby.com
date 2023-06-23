---
title: "Known Bugs"
description: "Known DNS Driveby bugs"
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
## v1.2 PCB
* The GPS jumper pads connect `GPS-RX` to ESP8266 `RX`, and `GPS-TX` to ESP8266 `TX`.  The correct configuration is supposed to be `GPS-TX`→`RX` and `GPS-RX`→`TX`.  To fix this, `v1.2` boards route the GPS pins to `D3` & `D4` by default.

## GPS Serial Communcation
The [NEO-6M GPS Module]() uses UART to communicate over a Serial connection.  However, the ESP8266 only has a single UART bus, which is used for uploading code via USB / providing a Serial readout.  There are two things that can be done, both of which kinda suck:

1. **Software Serial** - Using pins `D3` & `D4`, you can *emulate* a Serial connection in software. However, this isn't recommended if you intend to perform WiFi recon, since SoftwareSerial relies on interrupts that crash the ESP8266.

2. **Built-in UART** - This isn't optimal, since having a free USB Serial readout is nice - but ensures reliable communication.  You can use the [jumpers]() to toggle this option. 




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