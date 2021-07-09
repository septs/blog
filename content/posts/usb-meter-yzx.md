+++
date = 2021-07-08T18:55:10+08:00
title = "YZXStudio USB Meter Protocol design"
slug = "yzx-usb-meter"
+++

## YZXStudio USB Meter

### Serial Port

| Via       | Band rate |
| --------- | --------- |
| USB       | 115200    |
| Bluetooth | 9600      |

### Packet layout

| Field |      Type | Note       |
| ----: | --------: | ---------- |
|   STX |    3 byte | `AB 00 06` |
|  Volt |  int32 LE | / 10, mV   |
|   Amp |  int32 LE | / 10, mA   |
|   A·h | uint32 LE | / 10, mA·h |
|   W·h | uint32 LE | / 10, mW·h |
| Delta | uint32 LE | ms         |
|    D- | uint16 LE | mV         |
|    D+ | uint16 LE | mV         |

## Source Code

<https://github.com/CursedHardware/yzx-usb-meter>
