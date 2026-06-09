# ICS 4111: Embedded Systems & IoT
## Semester Project — Deliverable 1

**Flora Farms Greenhouse Monitoring System | Assigned Flower: Carnations**

### Group Members
| Name | Student ID |
|---|---|
| Donell Bikketi | 166604 |
| Gloria Kendi | 166074 |
| Emmanuel Douglas | 168053 |
| Crystal Kanana | 169820 |
| Andrew Kigondu | 166228 |

---

## 1. Environmental Requirements for Carnations

| Parameter | Optimal Range | Notes |
|---|---|---|
| Temperature | 10–24°C | Daytime: 18–24°C; Night: 10–15.5°C depending on season. Above 30°C stresses the plant. |
| Relative Humidity | 60–85% | 80–85% during vegetative growth; 60–65% at full growth stage. |
| Soil Type | Sandy loam / Loamy | Rich in organic matter; good drainage with adequate moisture retention. |
| Soil Moisture Content | 21–40% | Soil should dry slightly between waterings to prevent root rot. |
| Soil pH | 6.7–7.0 | Slightly alkaline, well-drained, fertile soil. |
| Sunlight Exposure | 4–6 hours/day | Morning sunlight preferred; keeps flowers fresh and prevents color fading. |

---

## 2. Hardware Components

### Microcontroller & Communication
| Component | Purpose |
|---|---|
| ESP32S DevKIT WiFi + BLE Module (30-pin) | Main microcontroller; handles processing and WiFi/BLE communication |

### Sensors
| Component | Purpose |
|---|---|
| DHT22 AM2302 | Temperature & relative humidity sensing |
| MQ-5 Gas Sensor | LPG / methane / butane / propane detection |
| Capacitive Soil Moisture Sensor (v1.2) | Soil moisture measurement |
| Soil pH Sensor Module | Soil pH measurement |
| BH1750 / LDR Light Sensor | Sunlight exposure measurement |

### Output & Control
| Component | Purpose |
|---|---|
| 1.3" White IIC 128×64 OLED Display | Local display of sensor readings |
| 5V 1-Channel Low-Level Trigger Relay Module | Actuator control (fans, pumps, alerts) |

### Power Supply
| Component | Purpose |
|---|---|
| 5V Micro USB Power Supply / Power Bank | Powers ESP32 and peripherals |
| AMS1117-3.3 LDO Voltage Regulator | Steps down voltage for sensitive sensors |

### Passive Components & Prototyping Tools
| Component | Purpose |
|---|---|
| 10kΩ Resistors (×5) | Pull-up/pull-down for sensor lines |
| 1kΩ Resistors (×3) | Current limiting |
| 10kΩ Potentiometer | Analog calibration / voltage divider |
| 100nF Ceramic Capacitors (×4) | Noise filtering near sensors |
| 10µF Electrolytic Capacitors (×2) | Power supply smoothing |
| Full-size Breadboards (×2) | Prototyping without soldering |
| Jumper Wires (M-M, M-F, F-F) | Component connections |
| USB to Micro-USB Cable | Flashing ESP32 from PC |
| Multimeter | Voltage, continuity & debugging |
| Laptop with Arduino IDE / VS Code + PlatformIO | Programming the ESP32 |

---

## 3. Component Datasheets

| Component | Datasheet / Reference |
|---|---|
| 1.3" White IIC 128×64 OLED (SH1106) | [displaymodule.com](https://www.displaymodule.com/products/1-3-inch-oled-graphic-display-128x64-with-i2c) |
| ESP32S DevKIT WiFi + BLE (30-pin) | [Espressif Datasheet (PDF)](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf) |
| DHT22 AM2302 | [Adafruit-hosted Datasheet (PDF)](https://cdn-shop.adafruit.com/datasheets/Digital+humidity+and+temperature+sensor+AM2302.pdf) |
| MQ-5 Gas Sensor | [Winsen Datasheet (PDF)](https://www.winsensensor.com/d/files/MQ-5.pdf) |
| 5V 1-Channel Relay Module | [Handsontec Datasheet (PDF)](https://handsontec.com/dataspecs/relay/1Chrelay.pdf) |

---

## 4. Schematic Diagrams

### Circuit 1 — Single ESP32S with MQ-5, DHT22 and LCD
All sensors feed into one ESP32S, which outputs readings to the OLED display over I2C.

![Circuit 1](./images/circuit1.png)

---

### Circuit 2 — Two ESP32S Boards Interfaced Directly
One ESP32S handles the MQ-5 (gas), the other handles the DHT22 (temp/humidity). The two boards communicate directly via GPIO/UART.

![Circuit 2](./images/circuit2.png)

---

### Circuit 3 — Two ESP32S Boards Connected via Relay
The first ESP32S (DHT22) triggers a relay that gates communication with the second ESP32S (MQ-5), demonstrating relay-based inter-node actuation.

![Circuit 3](./images/circuit3.png)

---

## Evidence of Groupwork

The team held a collaborative Google Meet session to discuss, assign, and review tasks for this deliverable.

![Group Meeting](./images/groupwork.png)

*Attendees: Crystal Kanana, Donell Bikketi, Gloria Munene, Emmanuel Douglas Ouma*

---
*ICS 4111 — Strathmore University | Apr–Jul 2026*
