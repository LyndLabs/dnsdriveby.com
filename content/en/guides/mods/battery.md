---
title: "🔋 Battery"
description: "Portable power solutions for DNS Driveby."
lead: "Battery power solutions for your DNS Driveby."
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
{{< alert icon="⚠️" context="warning" text="DO NOT attempt to charge the LiPo battery directly through the D1 Mini!  Your family will die" />}}

<br>
<img src="/images/battery-mod/AAA-battery.jpeg" class="d-block w-100" alt="...">
<br>

## Official Battery Shim 
`This product is coming soon!`

## The Power Problem
While DNS Driveby kits come with a LiPo connector, powering the kits & charging them isn't so straightforward.  In fact, it can be dangerous!

**The LiPo battery JST jack passes directly to the `5V` / `USB` pin on the D1 Mini** - so if you use USB with a LiPo battery connected, it will attempt to charge it - without any regulation or protection.

<br>
<img src="/images/battery-mod/connected-lines.png" class="d-block w-100" alt="...">
<br>

## Battery Level
Reading battery level also poses a problem.  Since there's no dedicated circuit to "switch off" the connection when the LiPo battery is too low, you can [fully discharge and damage it](https://www.jauch.com/blog/en/what-actually-happens-when-lithium-batteries-are-over-charged-or-deep-discharged/).  

DNS Driveby `v1.2` kits use a resistor voltage divider to measure battery voltage, and puts the board into deep-sleep mode when the battery voltage is below `3V`.  [Read more here.]()

Using a charging solution that has **over-discharge protection** would solve this issue, but these solutions do not allow you to gauge battery level.

These are some nice options for reading battery level over I2C:
- [Adafruit LC709203F Breakout](https://www.adafruit.com/product/4712)
- [Adafruit MAX17048 Breakout](https://www.adafruit.com/product/5580)

`Support for these chips coming soon.`

## Charging Solutions
##### 1. Inline charging
There are no existing solutions I could find that offer this in a small form-factor - let alone easy + cheap to source.  But I'm designing one :)

##### 2. Charge the battery separately
**This is currently the recommended way to charge LiPo's.**  Disconnect your LiPo battery, and charge it with an external circuit like the ones listed below.  As long as your battery fits the `JST 2.0` port, and you double check the polarity, you'll be good to go!

|Name|Description|Price|
|---|---|---|
|[Adafruit Micro Lipo Charger](https://www.adafruit.com/product/4410)|Compact charging up to 500 mAh|$6|
|[Generic TP4056 Breakout](https://www.amazon.com/Charging-Lithium-Battery-Charger-Protection/dp/B08X6G26Q8/ref=sr_1_1?crid=XKXTNEH4PT79&keywords=tp4056&qid=1700888181&sprefix=tp4056%2Caps%2C160&sr=8-1)|Extremely ubiquitous LiPo charger|$1|

##### 3. Wemos Battery Shield
Don't let this board decieve you, its actually the worst charging solution I've tried.  

While it comes in D1 Mini form factor (meaning you can stack it on your existing D1 Mini), it uses a slightly-too-large `JST 2.54` connector that doesn't securely hold the battery, and also requires you to charge through a separate USB port (and it's MicroUSB, eww).

<br>
<img src="/images/battery-mod/wemos-battery-shield.jpg" class="d-block w-100" alt="...">
<br>

