---
title: "💤 Deep Sleep"
description: "Using low-power mode on your DNS Driveby Kit"
lead: "Using low-power mode on your DNS Driveby Kit 🔋"
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
**Deep sleep mode** allows your wardriving kit to preserve energy when the device isn't in motion. Your kit automatically shuts off after a couple minutes of inactivity, and wakes up when again when motion is detected!

This lets you attach the kit to a car, a cat, or other similar object for motion-triggered tracking.

### Parts
|Type|Part|#|
|----|----|----|
|Shake Sensor|[SW-18010P]() *|1|
|NPN Transistor|[2N3904]()|2|
|Resistor|10K Ω|2|

*Other SW-180xxP switches will work, but part 18010P is the most sensitive*

### How It Works
The ESP8266 can be placed into a timed deep sleep using the builtin`ESP.deepSleep(uS)` function, or indefinitely with `ESP.deepSleep(0)`.  The latter sleeps until the ESP8266 is reset by grounding the `RST` pin.

Using a [shake sensor]() allows us to short the `RST` pin to `GND `when motion is detected without needing any code - but we don't want to accidentally trigger resets while driving.

We solve this by using digital logic that prevents the `RST` pin from grounding while the ESP8266 is powered up.  This simple circuit uses transistors in a `NOT Gate` configuration to prevent the `RST` from grounding if a `HIGH` current is detected from pin `D0`.  Otherwise, when the ESP8266 is in sleep mode (no current from `D0`), the `NOT Gate` allows the circuit to reset.

<img src="/images/reset-circuit.jpg">

### Code
Try this really basic Arduino sketch to try this feature out: 

```
void setup() {

  // start Serial
  Serial.begin(115200);
  Serial.println("ESP8266 Started!");

  // set pin D0 HIGH on startup
  pinMode(D0, OUTPUT);
  digitalWrite(D0, HIGH);

  // sleep after 15 seconds
  Serial.println("Sleeping in 10 seconds!");

  unsigned long ptime = millis(); unsigned long ctime = millis();
  while (ctime-ptime <15000) { 
    ctime = millis();
    Serial.println(ctime/1000);
  }

  // SLEEPY TIME
  ESP.deepSleep(0);

}

void loop() {
  //
}
```

