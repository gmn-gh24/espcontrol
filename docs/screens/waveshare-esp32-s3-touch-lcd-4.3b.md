---
title: 4.3-inch Waveshare ESP32-S3-Touch-LCD-4.3B
description:
  EspControl on the Waveshare ESP32-S3-Touch-LCD-4.3B — a 4.3-inch 800×480 landscape touchscreen with 15 cards, powered by ESP32-S3.
---

# 4.3-inch Waveshare ESP32-S3-Touch-LCD-4.3B

The **Waveshare ESP32-S3-Touch-LCD-4.3B** is a 4.3-inch landscape industrial touch panel with native ESP32-S3 WiFi, RGB display, capacitive touch, RS485, CAN, and isolated digital I/O.

## Hardware summary

| Spec | Value |
|------|-------|
| **SoC** | ESP32-S3-WROOM-1-N16R8 |
| **Flash / PSRAM** | 16 MB / 8 MB (octal) |
| **Screen size** | 4.3 inches |
| **Resolution** | 800 × 480 (landscape) |
| **Display** | RGB parallel (ST7262), IPS |
| **Touch** | GT911 capacitive (I2C) |
| **Backlight / reset** | CH422G I/O expander (I2C 0x24) |
| **Home screen** | 15 cards (5 × 3 grid) |

## Firmware notes

- Uses ESPHome `mipi_rgb` with model `ESP32-S3-TOUCH-LCD-4.3` (same pinout as the Waveshare 4.3B board).
- Backlight is switched through CH422G EXIO2 (on/off only — no hardware PWM dimming).
- After USB flash or OTA, the panel performs a short deep-sleep reset so the RGB display stack initializes reliably (same approach as the Guition 4848S040).

## Install

Use the web installer and select **Waveshare 4.3B**, or point ESPHome at:

`devices/waveshare-esp32-s3-touch-lcd-4.3b/esphome.yaml`

## References

- [Waveshare product page](https://www.waveshare.com/esp32-s3-touch-lcd-4.3b.htm)
- [Waveshare wiki](https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-4.3B)
