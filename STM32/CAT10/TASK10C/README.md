# Continuous Lab Evaluation-10 (Task 10C)

**EXP:** Continuous Lab Evaluation-10  
**DATE:** 23/10/2026  
**NAME OF EXP:** Access Point Association & IP Address Acquisition via ESP8266 on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + WeMos ESP8266 + Wi-Fi Access Point  

---

### Circuit Diagram
![Circuit Diagram](../CAT10.png)

---

### Core Logic

* **1. Wireless Access Point Association**  
  Dispatches `AT+CWJAP="SSID","PASSWORD"` to join the wireless network, allowing extended timeout for DHCP IP assignment:
  ```c
  send_cmds("AT+CWJAP=\"SNUC\",\"snu12345\"\r\n", 12000);
  ```

* **2. IP Address & MAC Address Resolution**  
  Executes `AT+CIFSR` to retrieve and verify assigned IPv4 address and hardware MAC address.

---

### Inference
Successful DHCP association to an external Wi-Fi access point was achieved. The STM32 receives its network address, enabling TCP/IP socket communications.
