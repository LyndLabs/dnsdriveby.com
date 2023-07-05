---
title: "Firmware"
description: "Updating your DNS Driveby Firmware"
lead: "Updating your DNS Driveby Firmware"
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
### 1. Install dependencies
All you need is [Docker]() and [Make]()!
```
sudo apt install docker make
```
### 2. Clone the GitHub Repo
You can use git to download the [source code](https://github.com/LyndLabs/DNS-Driveby). You can also download it as a [zip file]().

```
git clone https://github.com/LyndLabs/DNS-Driveby
```

### 3. Navigate into Code Folder

```
cd DNS-Driveby/src/Demo 
```
### 4. Flash the code!
You can generate your own DNS Token at [canarytokens.org](https://canarytokens.org), and make sure to replace it below!
```
sudo make flash canaryurl = "<CANARYTOKEN>"
