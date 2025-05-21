

You're absolutely right. The Table of Contents links weren't formatted correctly for GitHub. Here's the fixed README.md with properly working anchor links:

# ESPsomo

Universal firmware for small to medium mesh networks based on ESP microcontrollers leveraging ESP-NOW, WiFi, and BLE protocols.

![ESP32](https://img.shields.io/badge/ESP32-Supported-blue)
![ESP8266](https://img.shields.io/badge/ESP8266-Supported-blue)
![Arduino](https://img.shields.io/badge/Arduino-2.0.10-green)
![IoT](https://img.shields.io/badge/IoT-Automation-orange)
![Mesh](https://img.shields.io/badge/Mesh-Network-purple)

## 📋 Table of Contents

* [About](#-about)
* [Features](#-features)
* [Hardware Requirements](#-hardware-requirements)
* [Software Requirements](#-software-requirements)
* [Installation](#️-installation)
* [Usage](#-usage)
* [Network Architecture](#️-network-architecture)
* [Supported Sensors](#-supported-sensors)
* [Contributing](#-contributing)
* [License](#-license)

## 🌟 About

ESPsomo is a universal firmware solution designed for creating reliable mesh networks using ESP microcontrollers. Perfect for home automation, environmental monitoring, and industrial IoT applications, ESPsomo makes it easy to deploy interconnected sensor and actuator networks without complex infrastructure.

## ✨ Features

* Universal firmware compatible with both ESP32 (S2, S3, C3) and ESP8266
* Multi-protocol mesh networking using ESP-NOW, WiFi, and BLE
* Self-healing mesh topology for reliable communications
* Low power consumption with deep sleep support
* Over-the-air (OTA) firmware updates
* Simple configuration via web interface or JSON files
* Support for various sensors (motion, presence, illumination, etc.)
* Data logging and visualization capabilities
* Integration with popular home automation platforms

## 🔧 Hardware Requirements

### Supported Microcontrollers

* ESP32 (Standard)
* ESP32-S2
* ESP32-S3
* ESP32-C3
* ESP8266

### Recommended Specifications

* 2MB+ Flash Memory
* Stable 3.3V power supply
* For battery-powered nodes: Deep sleep support

## 💾 Software Requirements

* Arduino IDE 2.0+ or PlatformIO
* ESP Arduino Core 2.0.10
* Required Libraries:
  * ESP-NOW
  * WiFi
  * BLE (for ESP32)
  * ArduinoJSON
  * ESPsomo Core Library

## ⚙️ Installation

### Option 1: Using Arduino IDE

```
1. Install the Arduino IDE 2.0.10 or newer
2. Install the ESP Arduino Core from the Boards Manager
   - For ESP32: https://github.com/espressif/arduino-esp32
   - For ESP8266: https://github.com/esp8266/Arduino
3. Clone this repository:
   git clone https://github.com/yourusername/ESPsomo.git
4. Open the ESPsomo.ino file in Arduino IDE
5. Select your board from Tools > Board menu
6. Configure settings in config.h
7. Compile and upload to your device
```

### Option 2: Using PlatformIO

```
1. Install PlatformIO Core or PlatformIO IDE extension for VSCode
2. Clone this repository:
   git clone https://github.com/yourusername/ESPsomo.git
3. Navigate to the project directory
4. Modify platformio.ini as needed for your board
5. Configure settings in config.h
6. Build and upload:
   platformio run --target upload
```

## 🚀 Usage

### Basic Configuration

The basic configuration is done via the `config.h` file or through the web interface after initial setup.

```
// Sample configuration
#define NODE_NAME "kitchen_sensor"
#define NODE_ROLE NODE_ROLE_SENSOR  // Options: NODE_ROLE_GATEWAY, NODE_ROLE_ROUTER, NODE_ROLE_SENSOR
#define MESH_NETWORK_NAME "home_network"
#define MESH_NETWORK_PASSWORD "securepassword123"
#define DEEP_SLEEP_ENABLED true
#define DEEP_SLEEP_INTERVAL 300  // seconds
```

### Network Setup

1. Configure at least one node as a Gateway (connected to WiFi)
2. Configure additional nodes as Routers to extend network range
3. Configure end devices as Sensors (can operate in deep sleep mode)
4. Power on the Gateway first, followed by Routers, then Sensors
5. The network will auto-configure and establish optimal routing paths

### Monitoring and Management

Access the web interface through the Gateway's IP address to:

* View network topology
* Monitor sensor data
* Configure node parameters
* Update firmware
* Export data

## 🏗️ Network Architecture

ESPsomo uses a hybrid mesh architecture with three main node types:

| Node Type | Function | Power Mode | Typical Hardware |
| --- | --- | --- | --- |
| Gateway | Connects mesh to external networks (WiFi/Ethernet) | Always on | ESP32 with stable power source |
| Router | Extends network range, relays messages | Always on | ESP32/ESP8266 with stable power |
| Sensor | Collects data, performs actions | Deep sleep capable | Any ESP device, often battery powered |

Communication within the network uses:

* **ESP-NOW**: For efficient device-to-device communication with low latency
* **WiFi**: For gateway connections and high-bandwidth data transfer
* **BLE**: For energy-efficient connections and smartphone configuration

## 📊 Supported Sensors

ESPsomo supports a wide range of sensors including:

### Motion Sensors
* PIR motion sensors
* Microwave sensors
* Ultrasonic distance sensors

### Presence Detection
* mmWave radar sensors
* IR beam break sensors
* Capacitive presence detection

### Environmental Sensors
* Temperature & humidity (DHT11/22, BME280)
* Pressure sensors (BMP180/280)
* Air quality (MQ series, CCS811)

### Light Sensors
* Illumination (LDR, BH1750)
* UV index sensors
* Color sensors (TCS34725)

### Utility Sensors
* Power consumption monitors
* Water flow sensors
* Door/window contact sensors

### Custom Sensors
* Easy integration via I2C
* SPI interface support
* Analog sensor input

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add some amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

© 2025 ESPsomo Project

Made with ❤️ for the ESP IoT community
