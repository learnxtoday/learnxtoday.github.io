---
layout: post
title: "Install Deepin on Ubuntu"
author: "thenerdsuperuser"
podcast-id: "b608a47b-75fb-44fa-b72d-af6f42e4a4b7"
tags: deepin-de ubuntu
---


Follow the steps below to install Deepin Desktop Environment on Ubuntu 20.04 / Linux Mint 20.x or Ubuntu 20.10.

### Add the UbuntuDDE Stable Release PPA

```bash
sudo add-apt-repository ppa:ubuntudde-dev/stable

sudo apt-get update
```

### Install the Deepin Desktop Environment on Ubuntu 20.04 or 20.10 / Linux Mint 20.x

```bash
sudo apt install ubuntudde-dde ubuntudde-dde-extras
```

While installing `ubuntudde-de`, it will ask you to choose LighDM as the display manager, which is not necesary if you want the default Ubuntu login screen, GDM3.


### Errors while installing

One specific error which annoyed me was procesing `deepin-anything-dkms` package. Now, everything was working fine. Deepin was installed, and it worked flawlessly. I was able to update and install new packages without any issues, but 4 packages were not configured completely. 

So I had to go down the rabbit hole of endless google searches, until I came across a blog by [Linux Uprising](https://www.linuxuprising.com/2020/12/how-to-install-deepin-desktop.html#:~:text=Fix,20.x)

I had to download the `deepin-anything-dkms.deb` package and install it manually.   
To do this, download the deepin-anything-dkms from [here](http://ppa.launchpad.net/ubuntudde-dev/stable/ubuntu/pool/main/d/deepin-anything/deepin-anything-dkms_5.0.1-7_all.deb) (it's version 5.0.1-7_all.deb at the time I'm writing this), and install it from a terminal, like this:

```bash
sudo apt install ./deepin-anything-dkms_5.0.1-7_all.deb
```

In case the DEB download link no longer works in the future (if the package is updated), you can find the latest version [here](http://ppa.launchpad.net/ubuntudde-dev/stable/ubuntu/pool/main/d/deepin-anything/?C=N;O=A) (just make sure to get the newest version).


After all these packages are installed, `reboot` your system and you're done.
