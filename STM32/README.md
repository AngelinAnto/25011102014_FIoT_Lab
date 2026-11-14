# STM32 ARM Cortex-M Laboratory Exercises

This directory contains all laboratory experiments developed on the STM32 ARM Cortex microcontroller platform using STM32CubeMX, Keil MDK-ARM, and STM32 HAL libraries.

## Experiment Index

| CAT Folder | Task | Description | Target Hardware / Peripherals |
|---|---|---|---|
| **CAT8** | `TASK8A` | Direct GPIO Input Polling (Button to LED) | STM32F103C8T6 (Blue Pill), PA0 Button, PA5 LED |
| **CAT8** | `TASK8B` | Push Button Debouncing & Release-Lock Toggle State Machine | STM32F103C8T6, PA0 Button, PA5 LED |
| **CAT8** | `TASK8C` | Multi-Action Gesture (Short Press Toggle vs Long Press Blink) | STM32F103C8T6, SysTick Timing, PA0, PA5 |
| **CAT9** | `TASK9A` | USART1 Polling Serial Echo & 3-Second Heartbeat Telemetry | STM32F103C8T6, USART1 (PA9/PA10), USB-TTL Bridge |
| **CAT9** | `TASK9B` | Command-Line Interface (CLI) Parser (ON, OFF, BLINK) | STM32F103C8T6, USART1, PC13 User LED |
| **CAT10** | `TASK10A` | ESP8266 Modem AT Command Handshake & Terminal Relay | STM32F103C8T6, ESP8266 (USART3), PC Terminal (USART1) |
| **CAT10** | `TASK10B` | ESP8266 Firmware Query (AT+GMR) & Station Mode Setup | STM32F103C8T6, ESP8266, AT Command Parser |
| **CAT10** | `TASK10C` | Access Point Association (AT+CWJAP) & IP Address Query | STM32F103C8T6, ESP8266, Wi-Fi Station Mode |
| **CAT11** | `TASK11A` | Embedded HTTP Web Server on Port 80 (Static HTML Delivery) | STM32F103C8T6, ESP8266, TCP Server Port 80 |
| **CAT11** | `TASK11B` | Dynamic HTTP Web Server with Real-Time Uptime Telemetry | STM32F103C8T6, ESP8266, Auto-refreshing HTML |
| **CAT12** | `TASK12A` | Nucleo Board User LED (PA5) Blinking via HAL Delay | STM32 Nucleo-F401RE / F411RE, Cortex-M4, PA5 LED |
| **CAT12** | `TASK12B` | Nucleo Board Blue User Button (PC13) Debounced Toggle | STM32 Nucleo Board, PC13 Button, PA5 LED |
| **CAT12** | `TASK12C` | Nucleo Dual-Mode Push Button (Tap Toggle vs Hold Blink) | STM32 Nucleo Board, PC13 Button, PA5 LED |
| **CAT13** | `TASK13` | Bosch BME280 Environmental Sensor over I2C | STM32F103C8T6, BME280 (I2C1: PB6 SCL, PB7 SDA) |
| **CAT14** | `TASK14` | MQTT Telemetry Publisher & Command Subscriber | STM32F103C8T6, BME280, ESP8266, MQTT Broker (`broker.emqx.io`) |
| **CAT15** | `PROJECT` | Closed-Loop Environmental Automation & Node-RED Dashboard | STM32F103C8T6, BME280, ESP8266, OpenWeatherMap, Node-RED |
