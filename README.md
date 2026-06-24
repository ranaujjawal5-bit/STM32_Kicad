# STM32F103C8T6 Minimum Viable System Development Board

A custom-designed, industry-standard 2-layer development platform featuring an ARM Cortex-M4 (STM32) architecture, engineered from scratch using KiCad. This project focuses on robust Power Distribution Network (PDN) design, clock isolation, and signal integrity constraints based on professional hardware methodologies.

## 🛠️ Hardware Specifications & Architecture
* **Microcontroller:** STM32F103C8T6 (32-bit ARM Cortex-M3/M4 RISC Core)
* **Power Supply:** 5V to 3.3V Linear Regulation via AMS1117 LDO with a local 22µF tank capacitor bank.
* **Clock System:** High-Precision External (HSE) 16MHz crystal oscillator network with parallel symmetric trace layout.
* **Analog Isolation:** Dedicated VDDA decoupling utilizing a 120Ω @ 100MHz Ferrite Bead Pi-Filter.
* **Connectivity/Debug:** Native USB-C/Micro interface with a 1.5kΩ pull-up indicator on the D+ line and a 4-pin SWD debugging port.

## 📐 Schematic Walkthrough
[Insert a screenshot of your KiCad Schematic here once uploaded]

### Key Engineering Decisions:
1. **Decoupling Strategy:** Positioned 100nF ceramic capacitors immediately adjacent to every VDD pin to minimize trace loop inductance and bypass high-frequency digital switching noise.
2. **Boot Architecture:** Integrated a pull-down network on the `BOOT0` pin via a 10kΩ resistor to ensure stable system initialization into internal Flash memory.
3. **Open-Drain Bus Design:** Embedded 1.5kΩ pull-up resistors on the broken-out I2C lines to snap idle states directly to 3.3V logic.
