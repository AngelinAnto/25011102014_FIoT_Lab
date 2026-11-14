# Continuous Lab Evaluation-10 (Task 10B)

**EXP:** Continuous Lab Evaluation-10  
**DATE:** 23/10/2026  
**NAME OF EXP:** ESP8266 Firmware Query & Wi-Fi Station Mode Configuration on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + ESP8266 Wi-Fi Module + USB-to-TTL Adapter  

---

### Circuit Diagram
![Circuit Diagram](../CAT10.png)

---

### Core Logic

* **1. Automated AT Command Dispatcher**  
  `send_cmds(cmd, wait_time)` transmits formatted commands to the ESP8266 while logging bidirectional traffic to the PC terminal.

* **2. Version Query & Station Mode Setup**  
  - `AT+GMR`: Queries SDK and AT firmware version strings.
  - `AT+CWMODE=1`: Sets ESP8266 to Wi-Fi Station Mode:
  ```c
  send_cmds("AT\r\n", 1000);
  send_cmds("AT+GMR\r\n", 2000);
  send_cmds("AT+CWMODE=1\r\n", 1000);
  ```

---

### Inference
The ESP8266 Wi-Fi modem was verified and configured into Station mode, allowing the embedded system to join local wireless LAN infrastructure.
