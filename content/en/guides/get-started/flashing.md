---
title: "Firmware"
description: "Update your DNS Driveby Firmware!"
lead: ""
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
{{< alert icon="⚠️" context="warning" text="Your kits are becoming more wardriving-focused!  Check out \"Other Projects\" to see other supported projects, including DNS Driveby itself." />}}

## Instructions
This guide will help you update your DNS Driveby kits with the latest wardriving firmware, but you can also flash other [supported projects]()!

The [Web Flashing Guide]() lets you easily flash your kit without any tooling, but you can also use [ESPTool if you prefer Command Line]().

## Flash w/ Web Browser (WebSerial)
Thanks to [WebSerial](), an experimental feature in [Google Chrome](), we can easily interact with microcontrollers and serial devices from a web browser!
##### 1. Downloads  
- [Latest Wardriver Binary](https://github.com/LyndLabs/Wardriver/releases/tag/latest)
- [Google Chrome Browser]()

##### 2. Place Kit in Flash Mode
This step is only necessary for `ESP32` based kits, and is currently not available.

##### 3. Web Flashing
- Open the [Web Flasher Application]()
- Connect to Your Kit, which identifies as a generic serial device
- Upload your `.bin` firmware file!
- Reset your kit and you're ready to wardrive :)
</br>

<div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/images/flashing/web-step-1.png" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <p>1. Connect to the Kit via WebSerial</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="/images/flashing/web-step-2.png" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <p>2. Erase, Upload, and Flash Firmware!</p>
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


## Flash w/ Command Line (ESPTool.py)
##### 1. Downloads
- [Latest Wardriver Binary](https://github.com/LyndLabs/Wardriver/releases/tag/latest)
- [ESPTool.py](https://github.com/espressif/esptool)

##### 2. Place Kit in Flash Mode
This step is only necessary for `ESP32` based kits, and is currently not available.

##### 3. Find Serial Port & Erase Flash
- Find the Serial Port your device is connected to:
  - Windows: `Found via Device Manager`  
  - MacOS: `ls /dev/cu*`  
  - Linux: `ls /dev/tty*`  

<br/>

- Erase the flash:

```
esptool -p <SERIAL_PORT> erase_flash
```

##### 4. Flashing
Run the following command to flash the latest release file to your Kit!
```
esptool -p <SERIAL_PORT> write_flash -z 0 <BINARY_FILE>.bin
```