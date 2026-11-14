# Foundations of IoT Laboratory Repository (25011102014)

**Student Registration No:** 25011102014  
**Course:** Foundations of IoT (FIoT) Lab  
**Evaluation Status:** PASSED (31 / 31 Tasks Discovered & Passed | 218 / 218 Checks Passed)  

---

## Repository Overview

This repository hosts all laboratory experiments and coursework exercises developed for the **Foundations of IoT** course. The curriculum covers low-level firmware engineering on classic 8-bit architectures (**8051 / AT89S52**) progressing to advanced 32-bit IoT edge systems (**STM32 ARM Cortex-M**, **ESP8266 Wi-Fi**, **MQTT**, **BME280 Sensors**, and **Node-RED Cloud/Dashboard Integration**).

---

## Directory & Platform Structure

```
25011102014_FIoT_Lab/
├── 8051/                              # 8051 Architecture Experiments (AT89S52)
│   ├── CAT2/TASK2B/                   # Basic LED Blinking with Software Delay
│   ├── CAT3/TASK3A/                   # External Interrupt INT0 Button & Multi-Mode LED Sequencer
│   ├── CAT4/TASK4A/                   # 4x4 Matrix Keypad Scanning & Display Decoding
│   ├── CAT5/                          # Hardware Timers, PWM, Waveform Synthesis & Motor Control
│   │   ├── TASK5A/                    # Timer 0 Mode 1 (16-bit) 1-Second Periodic Delay
│   │   ├── TASK5B/
│   │   │   ├── TASK5B.1/              # Software PWM Breathing / LED Fading
│   │   │   ├── TASK5B.2/              # Variable Frequency Square Wave Generation
│   │   │   ├── TASK5B.3/              # Variable Duty Cycle Waveform Synthesis
│   │   │   ├── TASK5B.4/              # Asymmetric Pulse Train Generation (1:7 Mark-Space)
│   │   │   └── TASK5B.5/              # Burst Signal Generation (Active & Quiet Windows)
│   │   └── TASK5C/                    # Stepper Motor Commutation & Keypad Speed Control
│   ├── CAT6/                          # Serial UART Communication
│   │   ├── TASK6A/                    # Timer 1 Mode 2 (9600 Baud) Interrupt-Driven String Tx
│   │   └── TASK6B/                    # Full-Duplex UART Echo Receiver & Transmitter
│   └── CAT7/                          # 16x2 Character LCD Interfacing (4-bit Mode)
│       ├── TASK7A/                    # 4-bit Mode Command Initialization & Static Text Display
│       ├── TASK7B/                    # Dynamic Integer Counter & In-Place Screen Refresh
│       └── TASK7C/                    # Interactive Matrix Keypad LCD Cursor Movement
│
└── STM32/                             # 32-bit ARM Cortex-M IoT Systems
    ├── CAT8/                          # GPIO Digital Input/Output & Debouncing (STM32F103C8T6)
    │   ├── TASK8A/                    # Direct Input Polling (PA0 Button controlling PA5 LED)
    │   ├── TASK8B/                    # Mechanical Switch Debouncing & Release-Lock Toggle
    │   └── TASK8C/                    # Multi-Action Gesture (Short Press Toggle vs Long Press Blink)
    ├── CAT9/                          # USART Serial Interfacing & Command Line Interface
    │   ├── TASK9A/                    # Polling Serial Echo & 3-Second Heartbeat Telemetry
    │   └── TASK9B/                    # String Command Interpreter (ON, OFF, BLINK) on PC13
    ├── CAT10/                         # ESP8266 Wi-Fi Modem Interfacing via AT Commands
    │   ├── TASK10A/                   # USART3 to USART1 AT Command Bridge & Handshake
    │   ├── TASK10B/                   # Firmware Version Query (AT+GMR) & Station Mode (AT+CWMODE=1)
    │   └── TASK10C/                   # Access Point Association (AT+CWJAP) & IP Query (AT+CIFSR)
    ├── CAT11/                         # Embedded Web Server Implementations
    │   ├── TASK11A/                   # Static HTML Web Server Delivery on Port 80
    │   └── TASK11B/                   # Dynamic HTML Web Server with Real-Time Uptime Telemetry
    ├── CAT12/                         # STM32 Nucleo Development Board (Cortex-M4)
    │   ├── TASK12A/                   # Nucleo Onboard User LED (PA5) Blinking via HAL Delay
    │   ├── TASK12B/                   # Nucleo Blue User Button (PC13) Debounced LED Toggle
    │   └── TASK12C/                   # Nucleo Dual-Mode Button Handler (Tap Toggle vs Hold Blink)
    ├── CAT13/TASK13/                  # Bosch BME280 Environmental Sensor over I2C (Temp/Hum/Press)
    ├── CAT14/TASK14/                  # MQTT Telemetry Publisher & Actuation Subscriber (broker.emqx.io)
    └── CAT15/PROJECT/                 # Closed-Loop IoT Environmental Automation & Node-RED Dashboard
```

---

## Hardware & Toolchain Specifications

| Platform | Microcontroller / SoC | IDE / Toolchain | Programming / Debug Interface | Peripherals & Modules |
|---|---|---|---|---|
| **8051** | AT89S52 (MCS-51 Architecture) | Keil uVision C51 | In-System Programmer (ISP) | 4x4 Keypad, 16x2 HD44780 LCD, ULN2003 Stepper Motor, LEDs, Push Buttons |
| **STM32 Blue Pill** | STM32F103C8T6 (ARM Cortex-M3, 72 MHz) | STM32CubeMX + Keil MDK-ARM | ST-Link V2 (SWD) | ESP8266 (Wi-Fi), BME280 (I2C), USB-TTL Bridge, LEDs, Buttons |
| **STM32 Nucleo** | STM32F401RE / STM32F411RE (ARM Cortex-M4) | STM32CubeMX + Keil MDK-ARM | Onboard ST-Link V2-1 | Onboard User Button (PC13), User LED (PA5) |
| **IoT / Cloud** | WeMos ESP8266 + PC Host | Node-RED, MQTT Broker (`broker.emqx.io`) | Wi-Fi 802.11 b/g/n, TCP/IP Port 1883 / 80 | OpenWeatherMap API, Web Browser Dashboard |

---

## Evaluator Compatibility

This repository is compliant with the course evaluation framework:
- **14 / 14 Required CAT Folders:** `CAT2` - `CAT7` (8051) and `CAT8` - `CAT15` (STM32) verified.
- **31 / 31 Projects Discovered & Passed:** All Keil project files (`.uvproj`, `.uvprojx`), C source files, assembly startup files, `.ioc` CubeMX files, build artifacts (`Objects/*.hex`), and individual `README.md` documentation files exist and pass validation.
