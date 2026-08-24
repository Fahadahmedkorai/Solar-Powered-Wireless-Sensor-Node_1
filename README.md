# Solar-Powered Wireless Sensor Node

Ultra-low-power, battery-free wireless sensing platform designed for passive flier and long-term environmental monitoring applications.

The system combines **solar energy harvesting
, hybrid-supercapacitor storage, environmental sensing, motion sensing, and low-power wireless communication** in a compact **4-layer flexible PCB**.

## Project Overview

The goal of this project is to develop an ultra-lightweight sensing platform capable of operating for extended periods without a conventional battery.

The current architecture uses harvested solar energy to charge an **8 F Eaton hybrid supercapacitor**, which powers an nRF-based wireless sensor node during low-light and nighttime conditions.

The platform is being developed for applications such as:

* Passive microfliers
* Forest monitoring
* Environmental sensing
* Long-term autonomous sensor networks
* Battery-free IoT systems

## Hardware

### Main PCB

**4-Layer Flexible PCB**

The latest PCB combines the energy-harvesting and wireless sensing electronics into a single lightweight flexible board.

Main components include:

* **Nordic nRF52810** — ultra-low-power MCU and 2.4 GHz radio
* **TI BQ25570** — solar energy harvesting and MPPT
* **8 F Eaton hybrid supercapacitor** — energy storage
* Temperature and humidity sensor
* 3-axis accelerometer
* **TI OPT3007** ambient-light sensor
* U.FL connector for external 2.4 GHz antenna
* SWD programming interface

The flexible PCB reduces connectors, wiring, and overall system mass compared with the earlier two-board prototype.

## Power Architecture

```text
Solar Panel
    ↓
BQ25570 Energy Harvester
    ↓
8 F Hybrid Supercapacitor
    ↓
Low-Power Regulation
    ↓
nRF52810 + Sensors
    ↓
Wireless Gateway
```

The system is designed to harvest energy during daylight and use stored supercapacitor energy during darkness or temporary shading.

## Wireless Communication

The current implementation uses **Nordic ESB** for low-energy wireless transmission.

Measured results showed:

| Parameter             |   Result |
| --------------------- | -------: |
| Average current       | ~12.8 µA |
| Peak current          | ~6.66 mA |
| Wake-up duration      | ~17.7 ms |
| TX duration           |  ~3.4 ms |
| Energy per event      | ~39.1 µJ |
| Transmission interval |   ~120 s |

Compared with the earlier BLE implementation, the ESB configuration reduced transmission-event energy significantly.

## Energy Storage Testing

An 8 F hybrid supercapacitor was tested with the solar input disconnected while the wireless node remained active.

Measured results:

* Initial voltage: **4.139 V**
* Final voltage: **3.883 V**
* Test duration: **~65 hours**
* Estimated average system current: **~8.8 µA**

The capacitor demonstrated multi-day operation without solar input.

## Forest Energy-Harvesting Tests

The system has also been tested under forest-canopy illumination with the wireless load connected.

Preliminary measurements showed positive capacitor charging during daylight, indicating that harvested solar energy exceeded node consumption under the tested conditions.

This is being extended toward long-term **energy-neutral operation** analysis.

## Solar Panels Under Evaluation

Several lightweight PowerFilm solar modules are being evaluated:

| Panel        | Approx. Weight | Role                    |
| ------------ | -------------: | ----------------------- |
| ONP1.2-37×54 |        0.496 g | Minimum-mass candidate  |
| SP3-37       |         0.69 g | Compact reference       |
| MP3-25       |         0.73 g | Main balanced candidate |
| MP3-37       |        ~1.04 g | Higher-power reference  |

The final panel will be selected based on **energy harvested per day, mass, illumination conditions, and long-term energy neutrality**.

## Current Status

* Battery-free operation demonstrated
* Solar energy harvesting operational
* 8 F hybrid supercapacitor integrated
* 4-layer flex PCB developed
* nRF52810 wireless node operational
* Temperature and humidity sensing implemented
* Accelerometer integrated
* Ambient-light sensing integrated
* Nordic ESB communication operational
* Gateway communication operational
* Overnight operation demonstrated
* Forest-canopy harvesting demonstrated
* Long-term outdoor testing ongoing

## Future Work

* Long-term energy-neutral operation testing
* MP3-25 / ONP1.2 / MP3-37 comparison
* Orientation-aware adaptive transmission
* Dual-sided solar harvesting
* Multi-gateway deployment
* Packet-delivery and range characterization
* Outdoor moisture and rain protection
* Further PCB weight reduction
* Localization and BLE 6.0 Channel Sounding experiments using compatible future hardware

## Research Focus

The main research question is:

> **How lightweight can a battery-free passive-flier sensing platform become while maintaining long-term autonomous operation under realistic environmental conditions?**

## Author

**Fahad Ahmed Korai**
Doctoral Researcher
Tampere University, Finland
