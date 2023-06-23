---
title: "Assembly Guide"
description: "Soldering & Assembling Your DNS Driveby Kit"
lead: "Soldering & Assembling Your DNS Driveby Kit"
date: 2022-08-27T08:48:57+00:00
lastmod: 2022-08-27T08:48:57+00:00
draft: false
images: ['Purple_Thumbnail.png']
menu:
  docs:
    # parent: "get-started"
weight: 20
toc: true
---
<img src="/images/assembly/0-components.png" title="Thumbnail Image"/>


## Basic Assembly
First make sure your kit has all of the following parts!  This is everything you need to get started with basic wardriving.


| Main Components | Description | Count |
| --- | --- | --- |
| [D1 Mini](https://www.amazon.com/HiLetgo-ESP32-S2FN4R2-ESP32-S2-Type-C-Connect/dp/B0B291LZ99/ref=sr_1_1?crid=3RFAV6TMVXMQB&keywords=s2+mini&qid=1683797716&sprefix=s2+mini%2Caps%2C1335&sr=8-1) | ESP8266 Wi-Fi Microcontroller | 1 |
| [GPS Module]() | NEO-6M UART GPS | 1 |
| [DNS Driveby PCB](https://lyndlabs.io/products/dns-driveby-kit) | |1|
|3D Printed Enclosure||1|
| Female Socket | For Mounting the Microcontroller |2|
| Male Header | D1 Mini Headers |2|




### 1. PCB Socket
{{< details "Tips">}}
* Insert the 2 female sockets on the PCB face up.
* Flip the PCB over so the sockets are flush on a table or flat surface - and solder!
* You can balance the PCB by putting something underneath the other end (I used the GPS module)
{{< /details >}}

<div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/assembly/1-socket.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>1. Place the sockets in the microcontroller footprint.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/1-socket-flush.png" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <p>2. Flip over, and lay flush on a flat surface.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/1-socket-solder.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>3. Solder the sockets on the reverse side!</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

### 2. D1 Mini
{{< details "Tips">}}
* Insert the 2 male headers in the PCB socket, long side down
* Stack the D1 mini on top, and solder the pins!
* Using the PCB socket keeps the Microcontroller steady while soldering
{{< /details >}}

<div id="headers" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/assembly/2-header-1.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>1. Insert male headers into socket, long side down.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/2-header-3.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>2. Set D1 mini on top of headers and solder!</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#headers" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#headers" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

### 3. GPS Module
{{< details "Tips">}}
* Solder down the Antenna with a generous amount of solder
* Adhering the Antenna can be difficult so I'd recommend using flux, or "scrubbing" the solder back & forth against the Antenna ground plane (see video)
* You can keep the D1 Mini inserted to help balance the GPS while soldering.
{{< /details >}}

<div id="gps" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/assembly/3-gps-1.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>1. Pass the GPS Antenna connector through the hole.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/3-gps.png" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <p>2. Connect the GPS Antenna to the u.fl connector.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/3-gps-3.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>3. Solder the GPS ground plane!</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/3-gps-4.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>4. Insert the 4 pin header in the GPS, and align with the PCB.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/assembly/3-gps-5.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>5. Solder the GPS pin header on both sides!</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#gps" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#gps" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

### 4. Case Assembly
{{< details "Tips">}}
* The case is snap-fit, so simply press the PCB into place!
* If you wish, you can also use heat-inserts & screws to keep it in place

[Check out this advanced guide to see how]().
{{< /details >}}

<div id="assembly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/kits/thumbnail.JPG" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="/images/kits/Raw-Side-by-Side.JPG" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="/images/kits/Stacked.JPG" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="/images/kits/Head-on-C3.JPG" class="d-block w-100" alt="...">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#assembly" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#assembly" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
<br/>
{{< alert icon="⚠️" context="info" text="Before you can use your kit, don't forget to flash the firmware!" />}}
<hr>

## Low-Power & Battery Assembly
Your kit is ready to wardrive!  But if you're looking to take it a step further and also try out the experimental deep sleep mode / battery feature, you'll need the following components:

| Low-Power Components | Description | Count |
| --- | --- | --- |
| Resistors  | 10K Ω |3|
| Transistors | Resistors for Power Management |2|
| Motion Sensor | Resistors for Power Management |2|

| Battery Components | Description | Count |
| --- | --- | --- |
| Resistors  | 10K Ω |3|
| Transistors | Resistors for Power Management |2|
| Motion Sensor | Resistors for Power Management |2|

**Assembly Instructions & Docs coming soon.**

{{< alert icon="⚠️" context="info" text="Due to shipping restrictions, DNS Driveby kits don't ship with LiPo batteries, but you can find the required components above." />}}

