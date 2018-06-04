---
title: Getting Started with i.MX7 96Boards - Meerkat
permalink: /documentation/consumer/imx7-96/getting-started/
---
# Getting Started

Learn about your i.MX7 96 - Meerkat<sup>®</sup> board as well as how to prepare and set up for basic use

## Setup - What you will need

**Need**
- [i.MX7 96](https://www.96boards.org/product/imx7-96/)
   - Board based on the i.MX7 SoC
- Power adapter
   - 96Boards specifications requires a 8V-18V with 2000mA Power adapter
- USB Keyboard and Mouse
   - With two USB-A connectors, all 96Boards can be equiped with a full sized keyboard and mouse
- Monitor and HDMI Cable
   - All 96Boards are equiped with a full sized HDMI connector, HDMI capable monitor is recommended

**Optional**
- MicroSD card with adapter
  - For quick and easy switching between operating systems and extra storage
- Mezzanine Products
  - These devices allow you to expand your experience with any 96Boards by adding peripherals and enhancing onboard components
- USB to TTL cable
  - This is needed for serial console interface and fastboot/adb commands
- USB to ethernet adapter and ethernet cable
  - For connecting to a network without using WiFi

***

# Out of the Box

The following subsections should describe how to get started with the i.MX7 96 using the release build shipped with the boards.

<img src="../additional-docs/images/images-board/iMX7-96-front.jpg" data-canonical-src="../additional-docs/images/images-board/iMX7-96-front.jpg" width="250" height="160" />
<img src="../additional-docs/images/images-board/iMX7-96-back.jpg" data-canonical-src="../additional-docs/images/images-board/iMX7-96-back.jpg" width="250" height="160" />

## Features

The i.MX7 96Boards consumer edition board from Arrow Electronics is a
Linaro Consumer Edition specification board. This low-power i.MX7 was
designed in collaboration with Arrow, NXP, Linear Technology and LSR.
This is one of many boards in the Linaro 96Boards community. The goal of
the 96Boards initiative is to provide an option for standardization of
system-on-a-chip (SoC) boards for software developers, the maker
community and embedded product manufacturers.


|   Component          |   Description                                                                                         |
|:---------------------|:------------------------------------------------------------------------------------------------------|
|  SoC                 | i.MX7                                                                                                 |
|  CPU                 | Dual ARM® Cortex®-A7 at 1.0 GHz / Cortex-M4 at 266 MHz                                                |
|  RAM                 | 512 MB DRAM                                                                                           |
|  Wireless            | 802.11 b/g/n + BT / 2.4 GHz 802.11 b/g/n / BT 2.1+EDR (Enhanced Data Rate), BLE 4.1 / LSR Sterling-LWB|
|  USB                 | 2 x USB 2.0 Host 1 x USB 2.0 OTG                                                                      |
|  Display             | MIPI-DSI (Display Serial Interface)                                                                   |
|  Camera              | (Mobile Industry Processor Interface) MIPI-CSI (Camera Serial Interface)                              |
|  Expansion Interface | 40 pin low speed expansion connector: +1.8V, +5V, SYS_DCIN, GND, UART, I2C, SPI, PCM, PWM,GPIO x12 60 pin high speed expansion connector: 4L-MIPI DSI, USB, I2C x2, 2L+4L-MIPI CSI                                                         |
|  LED                 | 6 x LED: 4xUser controlled, 2xRadio(BT and WLAN activity)                                             |
|  Button              | Power/Reset                                                                                           |
|  Power Source        | 8V~18V@3A, Plug specification is inner diameter 1.7mm and outer diameter 4.8mm / 250 μW standby power |
|  Size                | 85mm x 54mm                                                                                           |




***

## Starting the board for the first time

**The SD card delivered with your Meerkat<sup>®</sup> has a graphical desktop based on xfce.**
- Connect a 1080P monitor to the HDMI connector. It is important to do this first because the monitor may not detect the board if it is connected after starting. Ensure that the source for the display is switched to the HDMI port you are using.
- Connect the USB keyboard and mouse.
- Ensure that the dipswitch is set to the factory default (1-1, i.e. all the switches are on)
- The dipswitch can be found on the reverse side of the board.
- Connect the power supply to an outlet and the board, the board will boot to a GUI desktop.

***


## What's Next?

If you are already familiar with the i.MX7 96 board and would like to change out the stock operating system, please proceed to one of the following pages:

- [Downloads page](../downloads/): This page lists all Linaro and 3rd party operating systems available for i.MX7 96
- [Installation page](../installation/): If you already have the images you need, this page has information on how to install the different operating systems onto your i.MX7 96 board
- [Support](../support/)
- From bug reports and current issues, to forum access and other useful resources, we want to help you find answers

Back to the [i.MX7 96 documentation home page](../)

***
