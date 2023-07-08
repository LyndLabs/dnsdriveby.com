---
title: "Threaded Inserts"
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
{{< alert icon="⚠️" context="info" text="v1.2 kits didn't ship with threaded inserts, but have the option to add them." />}}

DNS Driveby enclosures are 3D printed, so directly tapping / adding screws can wear down the plastic over time.  Threaded inserts are a slick & easy way to solve this problem!

<img src="/images/inserts/threaded-inserts.jpg" title="Thumbnail Image"/>

### Parts

- `1/4" 20` [insert](https://www.aliexpress.us/item/2255799934372578.html)
- `M2.5` [insert]() 
- `M2.5` [screw]()

I typically use `M2.5` x `6mm` threaded inserts for fastening the enclosure, and screwing down the PCB.  Using a screw of the same height (`6mm`) works fine, since the PCB is about `1.6mm` thick.  I find `M2.5` optimal for most of my designs, and usually make the PCB mounting hole ~ `2.6 mm` to offer clearance.

<img src="/images/inserts/screws.jpg" title="Thumbnail Image"/> <br/>

`1/4" 20` x `6mm` threading is an industry standard tap size for camera mounting, so I like to add these to my designs to make them easily mountable to bikes, tripods, and other accessories.

I recommend using **Uxcell** inserts since they're easy to source.

<img src="/images/inserts/bike-mount.jpg" title="Thumbnail Image"/> <br/>


### Designing for Heat Inserts 
When designing a hole for threaded inserts, you have to compensate for [print shrinkage](https://filament2print.com/gb/blog/136_warping-contractions-3D-printing-parts.html) and heat warping during installation.

<div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/inserts/warp-damage-2.JPG" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>Example of warp damage & plastic filling from insert going askew.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/inserts/warp-damage-1.JPG" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <p>Warp damage from insufficient clearance.</p>
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

#### 1. Heat Warping
Heat warp happens when the insert doesn't have enough surrounding material to dissipate the heat while pressing.  

I like to make sure my heat inserts have at least `2mm` clearance on all sides and usually extrude a special pad to allow for this, as seen below.

Sometimes, the heat insert can also go askew while inserting (see picture below), and catch plastic inside of it.  I typically add 2 bevels to preempt this - the larger recess allowing me to easily press-fit the insert halfway into place.

<img src="/images/inserts/double-circle.png" title="Thumbnail Image"/>

#### 2. Print Shrinkage
Combating print shrinkage is pretty easy.  I typically scale my designs in the `xy` dimensions by `101 %` in my slicer settings, and add a `.1-2 mm` tolerance to my holes.

<img src="/images/inserts/slicer.png" title="Thumbnail Image"/>

#### 3. Recommended Dimensions

**1/4" 20**: *Recommended profile for `1/4" 20` x `6mm` insert*

|Name|Dimension|Notes|
|---|---|---|
|Small Radius|`8 mm`||
|Large Radius|`8.4 mm`|~ `3-4mm depth`|
|Total Depth|`7 mm`||

**M2.5**: *Recommended profile for `M2.5` x `6mm` insert*

|Name|Dimension|Notes|
|---|---|---|
|Small Radius|`3.2 mm`||
|Large Radius|`3.8 mm`|~ `3-4mm depth`|
|Total Depth|`7 mm`||


### How to Install
Pictures coming soon.  This is a good guide for [adding threaded inserts](https://www.makerbot.com/professional/post-processing/inserts/).

**Tools**
- Tweezers or Pliers
- Soldering Iron

1. Press fit your insert into place, until it rests about halfway in the hole.
2. You can hold the insert stable using tweezers / needle-nose pliers.
3. Heat up your soldering iron (~ 300 F) and gently press the insert into place.
4. Be patient!  Pressing too fast can cause the print to warp or melt.
