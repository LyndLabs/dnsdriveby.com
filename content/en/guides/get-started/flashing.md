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
{{< alert icon="⚠️" context="info" text="Updates & more instructions coming soon." />}}
### 1. Install dependencies
All you need is [Docker](https://www.docker.com/) and [Make](https://www.gnu.org/software/make/)!
```
sudo apt install docker.io make
```
### 2. Clone the GitHub Repo
You can use git to download the [source code](https://github.com/LyndLabs/DNS-Driveby). You can also download it as a [zip file]().

```
git clone https://github.com/LyndLabs/DNS-Driveby
```

### 3. Navigate into Code Folder
Change directories into the source code folder.

```
cd DNS-Driveby/src 
```
### 4. Create a DNS CanaryToken
Generate a DNS Token at [canarytokens.org](https://canarytokens.org).

### 5. Flash the code!
Replace `<CANARYTOKEN>` with your custom CanaryToken generated above!

```
sudo make flash canaryurl="<CANARYTOKEN>"
```

### 6. Monitoring your Token
`coming soon`

### 7. Adding a Screen
`coming soon`