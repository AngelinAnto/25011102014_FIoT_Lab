# Continuous Lab Evaluation-11 (Task 11B)

**EXP:** Continuous Lab Evaluation-11  
**DATE:** 30/10/2026  
**NAME OF EXP:** Dynamic HTTP Web Server with Real-Time Uptime Telemetry on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + ESP8266 + Web Browser  

---

### Circuit Diagram
![Circuit Diagram](../CAT11.png)

---

### Core Logic

* **1. Real-Time Telemetry Generation**  
  Calculates system uptime using `HAL_GetTick() / 1000` and generates HTML payloads containing meta auto-refresh headers:
  ```c
  int uptime_seconds = HAL_GetTick() / 1000;
  char html_body[256];
  int len = snprintf(html_body, sizeof(html_body),
      "<html><head><meta http-equiv=\"refresh\" content=\"2\"></head>"
      "<body>"
      "<h1>STM32 & ESP8266 Web Server</h1>"
      "<p><b>Status:</b> Static & Dynamic Data Working!</p>"
      "<p><b>System Uptime:</b> %d seconds</p>"
      "</body></html>", uptime_seconds);
  ```

* **2. Sliced TCP Transmission**  
  Transmits response length using `AT+CIPSEND=<link_id>,<len>`, followed by HTTP response payload streaming and socket closure.

---

### Inference
Dynamic embedded web pages were served with auto-refreshing parameters. Live sensor telemetry or system counters can be monitored from web browsers without external servers.
