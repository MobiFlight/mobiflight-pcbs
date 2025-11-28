# 🧠 PicoNano (RP2350A)

[![Mobiflight Compatible](https://img.shields.io/badge/Mobiflight-Compatible-brightgreen?style=flat-square&logo=mobiflight&logoColor=white)](https://www.mobiflight.com/)
[![RP2350A MCU](https://img.shields.io/badge/RP2350A-Dual%20Core%20Cortex--M33-blue?style=flat-square)](https://www.raspberrypi.com/documentation/microcontrollers/)

The **PicoNano** is a compact RP2350A-based microcontroller board designed as a **modern drop-in alternative to the Arduino Nano**.  
It keeps the same small footprint while offering significantly more processing power, memory, and advanced features for modern projects.

This board is optimized especially for **Mobiflight custom devices**, cockpit electronics, displays, and I/O-intensive modules.

---

## 🚀 Key Advantages over Arduino Nano

| Feature | Arduino Nano | **PicoNano (RP2350A)** |
|---------|--------------|------------------------|
| MCU | ATmega328P (8-bit AVR) | RP2350A Dual-Core ARM Cortex-M33 |
| Clock Speed | 16 MHz | **up to 150 MHz** |
| Flash | 32 KB | **2 MB on-chip** |
| RAM | 2 KB | **520 KB** |
| USB | Mini-USB | **USB-C native** |
| Bootloader | Reset double-tap | **Dedicated BOOT button** |
| Logic Voltage | 5V | **3.3V with 5V-tolerant I/O** |
| Analog Inputs | 8 | 4 (A0–A3) |
| PWM Outputs | 6 | **16+** |
| Interfaces | 1×I²C, 1×SPI, 1×UART | Multiple independent channels |
| Mobiflight | Supported | **Fully supported / custom device ready** |

---

## ⭐ Highlights

- **Full dual-core 150 MHz processing performance**
- **Large memory**, ideal for OLED and multitasking display projects
- **5V-tolerant GPIO**, perfect migration from Nano
- **USB-C & Boot button** for easy flashing
- **All pins available on dual header layout**
- Runs **Mobiflight, CircuitPython, MicroPython and C/C++**

---

## ⚡ Why PicoNano works so well with Mobiflight custom devices

- Community cockpit modules often require:
  - More RAM and Flash
  - Higher-speed SPI / I²C
  - Multiple displays (e.g., **SSD1306 OLED**, MAX7219 LED matrices)
- Eliminates typical limitations of Arduino Nano (out-of-memory, flickering, very slow text rendering)
- Extremely fast and stable with large display chains and LED drivers

---

## ⚠ Compatibility Limitations

| Limitation | Explanation |
|-----------|-------------|
| Only 4 analog inputs | A0–A3 available; more require expansion IC |
| 3.3V logic output | 5V-tolerant input but cannot source high-current loads |
| External 5V recommended for LED drivers | e.g. MAX7219, LED modules |
| Level shifting required for 5V digital peripherals | use BSS138-based modules |

---

## 🔌 Example Wiring — MAX7219 with PicoNano (via Level Shifter)

PicoNano (RP2350A) → MAX7219 (via BSS138 Level Shifter)
-------------------------------------------------------

Pin 22  → DIN
Pin 23  → CLK
Pin 24  → CS
Pin 25  → LOAD

Power:
MAX7219 VCC → 5V External Supply or USB 5V (Vin)
GND         → GND (shared with PicoNano)

## Important Notes

Use a BSS138-based bidirectional level shifter (MAX7219 requires 5V logic).

The MAX7219 must be powered from 5V, not 3.3V.

Pins 22–25 are well-suited for level-shifted SPI routing.

Level shifters cannot source high current → not suitable for LED strips, relays, or high-load devices.

## 📦 Summary

The PicoNano brings the familiar Nano format into the modern era:

Massive processing headroom and memory

Perfect match for Mobiflight custom device development

Ideal for display-based avionics panels

Fully breadboard-friendly

## 🛠 Coming soon

Pinout graphic (PNG + printable PDF)

Wiring diagrams as images

Board rendering + enclosure STL