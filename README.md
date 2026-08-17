# CDAC-Project-Realtime-EV-Management-System-with-Safety-Protections
A real-time Battery Management and Safety System (BMS) for electric vehicles, designed using a dual-STM32 architecture with CAN bus communication, FreeRTOS task scheduling, and IoT monitoring via ESP32 and MQTT/HTTP.
# EV Battery Management System (BMS)

An STM32-based Electric Vehicle Battery Management System featuring real-time sensor monitoring, CAN bus communication between multiple microcontrollers, RTOS and bare-metal (non-RTOS) firmware implementations, and a live web dashboard.

## 🔋 Overview

This project implements a multi-node BMS for electric vehicles using STM32F4 microcontrollers. Two STM32 nodes communicate over **CAN bus**, collecting data from current and smoke sensors and driving actuators (fan, buzzer, LCD) for safety monitoring and status display. Sensor data is also published to a **web-based dashboard** for real-time visualization of State of Charge (SOC), current, and system alerts.

## ✨ Features

- 🔌 **Current sensing** for battery load monitoring
- 🔥 **Smoke/gas sensing** for fire and thermal-runaway safety
- 🚗 **Dual STM32 nodes** communicating over CAN bus
- ⚙️ **RTOS and Non-RTOS** firmware implementations for comparison
- 🌀 **Fan control** for thermal management
- 🔊 **Buzzer alerts** for fault/alarm conditions
- 🖥️ **LCD display** for local status readouts
- 📊 **Web dashboard** (HTML + Chart.js + MQTT) for live SOC, current, and alert visualization
- 📄 Design documentation and logic implementation reports (PDF)

## 🗂️ Project Structure

```
.
├── bms_stm1_full setup/          # STM32 Node 1 – main BMS firmware (STM32CubeIDE project)
├── full_setup_stm2/               # STM32 Node 2 – secondary node firmware
├── Current_Sensor/                # Current sensor module firmware
├── Smoke_Sensor/                  # Smoke sensor module firmware
├── smoke_tmp_through_can/         # Smoke/temperature data relay over CAN
├── fan_setup/                     # Cooling fan control firmware
├── buzzer_setup/                  # Buzzer alert firmware
├── lcd_setup/                     # LCD display firmware
├── Non_Rtos_Final_Codes/          # Bare-metal (non-RTOS) implementation
├── Professional_EV_BMS_Dashboard_FIXED.html   # Live web dashboard (Chart.js + MQTT)
├── Logic_Implementation_1.pdf
├── Logic_Implementation_2.pdf
├── Logic_implementaion_3.pdf
├── RTOS_Implementation.pdf
└── README.md
```

> Each firmware folder is a self-contained **STM32CubeIDE** project (`.ioc` + `Core/` + `Drivers/`) built on the STM32F4xx HAL library.

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Microcontroller | STM32F4 series |
| Firmware | C, STM32 HAL, FreeRTOS (RTOS builds) |
| Communication | CAN bus (inter-MCU), MQTT (dashboard) |
| IDE | STM32CubeIDE |
| Dashboard | HTML, JavaScript, Chart.js, MQTT.js |

## 🚀 Getting Started

### Hardware
- 2x STM32F4 development boards (e.g., STM32F407/F401 Discovery/Nucleo)
- CAN transceiver module(s)
- Current sensor (e.g., ACS712)
- Smoke/gas sensor (e.g., MQ-2)
- Cooling fan, buzzer, 16x2 LCD

### Firmware Setup
1. Install [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html).
2. Import the relevant project folder via **File → Import → Existing Projects into Workspace**.
3. Connect your STM32 board via ST-Link and build/flash the project.
4. Repeat for each node (STM1, STM2, sensor/actuator modules) as needed.

### Dashboard Setup
1. Open `Professional_EV_BMS_Dashboard_FIXED.html` in a browser, or serve it with any static file server.
2. Update the MQTT broker URL/topic inside the HTML file to match your setup.
3. Ensure your STM32/gateway publishes sensor data to the configured MQTT topic.

## 📄 Documentation

- `RTOS_Implementation.pdf` — RTOS-based firmware design
- `Logic_Implementation_1/2/3.pdf` — Core logic and control-flow documentation

## 👥 Contributors

_Add your team/group members here._

## 📜 License

_Add a license (e.g., MIT) if you intend this repo to be open source._
