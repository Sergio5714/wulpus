<img src="docs/images/wulpus_main.png" alt="WULPUS main" width="100%"/>

# WULPUS v1.2.2
## Wearable Ultra Low-Power Ultrasound
> Independent fork by @Sergio5714 with enhanced reproduction instructions and minor improvements.

# Introduction

This repository contains a stable release of WULPUS, a truly wearable ultra-low-power open research ultrasound platform.

To date, more than 70 probes have been produced worldwide, and over 12 groups have used it in academic and industrial research.

## System diagram

WULPUS probe comprises two printed circuit boards (PCBs):
- Acquisition PCB: featuring an ultrasound MCU (MSP430FR5043) and BLE MCU (nRF52832)
- High-Voltage PCB: featuring a High-voltage multiplexer (HV MUX), a transmit/receive switch, and a MOSFET driver.

<img src="docs/images/wulpus_system_diagram.png" alt="WULPUS System Diagram" width="100%"/>
WULPUS System Diagram

## Specifications

| Feature | Specification |
| --- | --- |
| Channels | 8 (time-multiplexed) |
| ADC | 1 channel, up to 8 Msps, 12-bit resolution, approx. 1.4 MHz -3 dB bandwidth |
| Analog front-end | 30.8 dB Programmable-Gain Amplifier + 10 dB Operational Amplifier |
| Wireless link | Bluetooth Low Energy (BLE), 320 kbps throughput |
| Acquisition rate | Up to 50 Hz PRF, 400 samples per acquisition (raw data streaming mode) |
| Size & weight | 46 x 25 mm footprint, 9 g |
| Power | 25 mW (raw data streaming mode, 50 Hz PRF) |

# Structure of the repository

This repository has the following folders:

- `fw`, containing the firmware source code, namely:
    - source code for the nRF52832 MCU of the WULPUS probe, located at `fw/nrf52/ble_peripheral/US_probe_nRF52_firmware`
    - source code for the nRF52840 USB dongle, located at `fw/nrf52/peripheral/US_probe_dongle_firmware`
    - source code for the MSP430 ultrasound MCU, located at `fw/msp430`
- `sw`, containing the Python code for the WULPUS Graphical User Interface
 
- `hw`, containing the CAD source files for 
    - WULPUS Acquisition PCB (located at `hw/wulpus_acquisition_pcb`)
    - WULPUS High-Voltage PCB (located at `hw/wulpus_hv_pcb`)
    - WULPUS Programmer PCBs (located at `hw/wulpus_programmer_pcbs`)
    - WULPUS Silicone Rubber package (located at `hw/wulpus_silicone_package`)

- `docs`, containing the project documentation (e.g., images of the device, user manual, ...)

# Documentation 

The comprehensive [WULPUS User Manual](docs/wulpus_user_manual.pdf) can be found in the `docs/` folder. It covers everything about WULPUS, from assembly instructions to example measurements and troubleshooting, making the platform user-friendly for everyone, regardless of technical expertise.

# Reproduction

Please find the detailed instructions in chapter 2 of the [WULPUS User Manual](docs/wulpus_user_manual.pdf).

In a nutshell, to build your own instance of WULPUS, the following steps should be completed:
1. *PCBs manufacturing and assembly*<br>
   You can find the design files (Altium source files, schematics, bills of materials) under the `hw` folder.
2. *Flashing MSP430 firmware*<br>
   You can find the instructions on seting-up the toolchain, compiling the firmware and flashing the MSP430 MCU in the `fw/msp430` folder.
3. *Flashing nRF52 MCU and USB dongle firmware*<br>
   You can find the instructions on setting-up the toolchain, compiling the firmware, flashing the nRF52 MCU and USB dongle in the `fw/nrf52` folder.
4. *Python dependencies installation on the host PC*<br>
   Follow the instructions in the `sw` folder to install the dependencies.

## PCBWay projects for Acquisition and High-Voltage PCBs

For convenient one-click PCB production and assembly, you can use the PCBWay shared projects (optional; DIY via the `hw` folder is also supported):
- [WULPUS Acquisition Board](https://www.pcbway.com/project/shareproject/WULPUS_Acquisition_PCB_v1_2_2_f15bda6f.html)
- [WULPUS HV MUX Board](https://www.pcbway.com/project/shareproject/WULPUS_High_Voltage_PCB_v1_1_1_2b755171.html)

This option is convenient for outsourced PCB production and assembly, with an estimated **~1 month lead time** and a price of about **USD 180** per probe (Acquisition + HV PCB), based on mid-2025 pricing.

# Usage

Please refer to chapter 3 of the [WULPUS User Manual](docs/wulpus_user_manual.pdf) for detailed information.

Starting a measurement with WULPUS can be accomplished in three simple steps:
- Power up the probe, either from the micro-USB connector or from the battery connector
- Connect the USB dongle to the host PC
- Activate the Python environment, launch the Jupyter notebook located in `sw` folder, and follow the instructions in the notebook

# Citation
If you would like to cite the project, please use the following repository citation:

```
@misc{wulpus_repo_sergio5714_2026,
  title={WULPUS: Wearable Ultra Low-Power Ultrasound (Independent Fork)},
  author={Vostrikov, Sergei},
  year={2026},
  howpublished={GitHub repository},
  url={https://github.com/Sergio5714/wulpus}
}
```

If you prefer to cite the original scientific publication, please use:

```
@inproceedings{frey2022wulpus,
  title={WULPUS: a Wearable Ultra Low-Power Ultrasound probe for multi-day monitoring of carotid artery and muscle activity},
  author={Frey, Sebastian and Vostrikov, Sergei and Benini, Luca and Cossettini, Andrea},
  booktitle={2022 IEEE International Ultrasonics Symposium (IUS)},
  pages={1--4},
  year={2022},
  organization={IEEE}
}
```
# Works that use WULPUS

[1] Vostrikov, Sergei, et al. "Hand gesture recognition via wearable ultra-low power ultrasound and gradient-boosted tree classifiers." 2023 IEEE International Ultrasonics Symposium (IUS). IEEE, 2023.

[2] Vostrikov, Sergei, Luca Benini, and Andrea Cossettini. "Complete Cardiorespiratory Monitoring via Wearable Ultra Low Power Ultrasound." 2023 IEEE International Ultrasonics Symposium (IUS). IEEE, 2023.

[3] Frey, Sebastian, et al. "A wearable ultra-low-power semg-triggered ultrasound system for long-term muscle activity monitoring." 2023 IEEE International Ultrasonics Symposium (IUS). IEEE, 2023.

[4] Vostrikov S, Anderegg M, Benini L, Cossettini A. "Unsupervised Feature Extraction from Raw Data for Gesture Recognition with Wearable Ultra Low-Power Ultrasound." IEEE Transactions on Ultrasonics, Ferroelectrics, and Frequency Control. 2024 May 24.

[5] Spacone G, Vostrikov S, Kartsch V, Benatti S, Benini L, Cossettini A. "Tracking of Wrist and Hand Kinematics with Ultra Low Power Wearable A-mode Ultrasound." IEEE Transactions on Biomedical Circuits and Systems. 2024 Sep 23.

# Authors

This fork is maintained independently by @Sergio5714 ([Sergei Vostrikov](https://scholar.google.com/citations?user=a0KNUooAAAAJ&hl=en)).

The WULPUS system was originally developed at the [Integrated Systems Laboratory (IIS)](https://iis.ee.ethz.ch/) at ETH Zurich by:
- [Sergei Vostrikov](https://scholar.google.com/citations?user=a0KNUooAAAAJ&hl=en) (Firmware, Software, Open-Sourcing, Documentation)
- [Sebastian Frey](https://scholar.google.com/citations?user=7jhiqz4AAAAJ&hl=en) (Firmware, PCB design, Documentation)
- [Cédric Hirschi](https://www.linkedin.com/in/c%C3%A9dric-cyril-hirschi-09624021b/) (GUI, Documentation)
- [Luca Benini](https://scholar.google.com/citations?hl=en&user=8riq3sYAAAAJ) (Supervision, Conceptualization)
- [Andrea Cossettini](https://scholar.google.com/citations?user=d8O91jIAAAAJ&hl=en) (Supervision, Project administration)

Thanks to all the people who contributed to the WULPUS platform:
- [Josquin Tille](https://www.linkedin.com/in/josquin-tille-829a341a7/) (Silicone package design, Documentation)
- [William Bruderer](https://www.linkedin.com/in/william-bruderer-59ba9b26b/) (Documentation)


# License
The following files are released under Apache License 2.0 (`Apache-2.0`) (see `sw/LICENSE`):

- `sw/`

The following files are released under Solderpad v0.51 (`SHL-0.51`) (see `hw/LICENSE`):

- `hw/`

The following files are released under Creative Commons Attribution 4.0 International
License (`CC-BY-4.0`) (see `docs/images/LICENSE`):

- `docs/images/`

The `fw/msp430/` and `fw/nrf52/` directories contain third-party sources that come with their own
licenses. See the respective folders and source files for the licenses used.

## Limitation of Liability
In no event and under no legal theory, whether in tort (including negligence), contract, or otherwise, unless required by applicable law (such as deliberate and grossly negligent acts) or agreed to in writing, shall any Contributor be liable to You for damages, including any direct, indirect, special, incidental, or consequential damages of any character arising as a result of this License or out of the use or inability to use the Work (including but not limited to damages for loss of goodwill, work stoppage, computer failure or malfunction, or any and all other commercial damages or losses), even if such Contributor has been advised of the possibility of such damages.
