&nbsp;

<p align="center"><a href ="https://elementary.io/"><img src="https://raw.githubusercontent.com/flamanta/linux/master/images/community-black.png" alt="elementary Community logo"/ height="200"></a></p>

<h3 align="center">@flamanta + elementary OS</h3>

<p align="center">My Linux setup on Elementary OS 5 Juno.</p>

<hr>

<p align="center">
    <a href="https://elementary.io/">elementary OS</a> |
    <a href="https://elementary.io/support">Support</a> |
    <a href="https://developer.elementary.io/">Developer</a> |
    <a href="https://elementary.io/store/">Store</a>
    <br><br>
    <a href="https://github.com/prettier/prettier">
        <img src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg" alt="code style: prettier" />
    </a>
</p>

&nbsp;

<br>
<p align='center'>
    <img src="https://raw.githubusercontent.com/flamanta/linux/master/images/screenshot.png" height="500" />
</p>

<br>

&nbsp;

<hr>

## Why? [![start with why](https://img.shields.io/badge/start%20with-why%3F-brightgreen.svg?style=flat)](http://www.ted.com/talks/simon_sinek_how_great_leaders_inspire_action) <!-- omit in toc -->

I have two setups with Elementary OS, so I'm constantly trying to keep the applications and settings on these two setups in sync.

The open source nature of the Linux ecosystem means that users can customise aspects of the operating system to their whims and likes. The most common and widely supported way is through the command line.

As such, there will usually be a lot of Googling when I am setting up my Linux setups. This document will point to all the websites and articles that I use in my setup, making it easier for me to setup my OS.

I will likely update this document when the next version of Elementary OS is released, because that would likely mean another clean install of the operating system on both of my setups.

## Contents <!-- omit in toc -->

- [Installation](#installation)
- [System Settings](#system-settings)
  - [Applications](#applications)
  - [Desktop](#desktop)
  - [Security & Privacy](#security--privacy)
  - [Displays](#displays)
  - [Mouse & Touchpad](#mouse--touchpad)
  - [Network](#network)
  - [Sharing: **Off**](#sharing-off)
  - [Date & Time](#date--time)
  - [User Accounts](#user-accounts)
- [Terminal Commands](#terminal-commands)
  - [Update list of packages](#update-list-of-packages)
  - [Installing new versions of packages](#installing-new-versions-of-packages)
  - [Removing unused software dependencies](#removing-unused-software-dependencies)
  - [Installing closed-source multimedia codecs](#installing-closed-source-multimedia-codecs)
- [Alternative package management systems](#alternative-package-management-systems)
  - [AppImage (.AppImage)](#appimage-appimage)
  - [Debian packages(.deb)](#debian-packagesdeb)
  - [Flatpak](#flatpak)
  - [Snap Store](#snap-store)

## Installation

1. Check if your operating system is 32-bit or 64-bit.

   - _Elementary OS can only run on 64-bit systems_

   On **Windows**, right-click **This PC** in Windows Explorer. The System Properties will display if your computer is 32-bit or 64-bit.

   On **Mac**, run `getconf LONG_BIT` in the command line.

2. Download the [Elementary OS ISO](https://elementary.io/) and follow the [installation instructions](https://elementary.io/docs/installation#installation).

   - I generally prefer the use of [Balena Etcher](https://www.balena.io/etcher/) instead of UNetbootin.

3. If it is your first time using Linux or Elementary OS, I would highly recommend reading the [basics](https://elementary.io/docs/learning-the-basics) to get yourself started.

## System Settings

The System Settings can be accessed via the Applications menu.

Here I will list the system settings I use which I deem to be important.

### Applications

For how to install applications, see some later.

- Default
  - Web Browser: **Firefox**
  - Music Player: **Lollypop**
- Startup
  - **Discord**

### Desktop

- Wallpaper
  - Found on [Unsplash](https://unsplash.com/)
- Dock
  - Icon size: **Large**
- Hot Corners
  - Top right: **Maximize current window**
  - Bottom right: **Multitasking view**

### Security & Privacy

- Locking
  - Lock on sleep: **On**
  - Lock after screen turns off: **On**
- Firewall: **On**
- Housekeeping
  - Automatically delete old temporary files: **On**
  - Automatically delete old trashed files: **On**
  - Number of days to keep trashed and temporary files: **30**
- Location Services: **Off**

### Displays

- Night Light: **On**
  - Schedule: **Sunset to Sunrise**

### Mouse & Touchpad

- Mouse
  - Natural scrolling: **Off**
- Touchpad
  - Tap to click: **On**
  - Physical clicking: **On, Multitouch**
  - Scrolling: **Two-finger**
  - Natural scrolling: **On**
  - Ignore with typing: **On**
  - Ignore when mouse is connected: **Off**

### Network

- Wireless

  - IPv4 Settings
    - Method: **Automatic (DHCP) addresses only**
    - DNS servers: **1.1.1.1, 1.0.0.1** ([Cloudflare DNS](https://www.cloudflare.com/learning/dns/what-is-1.1.1.1/))
    - Require IPv4 addressing for this connection to complete: **On**
  - IPv6 Settings
    - Method: **Automatic, addresses only**
    - DNS servers: **2606:4700:4700::1111, 2606:4700:4700::1001** ([Cloudflare DNS](https://www.cloudflare.com/learning/dns/what-is-1.1.1.1/))
    - IPv6 privacy extensions: **Enabled, prefer temporary address**
    - IPv6 address generation mode: **Stable privacy**
    - Require IPv6 addressing for this connection to complete: **Off**

- [Setup instructions for SUTD_Wifi](https://gist.github.com/flamanta/dbf769c50e597205f386fd56daa24c4c) (for SUTD students)

### Sharing: **Off**

### Date & Time

- Network Time: **On**

### User Accounts

- Log in automatically: **Off**

## Terminal Commands

### Update list of packages

```bash
$   sudo apt-get update
```

### Installing new versions of packages

```bash
$   sudo apt-get upgrade
```

### Removing unused software dependencies

```bash
$   sudo apt-get autoremove
```

### Installing closed-source multimedia codecs

Closed-source software are not distributed with Ubuntu and Ubuntu derivatives, so we will have to install them via the terminal.

1. [ubuntu-restricted-extras](https://en.wikipedia.org/wiki/Ubuntu-restricted-extras)

   - Support for MP3 and unencrypted MP3 playback
   - Microsoft TrueType fonts
   - Adobe Flash plugin
   - Common audio and video codecs

```bash
$   sudo apt install ubuntu-restricted-extras
```

2. [libavcodec](https://en.wikipedia.org/wiki/Libavcodec)

   - Codecs for encoding and decoding audio and video

```bash
$   sudo apt install libavcodec-extra
```

3. [libdvdcss](https://www.videolan.org/developers/libdvdcss.html)

   - Allows access to DVDs as a block device

```bash
$   sudo apt install libdvd-pkg
```

## Alternative package management systems

The default package management system for Elementary OS is the Advanced Package Tool (APT). This was inherited by Elementary OS from Ubuntu which it is based on, while Ubuntu inherited it from Debian.

Other than running terminal commands starting with `sudo apt` in the Terminal, there are many other ways to install applications on Elementary OS.

### AppImage (.AppImage)

AppImage is a portable, distribution-agnostic format of software distribution for Linux. One does not need to install or give the software root permissions. It is a bit similar to the concept of a portable application.

To run an AppImage, one has to first download the `.AppImage` file. Next, navigate to its file location in the Terminal and make the `.AppImage` file executable.

```bash
$   chmod a+x Subsurface*.AppImage
```

One can simply run it by executing

```bash
$   ./Subsurface.*AppImage
```

### Debian packages(.deb)

Debian packages are archive files ending with the extension `.deb`. Due to Elementary OS being a derivative of Ubuntu, which is in turn a derivative of Debian, Debian packages can be installed on Elementary OS.

Debian packages can be installed by first installing the application [Eddy](https://appcenter.elementary.io/com.github.donadigo.eddy) from the AppCenter.

One can open downloaded `.deb` files in Eddy to install it, or download the `.deb` package first and open it later for installation.

### Flatpak

Flatpak offers a sandbox environment in which the application software runs, isolated from the rest of the Linux operating system.

To download and use Flatpak apps, one has to install the Flatpak PPA and add the Flathub repository.

```bash
$   sudo apt install software-properties-common --no-install-recommends
$   sudo add-apt-repository ppa:alexlarsson/flatpak
$   sudo apt update
$   sudo apt install flatpak
$   flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Thereafter, restart the system. The Flatpak applications can be downloaded by running the command line instructions found on the respective app pages on [Flathub](https://flathub.org/apps).

### Snap Store

The Snap Store is another distribution-agnostic format for software distribution developed by Canonical, the creators of Ubuntu. Applications on the Snap Store is collectively termed as snaps. The main way of accessing and installing snaps is via the Snap Store, which provides a graphical user interface for the user to install snaps similar to that of the Ubuntu Software Center.

To install the Snap Store, `snapd` has to be first installed and enabled.

```bash
$   sudo apt update
$   sudo apt install snapd
```

Restart the system to ensure that snap's paths are updated correctly. Thereafter, install the Snap Store on the Terminal using the command

```bash
sudo snap install snap-store
```

> to be continued..

<!-- ## References

- [6 Most Important things to do after Installing Elementary OS Juno](https://webcheerz.com/things-to-do-after-installing-elementary-os-5-juno/)
- [11 Things To Do After Installing elementary OS 5 Juno](https://itsfoss.com/things-to-do-after-installing-elementary-os-5-juno/)
- [16 Best Things To Do After Installing Elementary OS 5 Juno](https://www.ubuntupit.com/best-things-to-do-after-installing-elementary-os/)
- [33 Things to do After Fresh Installation of Elementary 5 Juno](https://linoxide.com/distros/things-after-fresh-installation-elementary-5-juno/) -->

## Author <!-- omit in toc -->

👤 **Wei Min Cher**

- GitHub: [@flamanta](https://github.com/flamanta)

## Show Your Support <!-- omit in toc -->

Please ⭐️ this repository if this project helped you!
