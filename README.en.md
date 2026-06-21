# VG93-MB8877-lgt8f328p-emulator

## Hardware layout for Evgeny Ugryumov's WD1793/MB8877/KR1818VG93 floppy disk controller emulator based on the LGT8F328P MCU.

> [English](README.en.md) | [Русский](README.ru.md)

This project features a hardware emulator for the Soviet KR1818VG93 (КР1818ВГ93) floppy disk controller chip and its international equivalents, the **Western Digital WD1793** and **Fujitsu MB8877**. Powered by the fast and affordable **LGT8F328P** microcontroller, this adapter board acts as a direct drop-in replacement. It is designed to replace scarce, expensive, or faulty vintage FDC chips in retro-computers like the ZX Spectrum and other compatible 8-bit systems.

*   **Firmware Development:** Evgeny Ugryumov (ZX-FLOPPY group).
*   **PCB Layout & Hardware Design:** Alex-2-Graf.

The adapter board is routed specifically to plug directly into a standard 40-pin IC socket on the host computer board, requiring no permanent modifications to the vintage hardware.

***

## ⚡ Key Features of LGT8F328P

*   **32 MHz Clock Speed:** Provides high-precision bus timing synchronization to accurately match vintage hardware cycles.
*   **High Performance Core:** Executes most machine instructions in a single clock cycle.
*   **Native 5V Logic:** Provides full signal level compatibility with legacy 8-bit computers without requiring logic level shifters or resistors.
*   **Cost-Effective:** The LGT8F328P microcontroller is significantly more affordable and accessible than surviving original WD1793/VG93 silicon chips.

## 🛠️ Supported Functionality

*   Emulation of core FDC commands for sector reading and writing.
*   Accurate tracking of stepper motor control signals (`STEP`, `DIR`).
*   Precise hardware emulation of standard drive feedback signals: `READY`, `INDEX`, and `TRACK 00`.

***

## 🔌 Hardware Revisions

The emulator has evolved through three distinct board layouts:

### Revision 1 (Not recommended for new builds)
The initial prototype version. Included for historical log purposes.
*   [Schematics](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Placement](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Gerber](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator)

### Revision 2 (Diode-based version)
An improved layout utilizing discrete steering diodes to condition signals.
*   [Schematics](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Placement](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Gerber](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator)

### Revision 3 (74AHC1G08 logic version - Recommended)
The latest and most stable layout utilizing a tiny 74AHC1G08 AND-gate chip. Since this logic IC comes in two common SMD packages, two distinct PCB options are available:
1.  **Ultra-compact layout** using the **SC-70** IC package package:
    *   [Schematics](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Placement](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Gerber](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator)
2.  **Standard layout** using the **SOT-23-5** IC package package:
    *   [Schematics](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Placement](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) | [Gerber](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator)

***

## 💾 Flashing Instructions

To flash the compiled firmware onto the onboard LGT8F328P microcontroller, a specialized ISP programmer is required. 

You can assemble your own programmer using one of these DIY options:
1.  An **Arduino-based** programmer using [LarduinoISP](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator).
2.  An **RP2040-based** programmer using [LarduinoISP](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator).

Once your hardware programmer is verified, flash the precompiled binary `.hex` files using the **AVRDUDESS** GUI software tool.

*   **Firmware Binaries:** Available inside the [/Firmware](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) directory.
*   **Latest Releases:** Updated software drops can be monitored directly in the **ZX-FLOPPY** community group.
*   **Source Material:** Complete design files can be inspected in the [/Sources](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator) folder.

### ⚠️ Interface Modification (Nemo-BDI Correction)
For Beta Disk Interfaces utilizing the **Nemo-BDI** standard architecture, an external hardware patch is required to correct the chip select (`CS`) signal timing. This modification requires a standard **555LA3 / 74LS00** discrete NAND logic gate chip.
*   [Modification Schematic](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator)

***

## 👥 Credits & Acknowledgments

*   **Evgeny Ugryumov** — Special thanks for his incredible work developing the firmware core inside the **ZX-FLOPPY** project.
*   **Alexander (UR4QBP)** — For running extensive hardware testing, experiments, and optimizations. You can find his specific repository fork [here](https://github.com/Alex-2-Graf/VG93-MB8877-lgt8f328p-emulator).
*   **HRDY (Dmitry)** — For developing the excellent RP2040-based hardware programmer design.

***

## 📜 License

This project is distributed under the open-source MIT License. See the `LICENSE` file for more details.
