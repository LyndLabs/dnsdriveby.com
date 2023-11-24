---
title: "📡 External Antenna"
description: "How to modify DNS Driveby Kits with a Long Range Antenna. "
lead: "Modify Your DNS Driveby Kit for Long-Range WiFi Sniffing!"
date: 2022-08-27T08:48:57+00:00
lastmod: 2022-08-27T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    # parent: "get-started"
weight: 40
toc: true
---
<br>
<img src="/images/antenna-mod/dns-driveby-antenna-tds.jpeg" class="d-block w-100" alt="...">
<br>

## Long-Range WiFi
If you want to give your kit extra range for attacks or WiFi sniffing, adding an external antenna is the way to go! 

Our kits do not ship with this by default since the adapter is hard to source in bulk, and this mod requires surface-mount soldering - which is difficult and time consuming for beginners.  

## Mod Guide
This mod requires delicate surface mount soldering.  So whip out those tweezers and solder flux!  I dont recommend trying this if you haven't SMD soldered before.

#### Parts
- [U.FL to RP-SMA Adapter](https://www.aliexpress.us/item/3256803540898095.html?spm=a2g0o.productlist.main.1.7378734f0feWyv&algo_pvid=eee9470a-8cbf-40f9-8f21-4a3b02141b64&algo_exp_id=eee9470a-8cbf-40f9-8f21-4a3b02141b64-0&pdp_npi=4%40dis%21USD%211.05%210.78%21%21%211.05%21%21%402101d64d17008602120628302ea981%2112000030178625784%21sea%21US%212008607852%21&curPageLogUid=lkcy9wAlaYlS)
- [D1 Mini Pro](https://www.amazon.com/CANADUINO-ESP8266-Module-External-Antenna/dp/B07GD79DGR)


{{< alert icon="⚠️" context="info" text="RP-SMA (reverse polarity) is recommended over SMA since most WiFi adapters user it.  U.FL is also the same as IPX-1 or IPEX-1 connectors.  I recommend getting the black cable over RG178." />}}

#### Tools
- [Solder Flux](https://amzn.to/3uDI327)
- [Angled Tweezers](https://amzn.to/3MZM3QO) (they're just nicer)

#### Steps
- The D1 Mini Pro comes with a U.FL connector to interface with external antennas.  By default it uses the onboard ceramic antenna, so we have to reposition a surface-mount resistor to switch the antenna trace.  Pictured below is the correct orientation.
- Typically, you would apply flux, and use a hot air-gun + tweezers to remove & reposition the resistor.  However, I'm able to re-position the resistor with just a soldering iron since its small enough.  A [hotplate]() also works!

<!-- <img src="/images/antenna-mod/d1-pro-components.png" title="Thumbnail Image"/> -->
<div id="headers" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/antenna-mod/d1-pro-components.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>1. You will need to reposition the SMD resistor to change the antenna path.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/antenna-mod/d1-pro-pads.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>2. These SMD pads let you orient the resistor.</p>
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
<br>

- The right angle SMA jack should be oriented "forward", solder it down underneath the board!  It overhangs some components on the right side of the PCB.  
<br>
<div id="sma" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/antenna-mod/ufl-to-sma.png" class="d-block w-100" alt="...">
      <!-- <div class="carousel-caption d-none d-md-block">
        <p>1. You will need to reposition the SMD resistor to change the antenna path.</p>
      </div> -->
    </div>
    <div class="carousel-item">
      <img src="/images/antenna-mod/rp-sma.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
          <p>RP-SMA Connector</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#sma" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#sma" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

## Choose an Antenna
There's 2 basic types of antennas you can pick for higher gain - **omnidirectional**, or **directional**.

I typically use an omnidirectional antenna for wardriving, since they have a better spread for quick surveying.  

For foxhunting, or long-range attacks where you're stationary, I definitely recommend a directional yagi antenna!  For [indoor fox-hunting](https://www.youtube.com/watch?v=bpR56Ua8v9s), a pannel antenna is better suited. 

- Omni - <a target="_blank" href="https://www.amazon.com/Alfa-ARS-N19-OMNI-Directional-High-Gain-Adapters/dp/B009H028CM/ref=sr_1_3?crid=1F2Q75H0C95TX&amp;keywords=alfa+antenna&amp;qid=1700855718&amp;sprefix=alfa+antenna%252Caps%252C216&amp;sr=8-3&_encoding=UTF8&tag=lyndlabs-20&linkCode=ur2&linkId=ffb1236b525705ef5b0332177d4cebf8&camp=1789&creative=9325">Alfa ARS-N19</a>
- Yagi - [SimpleWiFi](https://simplewifi.com/products/yagi)
- Pannel - [Alfa APA-M25](https://amzn.to/3Tewedl)

<br>
<img src="/images/antenna-mod/dns-driveby-computer.jpeg" class="d-block w-100" alt="...">
<br>